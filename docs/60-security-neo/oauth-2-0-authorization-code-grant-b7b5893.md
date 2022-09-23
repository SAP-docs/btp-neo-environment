<!-- loiob7b589334d444293a2a91e0ef4234136 -->

# OAuth 2.0 Authorization Code Grant

Use OAuth 2.0 service in the Neo environment of SAP BTP to enable your cloud applications for authorization code grant flow. Authorization code grant is one of the basic flows specified in the OAuth 2.0 protocol.

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**

 



## Overview

**OAuth 2.0**

OAuth has taken off as a standard way and a best practice for applications and websites to handle authorization. OAuth defines an open protocol for allowing secure API authorization of desktop, mobile and web applications through a simple and standard method.

OAuth is based on granting access without explicit credentials sharing. OAuth:

-   Avoids storing credentials at the third-party location
-   Limits the access permissions granted to third parties
-   Enables easy access right revocation without the need to change credentials

In this way, OAuth mitigates some of the common concerns with authorization scenarios.

The following table shows the roles defined by OAuth, and their respective entities in SAP BTP:


<table>
<tr>
<th valign="top">

Role



</th>
<th valign="top">

Entity in SAP BTP



</th>
<th valign="top">

Description



</th>
</tr>
<tr>
<td valign="top">

Resource owner



</td>
<td valign="top">

User



</td>
<td valign="top">

An entity that holds protected assets. This entity is capable of granting access to those assets under its control.



</td>
</tr>
<tr>
<td valign="top">

Resource server



</td>
<td valign="top">

Application



</td>
<td valign="top">

The server that hosts the resource owner's protected assets.



</td>
</tr>
<tr>
<td valign="top">

Client



</td>
<td valign="top">

Third-party application



</td>
<td valign="top">

The third party entity that needs to access the protected assets on behalf of the resource owner.



</td>
</tr>
<tr>
<td valign="top">

Authorization server



</td>
<td valign="top">

SAP BTP infrastructure



</td>
<td valign="top">

The server that manages the authentication and authorization of the different entities involved.



</td>
</tr>
</table>

For more information, see the [OAuth 2.0 Specification](http://oauth.net/2/).



## Using OAuth in SAP BTP

 **Protecting Resources Declaratively**

If you want to implement a login based on credentials in the form of an OAuth token, you can do that by using OAuth as a login method in your application web.xml. For example:

```
<login-config>
  <auth-method>OAUTH</auth-method>
</login-config>
<security-constraint>
  <web-resource-collection>
    <web-resource-name>Protected Area</web-resource-name>
    <url-pattern>/rest/get-photos</url-pattern>
  </web-resource-collection>
  <auth-constraint>
    <!-- Role Everyone will not be assignable -->
    <role-name>Everyone</role-name>
    </auth-constraint>
</security-constraint>
<security-role>
  <description>All SAP BTP users</description>
  <role-name>Everyone</role-name>
</security-role>
```

For more information, see [Enabling Authentication](authentication-e637f62.md#loioe637f62abb571014857cb0232adc43a7)

**Working with User Attributes**

In your protected application you can acquire the user ID and attributes as described in [Working with User Profile Attributes](user-attributes-9e2e0d7.md).

There are two additional user attributes you can use to retrieve token specific information:

-   `com.sap.security.oauth2.clientId` - holds information about the OAuth client ID
-   `com.sap.security.oauth2.grantedScopes` - holds information about the granted scopes.

**Handling Sessions**

The Java EE specification requires session support on the client side. Sessions are maintained with a cookie which the client receives during the authentication and then passes it along to the server on every request. The OAuth specification, however, does not necessarily require the client to support such a session mechanism. That is, the support of cookies is not mandatory. On every request, the client passes along to the server only the token instead of passing cookies. Using the OAuth login module described in the Protecting Resources Declaratively section, you can implement a user login based on an access token. The login, however, occurs on every request, and thus it implies the risk of creating too many sessions in the Web container.

To use requests that do not hold a Web container session, use a filter with the proper configuration, as described in the following example:

```
<filter>
    <display-name>OAuth scope definition for viewing a photo album</display-name>
    <filter-name>OAuthViewPhotosScopeFilter</filter-name>
    <filter-class>
      com.sap.cloud.security.oauth2.OAuthAuthorizationFilter
    </filter-class>
  <init-param>
    <param-name>scope</param-name>
    <param-value>view-photos_upload-photos</param-value>
  </init-param>
      <init-param>
    <param-name>no-session</param-name>
    <param-value>false</param-value>
  </init-param>
</filter>
```

**Checking Scopes Declaratively**

One of the ways to enforce scope checks for resources is to declare the resource protection in the web.xml. This is done by specifying the following elements:


<table>
<tr>
<th valign="top">

Element



</th>
<th valign="top">

Description



</th>
</tr>
<tr>
<td valign="top">

Servlet filter class



</td>
<td valign="top">

Enter as value ***com.sap.cloud.security.oauth2.OAuthAuthorizationFilter***.

On request it checks if the request contains a valid OAuth token to access the resources mapped to the configured scope.



</td>
</tr>
<tr>
<td valign="top">

Protected resources



</td>
<td valign="top">

Could be given as URL pattern or servlet.



</td>
</tr>
<tr>
<td valign="top">

Initial parameters



</td>
<td valign="top">

With these, you specify the scope, user principal and HTTP method:

-   `scope`
-   `http-method`
-   `user-principal` - if set to "yes", you will get the user ID
-   `no-session` - if you set this to "true", the session will be destroyed when you finish using the filter. This means that each time the filter is used, a new session will be created. Default value: false.



</td>
</tr>
</table>

The following example shows a sample web.xml for defining and configuring OAuth resource protection for the application.

```
<filter>
    <display-name>OAuth scope definition for viewing a photo album</display-name>
    <filter-name>OAuthViewPhotosScopeFilter</filter-name>
    <filter-class>
      com.sap.cloud.security.oauth2.OAuthAuthorizationFilter
    </filter-class>
  <init-param>
    <param-name>scope</param-name>
    <param-value>view-photos</param-value>
  </init-param>
  <init-param>
    <param-name>http-method</param-name>
    <param-value>get post</param-value>
  </init-param>
</filter>

				
```

**Declaring resource-to-scope Filter Mapping**

In this code snippet you can observe how the `PhotoAlbumServlet` is mapped to the previously specified OAuth scope filter:

```
<filter-mapping>
  <filter-name>OAuthViewPhotosScopeFilter</filter-name>
  <servlet-name>PhotoAlbumServlet</servlet-name>
</filter-mapping>
```

If you would like to use URL pattern instead, simply specify the pattern that should apply here:

```
<filter-mapping>
  <filter-name>OAuthViewPhotosScopeFilter</filter-name>
  <url-pattern>/photos/*.jpg</url-pattern>
</filter-mapping>
```

In the second case, all files with the \*`.jpg` extension that are served from the `/photos` directory will be protected by the OAuth filter.

For more information regarding possible mappings, see the `filter-mapping` element specification.



## Protecting Resources Programmatically

Alternatively to the declarative approach with the `web.xml` \(described above\), you can use the OAUTH login module programmatically. For more information, see [Programmatic Authentication](authentication-e637f62.md#loio778d8987e7714376977c190f6df379ad).



## Creating Protected Resource Requests

When a resource protected by OAuth is requested, your application must pass the access token using the HTTP "Authorization" request header field. The value of this header must be the token type and access token value. The currently supported token type is "bearer".



## Possible Responses to Requests for Protected Resources

When the protected resource access check is performed the filter calls the API and the API calls the authorization server to check the validity of the access token and retrieve token’s scopes.

In the table below the result handling between the authorization server and resource server, resource server and the API, and resource server and filter is presented.

<a name="loiob7b589334d444293a2a91e0ef4234136__table_jkp_xwb_ml"/>Responses to requests for protected resources


<table>
<tr>
<th valign="top" colspan="2">

Authorization server to resource server



</th>
<th valign="top" colspan="2">

Resource server to the API



</th>
<th valign="top" colspan="2">

Resource server to the filter



</th>
</tr>
<tr>
<td valign="top">

**Code**



</td>
<td valign="top">

**Description**



</td>
<td valign="top">

**Return value / Exception**



</td>
<td valign="top">

**Description**



</td>
<td valign="top">

**Code**



</td>
<td valign="top">

**Description**



</td>
</tr>
<tr>
<td valign="top">

`200`



</td>
<td valign="top">

`access_token` is valid



</td>
<td valign="top">

`True`



</td>
<td valign="top">

attribute "`user_id`" in the request

attribute "`client_id`" in the request



</td>
<td valign="top">

 



</td>
<td valign="top">

Access is allowed.

attribute "`client_id`" in the request

attribute "`user_id`" in the request

If `user-principal=true` -\>`request.getUserPrincipal(). getName()` returns `user_id`



</td>
</tr>
<tr>
<td valign="top">

`200`



</td>
<td valign="top">

 `access_token` is valid



</td>
<td valign="top">

`False`



</td>
<td valign="top">

attribute "`reason`" in the request describing the reason for the result

`reason = "access_forbidden"` 



</td>
<td valign="top">

`403`



</td>
<td valign="top">

Access is forbidden



</td>
</tr>
<tr>
<td valign="top">

`400`



</td>
<td valign="top">

 `access_token` parameter is null, empty string, missing or it is given more than once



</td>
<td valign="top">

`False`



</td>
<td valign="top">

Attribute "`reason`" in the request describing the reason for the result

`reason = "missing_access_token`



</td>
<td valign="top">

`401`



</td>
<td valign="top">

 



</td>
</tr>
<tr>
<td valign="top">

`401`



</td>
<td valign="top">

 `access_token` does not exist



</td>
<td valign="top">

`False`



</td>
<td valign="top">

Attribute "`reason`" in the request describing the reason for the result

`reason = "missing_access_token`



</td>
<td valign="top">

`401`



</td>
<td valign="top">

 



</td>
</tr>
<tr>
<td valign="top">

`401`



</td>
<td valign="top">

 `access_token` has expired



</td>
<td valign="top">

`False`



</td>
<td valign="top">

Attribute "`reason`" in the request describing the reason for the result

`reason = "missing_access_token`



</td>
<td valign="top">

`401`



</td>
<td valign="top">

 



</td>
</tr>
<tr>
<td valign="top">

`401`



</td>
<td valign="top">

 `access_token` is not issued for the current subscription



</td>
<td valign="top">

`False`



</td>
<td valign="top">

Attribute "`reason`" in the request describing the reason for the result

`reason = "missing_access_token`



</td>
<td valign="top">

`401`



</td>
<td valign="top">

 



</td>
</tr>
<tr>
<td valign="top">

`500`



</td>
<td valign="top">

Unexpected error \(no connection to the database\)



</td>
<td valign="top">

`OAuthSystemException` 

\(extends `Exception`\)



</td>
<td valign="top">

Inherit message from the original exception



</td>
<td valign="top">

`500`



</td>
<td valign="top">

 



</td>
</tr>
<tr>
<td valign="top">

 



</td>
<td valign="top">

 



</td>
<td valign="top">

`OAuthSystemException` 

\(extends `Exception`\)



</td>
<td valign="top">

HTTP request to the authorization server fails



</td>
<td valign="top">

 



</td>
<td valign="top">

 



</td>
</tr>
<tr>
<td valign="top">

 



</td>
<td valign="top">

 



</td>
<td valign="top">

`OAuthSystemException` 

\(extends `Exception`\)



</td>
<td valign="top">

OAuth destination is not found or can’t get destination HTTP client



</td>
<td valign="top">

 



</td>
<td valign="top">

 



</td>
</tr>
</table>



## Next Steps

1.  You can now deploy the application on SAP BTP. For more information, see [Deploying and Updating Java Applications](../30-development-neo/deploying-and-updating-java-applications-e5dfbc6.md) 
2.  After you deploy, you need to configure clients and scopes for the application. For more information, see [OAuth 2.0 Configuration](oauth-2-0-configuration-7e658b3.md).

