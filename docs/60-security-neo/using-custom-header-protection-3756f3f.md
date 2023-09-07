<!-- loio3756f3fc7b4342d39db1bbe57d1b2d57 -->

# Using Custom Header Protection



## Context

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**

Custom header protection is one of the possible approaches for CSRF protection. It is based on adding a servlet filter that inspects state modifying requests for the presence of valid CSRF token. The CSRF token is transferred as a custom header and is valid during the user session. This kind of protection specifically addresses the protection of REST APIs, which are normally not accessed from entry point pages. Note that the CSRF protection is performed only for modifying HTTP requests \(different from GET|HEAD or OPTIONS\).

In a nutshell, the REST CSRF protection mechanism consists of the following communication steps:

1.  The REST CLIENT obtains a valid CSRF token with an initial non-modifying "Fetch" request to the application.
2.  The SERVER responds with the valid CSRF token mapped to the current user session.
3.  The REST CLIENT includes the valid CSRF token in the subsequent modifying REST requests in the frame of the same user session.
4.  The SERVER rejects all modifying requests to protected resources that do not contain the valid CSRF token.

Custom header CSRF protection mechanism requires adoption both in the client \(JavaScript\) and server \(REST\) parts of the Web applications.

To better illustrate the mechanism we’ll use an example web application exposing the following REST APIs. We’ll use the same example application throughout the document.


<table>
<tr>
<th valign="top">

Number



</th>
<th valign="top">

Exposed with HTTP methods



</th>
<th valign="top">

REST API



</th>
<th valign="top">

Description



</th>
<th valign="top">

Type



</th>
</tr>
<tr>
<td valign="top">

1



</td>
<td valign="top">

GET



</td>
<td valign="top">

/services/list



</td>
<td valign="top">

Prints customers list in the output.



</td>
<td valign="top">

non-modifying



</td>
</tr>
<tr>
<td valign="top">

2



</td>
<td valign="top">

POST



</td>
<td valign="top">

/services/customers/removeCustomer



</td>
<td valign="top">

Removes the first item from the customers list.



</td>
<td valign="top">

modifying



</td>
</tr>
<tr>
<td valign="top">

3



</td>
<td valign="top">

POST



</td>
<td valign="top">

/services/customers/addCustomer



</td>
<td valign="top">

Adds a customer to the customers list.



</td>
<td valign="top">

modifying



</td>
</tr>
</table>

<a name="task_nlp_13d_tn"/>

<!-- task\_nlp\_13d\_tn -->

## 1. In the REST Service



## Prerequisites

You have created a working Web application and have enforced authentication for it, as described in [Authentication](authentication-e637f62.md#loioe637f62abb571014857cb0232adc43a7). All CSRF protected resources should be protected with an authentication mechanism.



<a name="task_nlp_13d_tn__steps_e1h_v3d_tn"/>

## Procedure

In the application's `web.xml`, protect all REST APIs using the out-of-the-box CSRF filter available with the SAP BTP SDK.

> ### Note:  
> You must have at least one non-modifying REST operation listed.

Identify all web application resources that have to be CSRF protected and map them to `org.apache.catalina.filters.RestCsrfPreventionFilter` \(this class represents the out-of-the-box CSRF filter available with the SAP BTP SDK, so you do not need to instantiate/implement it\) in the `web.xml`.

> ### Note:  
> If you are using an older version of the SAP BTP rutime for Java, use the `com.sap.core.js.csrf.RestCsrfPreventionFilter` class instead. It delivers the same implementation as the other one. Namely, use that class with the following runtime versions:
> 
> -   Java Web 1.x lower than 1.98.22
> -   Java EE Web Profile lower than 2.80.14
> -   Java Web Tomcat 7 lower than 2.45.16

As a result, all modifying HTTP requests matching the given `url-pattern` would be CSRF validated, i.e. checked for the presence of the valid CSRF token.

Applications should expose at least one non-modifying REST operation to enable CSRF token fetch mechanism. In order to obtain the valid CSRF token, the clients need to make an initial fetch requests. That is why the non-modifying REST API is necessary. Requirements for the non-modifying REST API:

-   Any GET/HEAD/OPTIONS requests to the URL shall not cause state modification.
-   The URL should be mapped to the `RestCsrfPreventionFilter` 
-   The URL should be protected with authentication mechanism.



### Example

The following example illustrates mapping a set of modifying REST APIs and one non-modifying REST API to the CSRF protection filter in the application’s `web.xml` deployment descriptor:

```
<filter>
   <filter-name>RestCSRF</filter-name>
   <filter-class>org.apache.catalina.filters.RestCsrfPreventionFilter</filter-class>
 </filter>
 <filter-mapping>
   <filter-name>RestCSRF</filter-name>
    <!— modifying REST APIs-->
    <url-pattern>/services/customers/removeCustomer</url-pattern>
    <url-pattern>/services/customers/addCustomer</url-pattern>
    <url-pattern>/services/customers/initCustomers</url-pattern>
    <!— non-modifying REST API-->
    <url-pattern>/services/customers/list</url-pattern>
 </filter-mapping>

```

<a name="task_frp_gjd_tn"/>

<!-- task\_frp\_gjd\_tn -->

## 2. In REST Clients



<a name="task_frp_gjd_tn__steps_o2g_kjd_tn"/>

## Procedure

1.  Make a fetch request.

    As a first step, the REST client should obtain the valid CSRF token for the current session. For this it makes a non-modifying request and includes a custom header `"X-CSRF-Token: Fetch"`. The returned `[sessionid – csrf token]` pair should be cached and used in subsequent REST requests by the client. Another option is to send Fetch request before every REST request and thus to use the `[sessionid – csrf token]` pair only once.

    Example HTTP Request-Response flow:

    ```
    Client Request:
    GET /restDemo/services/customers/list HTTP/1.1
    X-CSRF-Token: Fetch
    Authorization: Basic dG9tY2F0OnRvbWNhdA==
    Host: localhost:8080
     
    Server Response:
    HTTP/1.1 200 OK
    Set-Cookie: JSESSIONID=4BA3D75B73B8C4591F1D915BA9C2B660; Path=/restDemo/; HttpOnly
    X-CSRF-Token: 5A44B387B75E54417F6C64FF3D485141
    ..
    
    ```

2.  Use the cached `[sessionid – csrf token]` pair for subsequent REST requests.

    Subsequent modifying REST requests to the same application should include the valid jsessionid cookie and the valid `X-CSRF-Token` header.

    Example HTTP Request -Response flow:

    ```
    Client Request:
    POST /restDemo/services/customers/removeCustomer HTTP/1.1
    Cookie: JSESSIONID=4BA3D75B73B8C4591F1D915BA9C2B660
    X-CSRF-Token: 5A44B387B75E54417F6C64FF3D485141
    Authorization: Basic dG9tY2F0OnRvbWNhdA==
    Host: localhost:8080
     
    Server Response:
    HTTP/1.1 200 OK
    ..
    
    ```

3.  Handling error server responses

    The client should be prepared for the following server response:

    ```
    403 Forbidden
    X-CSRF-Token: Required
    
    ```

    It may occur in one of these cases:

    -   Invalid or missing CSRF token in the request.
    -   Expired session - after session expiration the `[sessionid – csrf token]` pair is no longer valid and it should be reinitialized by the client.
    -   There are cases when the sessionid is changed by the server and the client should take into account such changes.


<a name="task_lm2_dkd_tn"/>

<!-- task\_lm2\_dkd\_tn -->

## Exceptional Cases



## Context

In small number of use cases the client is not able to insert custom headers in its calls to a REST API. For example file uploads via POST HTML FORM consuming a REST API. Only for such use-cases there is an additional capability to configure REST APIs for which the valid CSRF token will be accepted as request parameter \(not only header\). If there is a `X-CSRF-Token` header, it will be taken with preference over any parameter with the same name in the request.

> ### Tip:  
> For security reasons we strongly recommend the following:
> 
> -   Use this approach only when the header approach cannot be applied.
> -   Use only hidden post parameter with name `X-CSRF-Token`, and not query parameters.

Example configuration in the `web.xml` deployment descriptor:

```
<filter>  
    <filter-name>CSRF</filter-name>
    <filter-class>org.apache.catalina.filters.RestCsrfPreventionFilter</filter-class>
    <init-param>
        <param-name>pathsAcceptingParams</param-name>
        <param-value>/services/customers/acceptedPath1.jsp,/services/customers/acceptedPath2.jsp
</param-value>
    </init-param>
</filter>
<filter-mapping>
    <filter-name>CSRF</filter-name>
    <url-pattern>/services/customers/*</url-pattern>
</filter-mapping>

```

