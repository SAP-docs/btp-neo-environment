<!-- loioe637f62abb571014857cb0232adc43a7 -->

# Authentication

In the Neo environment, enable user authentication for access to your applications.



## Context

-   [Declarative Authentication](authentication-e637f62.md#loioe36c712efa844e8199a9c4bd681cb4e0)
-   [Programmatic Authentication](authentication-e637f62.md#loio778d8987e7714376977c190f6df379ad)
-   [Handling Session Timeout](authentication-e637f62.md#loio6ad764f643bb401d8a50529afb1d17b3)
-   [Troubleshooting](authentication-e637f62.md#loio4ac91c9b213e4b67bba550d02991b49e)

> ### Note:  
> User names in SAP BTP are case insensitive.

<a name="loioe36c712efa844e8199a9c4bd681cb4e0"/>

<!-- loioe36c712efa844e8199a9c4bd681cb4e0 -->

## Declarative Authentication



## Context

The Java EE servlet specification allows the security mechanisms for an application to be declared in the `web.xml` deployment descriptor.

SAP BTP supports the following default authentication methods:


<table>
<tr>
<th valign="top">

Authentication Method

</th>
<th valign="top">

Default Login Options

</th>
<th valign="top">

Description

</th>
<th valign="top">

Sample Use Case

</th>
</tr>
<tr>
<td valign="top">

FORM

</td>
<td valign="top">

Trusted SAML 2.0 identity provider

If you need to configure the default options of an authentication method, or defineApplication-to-Application SSO

</td>
<td valign="top">

FORM authentication implemented over the Security Assertion Markup Language \(SAML\) 2.0 protocol. Authentication is delegated to SAP ID service or custom identity provider. You can specify the custom identity provider using the trust configuration for your subaccount. See [Application Identity Provider](application-identity-provider-dc61853.md#loiodc618538d97610148155d97dcd123c24).

\(Optional\) If you configure a connection with an on-premise user store, the existence of the user is also verified in the on-premise SAP NetWeaver AS Java system. See [Using an SAP System as an On-Premise User Store](using-an-sap-system-as-an-on-premise-user-store-71fdf1c.md).

</td>
<td valign="top">

You want to delegate authentication to your corporate identity provider.

</td>
</tr>
<tr>
<td valign="top">

BASIC

</td>
<td valign="top">

User name and password

</td>
<td valign="top">

HTTP BASIC authentication delegated to SAP ID servic, an on-premise SAP NetWeaver AS Java system or an Identity Authentication tenant. Web browsers prompt users to enter a user name and password.

By default, SAP ID service is used.

\(Optional\) You can use an on-premise SAP NetWeaver AS Java system instead of SAP ID service. You need to configure a connection with an on-premise user store to enable this scenario. See [Using an SAP System as an On-Premise User Store](using-an-sap-system-as-an-on-premise-user-store-71fdf1c.md).

\(Optional\) You can use your Identity Authentication tenant instead of SAP ID service.You need to configure the tenant in the *Basic Authentication* tab to enable this scenario. See [Basic Authentication](basic-authentication-a2c696b.md).

> ### Restriction:  
> BASIC authentication with a third-party corporate identity provider is **not** supported.

> ### Restriction:  
> The trust configuration \(*cloud cockpit* \> *Security* \> *Trust* \> *Application Identity Provider*\) you set for your subaccount does **not** apply for BASIC authentication.



</td>
<td valign="top">

Example 1: You want to delegate authentication to SAP ID service. Application users will log in with their SAP user name and password.

Example 2: You have a corporate on-premise SAP NetWeaver AS Java system. You want application users to log in using the user name and password stored in the corporate system.

Example 3: You have a corporate Identity Authentication tenant. You want application users to log in using the user name and password stored in the tenant.

</td>
</tr>
<tr>
<td valign="top">

CERT

</td>
<td valign="top">

Client certificate

</td>
<td valign="top">

Used for authentication only with client certificate. See [Enabling Client Certificate Authentication](enabling-client-certificate-authentication-0d7cf63.md).

</td>
<td valign="top">

Users log in using their corporate client certificates.

</td>
</tr>
<tr>
<td valign="top">

BASICCERT

</td>
<td valign="top">

User name and password

Client certificate

</td>
<td valign="top">

Used for authentication either with client certificate or with user name and password. See [Enabling Client Certificate Authentication](enabling-client-certificate-authentication-0d7cf63.md).

</td>
<td valign="top">

Within the corporate network, users log in using their client certificates. Outside that network, users log in using user name and password.

</td>
</tr>
<tr>
<td valign="top">

OAUTH

</td>
<td valign="top">

OAuth 2.0 token

</td>
<td valign="top">

Authentication according to the OAuth 2.0 protocol with an OAuth access token. See [OAuth 2.0 Authorization Code Grant](oauth-2-0-authorization-code-grant-b7b5893.md) 

> ### Restriction:  
> Using an external OAuth authorization server \(other than SAP BTP OAuth 2.0 service\) is not supported.



</td>
<td valign="top">

You have a mobile application consuming REST APIs using the OAuth 2.0 protocol. Users log in using an OAuth access token.

</td>
</tr>
<tr>
<td valign="top">

SAML2

</td>
<td valign="top">

Trusted SAML 2.0 identity provider

Application-to-Application SSO

</td>
<td valign="top">

See FORM.

</td>
<td valign="top">

See FORM.

</td>
</tr>
<tr>
<td valign="top">

OIDC

</td>
<td valign="top">

OpenID Connect provider

</td>
<td valign="top">

\(Beta\) Authentication based on the OpenID Connect \(OIDC\) protocol with an Identity Authentication tenant as OpenID Connect provider. Users will log in using credentials defined and verified by the Identity Authentication tenant \(by default, this is a user name and password pair stored in the tenant\).

Configure the OpenID Connect provider using the *OpenID Conect Authentication* section in the SAP BTP cockpit \(see [OpenID Connect Authentication](openid-connect-authentication-084c6fb.md)\).

</td>
<td valign="top">

Example 1: You want to delegate authentication to an Identity Authentication tenant.

Example 2: You want to use an Identity Authentication tenant as proxy to a third-party identity provider.

</td>
</tr>
</table>

[Authentication Configuration](authentication-configuration-4a46723.md)

> ### Tip:  
> Depending on your scenario, we recommend using one of the following authentication methods:.
> 
> -   `OAUTH`
> -   `FORM`
> -   `OIDC` \(Beta\)

> ### Note:  
> By default, any other method \(DIGEST, CLIENT-CERT, etc. or custom\) that you specify in the *web.xml* are executed as FORM. You can configure those methods using the *Authentication Configuration* section at Java application level in the Cockpit. See [Authentication Configuration](authentication-configuration-4a46723.md).

> ### Tip:  
> For the SAML and FORM authentication methods, if your application sends multiple simultaneous requests without an authenticated session, they may fail. We recommend that you first send one request to a protected resource, establish a session, and then use the session for the multiple simultaneous requests.

> ### Tip:  
> Although BASIC authentication is usually used for technical users to consume REST services \(stateless communication\) we recommend that the client leverages the security session instead of sending credentials with every call. This means the client needs to make sure it preserves and re-sends all HTTP cookies it receives. Thus, authentication will happen only once and this could improve performance.



## Results

-   When FORM authentication is used, you are redirected to SAP ID service or another identity provider, where you are authenticated with your user name and password. The servlet content is then displayed.
-   When BASIC authentication is used, you see a popup window and are prompted to enter your credentials. The servlet content is then displayed.



### Example

*Example 1: Using FORM Authentication*

The following example illustrates using FORM authentication. It requires all users to authenticate before accessing the protected resource. It does not, however, manage authorizations according to the user roles - it authorizes all authenticated users.

```
<login-config>
  <auth-method>FORM</auth-method>
</login-config>
<security-constraint>
  <web-resource-collection>
    <web-resource-name>Protected Area</web-resource-name>
    <url-pattern>/index.jsp</url-pattern>
    <url-pattern>/a2asso.jsp</url-pattern>
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

> ### Note:  
> All authenticated users implicitly have the Everyone role. You cannot remove or edit this role. In the SAP BTP Cockipt, the Everyone role is not listed in role mapping \(see [Managing Roles](managing-roles-db8175b.md) \).

*Example 2: Using FORM Authentication with Roles*

If you want to manage authorizations according to user roles, you should define the corresponding constraints in the *web.xml*. The following example defines a resource available for users with role Developer, and another resource for users with role Manager:

```
  <security-constraint>
    <web-resource-collection>
      <web-resource-name>Developer Page</web-resource-name>
      <url-pattern>/developer.jsp</url-pattern>
    </web-resource-collection>
    <auth-constraint>
      <role-name>Developer</role-name>
    </auth-constraint>
  </security-constraint>
  <security-constraint>
    <web-resource-collection>
      <web-resource-name>Manager Page</web-resource-name>
      <url-pattern>/manager.jsp</url-pattern>
    </web-resource-collection>
    <auth-constraint>
      <role-name>Manager</role-name>
    </auth-constraint>
  </security-constraint>
  <login-config>
    <auth-method>FORM</auth-method>
  </login-config>

```

> ### Remember:  
> If you define roles in the *web.xml*, you need to manage the role assignments of users after you deploy your application on SAP BTP. See [Managing Roles](managing-roles-db8175b.md)

<a name="loio778d8987e7714376977c190f6df379ad"/>

<!-- loio778d8987e7714376977c190f6df379ad -->

## Programmatic Authentication



## Context

With programmatic authentication, you do not need to declare constrained resources in the *web.xml* file of your application. Instead, you declare the resources as public, and you decide in the application logic when to trigger authentication. In this case, you have to invoke the authentication API explicitly before executing any application code that should be protected. You also need to check whether the user is already authenticated, and should not trigger authentication if the user is logged on, except for certain scenarios where explicit re-authentication is required.

If you trigger authentication in an SAP BTP application protected with FORM, the user is redirected to SAP ID service or custom identity provider for authentication, and is then returned to the original application that triggered authentication.

If you trigger authentication in an SAP BTP application protected with BASIC, the Web browser displays a popup window to the user, prompting him or her to provide a user name and password.

```

package hello;

import java.io.IOException;

import javax.security.auth.login.LoginContext;
import javax.security.auth.login.LoginException;
import javax.servlet.ServletException;
import javax.servlet.http.HttpServlet;
import javax.servlet.http.HttpServletRequest;
import javax.servlet.http.HttpServletResponse;

import com.sap.security.auth.login.LoginContextFactory;

public class HelloWorldServlet extends HttpServlet {
		
... 

  protected void doGet(HttpServletRequest request,
			HttpServletResponse response) throws ServletException, IOException {
    String user = request.getRemoteUser();
    if (user != null) {
      response.getWriter().println("Hello, " + user);
    } else {
      LoginContext loginContext;
      try {
        loginContext = LoginContextFactory.createLoginContext("FORM");
        loginContext.login();
        response.getWriter().println("Hello, " + request.getRemoteUser());

      } catch (LoginException e) {
        e.printStackTrace();
      }
    }
    ...
  }
  
  protected void doPost(HttpServletRequest request,
			HttpServletResponse response) throws ServletException, IOException {
    doGet(request, response);
  }
  ...
}

```

In the example above, you create *LoginContext* and call its `login()` method.

> ### Note:  
> All the steps below are described using the FORM authentication method, but they can also be applied to BASIC.



## Procedure

1.  Open the source code of your HelloWorldServlet class. Add the code for programmatic authentication to the `doGet()` method.

2.  Make the `doPost()` method invoke programmatic authentication. This is necessary because the SAP ID service always returns the SAML2 response over an HTTP POST binding, and in order to be processed correctly, the *LoginContext* login must be called during the `doPost()` method. The authentication framework is responsible for restoring the original request using GET after successful authentication. Another alternative is that your `doPost()` method simply calls your `doGet()` method.

3.  Test your application on the local server. It does not need to be connected to the SAP ID service, and authentication is done against local users. For more information, see Testing User Authentication on the Local Server.

4.  Deploy the application to SAP BTP. If you are using FORM, you are redirected to SAP ID service or another identity provider, depending on your trust configuration for this subaccount. If you are using BASIC, you are redirected to SAP ID service \(**not** configurable using trust settings\). The servlet content is then displayed and you should be able to see the content returned by the hello servlet.

    When BASIC authentication is used, you should see a popup window prompting you to provide credentials to authenticate. Once these are entered successfully, the servlet content is displayed.


<a name="loio6ad764f643bb401d8a50529afb1d17b3"/>

<!-- loio6ad764f643bb401d8a50529afb1d17b3 -->

## Handling Session Timeout





You can configure session timeout using the*web.xml*. Default value: 20 minutes. For example:

```
<session-config>
    <session-timeout>15</session-timeout> <!-- in minutes -->
  </session-config>

```

After the specified timeout, user sessions are invalidated. If the user tries to access an invalidated session, SAP BTP will return a login page in its response, so the user can enter credentials again. . If you are using SAML as login protocol, you cannot rely on the response code to find out the your session is expired because it will be 200 or 302. To check whether the response is for triggering new login, get the `com.sap.cloud.security.login` HTTP header, and reload the page. For example:

```
jQuery(document).ajaxComplete(function(e, jqXHR){
                if(jqXHR.getResponseHeader("com.sap.cloud.security.login")){
                                                alert("Session is expired, page shall be reloaded.");
                                                window.location.reload();
                }
}

```

> ### Note:  
> For requests made with the `X-Requested-With` header and value `XMLHttpRequest` \(AJAX requests\), you need to check for session expiration \(by checking the marker header `com.sap.cloud.security.login`\). If the session is expired and you are using SAML2 or FORM authentication method, the system does not trigger an authentication request.

<a name="loio4ac91c9b213e4b67bba550d02991b49e"/>

<!-- loio4ac91c9b213e4b67bba550d02991b49e -->

## Troubleshooting



Use the SAP Community, SAP Support Portal and Guided Answers or other related tools as described in [Getting Support, Neo Environment](../70-getting-support-neo/getting-support-neo-environment-fc2bf6a.md).

**Support Components**

Use the following components if you need to create a ticket for Authorization and Trust Management in the Neo environment:


<table>
<tr>
<th valign="top">

Suport Component

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

BC-NEO-SEC-IAM

</td>
<td valign="top">

Main support channel for tickets concerning Authorization and Trust Management in the Neo environment.

</td>
</tr>
<tr>
<td valign="top">

BC-NEO-SEC-CPG

</td>
<td valign="top">

Support for cryptographic services, including client certificate authentication and Keystore service.

</td>
</tr>
</table>

**Guided Answers**

Use the [Security in the Neo Environment](https://ga.support.sap.com/dtp/viewer/index.html#/tree/2065/actions/26547:26548:33705:33706) guided answers to locate the relevant solutions to problems or answers to questions.

**Local Testing**

When testing in the local scenario, and your application has `Web-ContextPath: /`, you might experience the following problem with Microsoft Internet Explorer:

After authentication you see:

> ### Output Code:  
> ```
> HTTP Status 405 - HTTP method POST is not supported by this URL
> ```



If you see such issues, you will have to add the following code into your protected resource:

```
@Override
protected void doPost(HttpServletRequest req, HttpServletResponse resp)
throws ServletException, IOException { doGet(req, resp); }
```



<a name="loio4ac91c9b213e4b67bba550d02991b49e__next"/>

## Next Steps

You can now test the application locally. See [Test Security Locally](test-security-locally-fe47e02.md).

After testing, you can proceed with deploying the application to SAP BTP. See [Deploying and Updating Java Applications](../30-development-neo/deploying-and-updating-java-applications-e5dfbc6.md).

After deploying on SAP BTP, you need to configure the role assignments users and groups will have for this application. See [Managing Roles](managing-roles-db8175b.md).

Optionally, you can configure the authentication options applied in the authentication method that you defined in the *web.xml* or programmatically. See [Authentication Configuration](authentication-configuration-4a46723.md).



<a name="loio4ac91c9b213e4b67bba550d02991b49e__example"/>

## Example

To see the end-to-end scenario of managing roles on SAP BTP, watch the complete video tutorial [Managing Roles in SAP BTP](http://youtu.be/KVLcVyz8GpM).

