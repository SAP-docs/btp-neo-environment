<!-- loiof69fa8762d2a44aab2a22ea7214fb3ff -->

# OAuth 2.0 Client Credentials Grant

Use OAuth 2.0 service in the Neo environment of SAP BTP to enable your cloud applications for client credentials grant flow.



## Context

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/docs/btp/sap-business-technology-platform/sap-business-technology-platform?version=Cloud) .**

Client credentials grant is one of the basic flows specified in the OAuth 2.0 protocol. It enables grant of an OAuth access token based on the client credentials only, without user interaction. You can use this flow for enabling system-to-system communication \(with a service user\), for example, in device communication in an Internet of things scenario.

> ### Note:  
> OAuth service supports sending client credentials in HTTP header Authorization BASIC. Sending client credentials in the body of HTTP request is **not** supported.



## Procedure

1.  Register a new OAuth client of type *Confidential*. See [Register an OAuth Client](register-an-oauth-client-61d8095.md).

2.  Using that client, you can get an access token using a REST call to the endpoints shown in *cockpit* \> *Security* \> *OAuth* \> *Branding*.

    Create a REST call containing `grant_type: client_credentials`, client ID and password.

    See the [OAuth 2.0 client credentials grant specification](https://tools.ietf.org/html/rfc6749#section-4.4).

    The HTTP response contains the access token.

3.  In the SAP BTP application:

    -   Protect your application declaratively with the OAuth login method in the `web.xml`. See [OAuth 2.0 Authorization Code Grant](oauth-2-0-authorization-code-grant-b7b5893.md).
    -   Use the `getRemoteUser()` method of the HTTP request \(`javax.servlet.http.HttpServletRequest`\) to get the **client ID**.

        The `getRemoteUser()` method returns the client ID prefixed by `oauth_client_` as follows:

        `oauth_client_<client ID>`

        > ### Tip:  
        > You can use the client ID returned as remote user to assign Java EE roles to clients, and use them for role-based authorizations. See:
        > 
        > -   [Managing Roles](managing-roles-db8175b.md)
        > 
        > -   [Authorizations](authorizations-85a19f0.md)

        > ### Caution:  
        > Having multiple clients with the same case-sensitive name will lead to having the same user ID at runtime. This could lead to incorrect user role assignments and authorizations.



