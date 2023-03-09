<!-- loiof5a92468ed204f0cb7a68e8ac2c0b67f -->

# Which OAuth 2.0 Authorization Grant Should I Use?

This document will provide you with information on which OAuth 2.0 authorization grant to use depending on your specific use case, the differences between them and guidance on when to use each one. For more detailed information the OAuth 2.0, see RFC6749.



<a name="loiof5a92468ed204f0cb7a68e8ac2c0b67f__section_ecb_cbb_rwb"/>

## OAuth 2.0 Client Credentials Grant

OAuth 2.0 Client Credentials is a type of authorization grant used to allow a client to access protected resources on its own behalf, rather than on behalf of a user. Where the accessed resources must be under the control of the client. In SAP BTP, Neo environment, an OAuth application client represents a single application, while an OAuth platform client represents a single sub-account management entity.

OAuth application clients are commonly used for server-to-server communication, where one or both of the parties share their credentials and communicate among each other without any intermediaries, where the calling party might be deployed outside of SAP BTP Neo environment.

On the other hand, OAuth platform clients are used to access protected resources under their control, such as the platform defined APIs. For more information, see [Using Platform APIs](../30-development-neo/using-platform-apis-392af9d.md).

For more information how to setup this grant type, see [OAuth 2.0 Client Credentials Grant](oauth-2-0-client-credentials-grant-f69fa87.md).



<a name="loiof5a92468ed204f0cb7a68e8ac2c0b67f__section_wyk_fbb_rwb"/>

## OAuth SAML 2.0 Bearer Assertion Grant

The OAuth SAML 2.0 Bearer Assertion is a type of authorization grant that utilizes an existing trust relationship without a direct user approval step at the authorization server. In comparison to OAuth 2.0 Client Credentials grant, the OAuth client acts on behalf of a user.

> ### Note:  
> SAP BTP, Neo environment does not support the usage of SAML 2.0 Bearer Assertions for client authentication.

OAuth SAML 2.0 Bearer Assertion grant is appropriate to be used when a client wants to access a protected resource on behalf of a user without an approval step at the authorization server.

Other common use cases for OAuth SAML 2.0 Bearer Assertion grant are:

-   Client needs to access a resource with user-based roles authorization.
-   Client needs to access a resource without the need for a user to give his consent explicitly.
-   Single sign-on cannot be achieved on approval step due to differences in authentication methods.
-   Principal propagation between two trusted entities where the calling entity might be deployed outside of SAP BTP, Neo environment. For more information, see [Principal Propagation to OAuth-Protected Applications](principal-propagation-to-oauth-protected-applications-310f39e.md).

To increase the resilience of the client \(the caller entity\) and the resource provider \(the called entity\), we recommend the usage of tokens in JWT format. For more information, see [OAuth 2.0 JWT Token Types](oauth-2-0-jwt-token-types-3f26e04.md).



<a name="loiof5a92468ed204f0cb7a68e8ac2c0b67f__section_tph_qbb_rwb"/>

## OAuth 2.0 Authorization Code Grant

The OAuth 2.0 Authorization Code is an authorization grant used to grant permission for a client application to access a protected resource on behalf of a user. With this method, the user must approve the requested access scope, which specifies what types of information the client application will be able to access. This helps ensure that user data is protected, and that access is only granted when necessary.

The OAuth 2.0 Authorization Code grant is primarily used when a client application needs to access a protected resource on behalf of a user even after the user is no longer present. This is achieved through a refresh token, which allows the client application to obtain a new access token without requiring the user to reauthorize the application. This provides a more seamless and secure user experience, as users do not need to constantly re-authorize the application each time they use it. In other cases, you should consider the usage of OAuth SAML 2.0 Bearer Assertion grant.

> ### Note:  
> When a new access token is requested, the previously issued refresh token will no longer be valid and cannot be used again. This follows the guidelines set forth in the OAuth 2.0 specification and should be considered when relying on refresh tokens for access to protected resources. It is important to plan accordingly and ensure that your application can handle the expiration of refresh tokens in a secure and efficient manner.

For more information, see [OAuth 2.0 Authorization Code Grant](oauth-2-0-authorization-code-grant-b7b5893.md).

