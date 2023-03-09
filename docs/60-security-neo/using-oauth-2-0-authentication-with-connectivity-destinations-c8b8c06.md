<!-- loioc8b8c06244864c328c84940ee1ffb1f3 -->

# Using OAuth 2.0 Authentication with Connectivity Destinations

The OAuth 2.0 Authentication process can be simplified by using connectivity destinations. These destinations provide additional flexibility and can be configured to suit your needs.



<a name="loioc8b8c06244864c328c84940ee1ffb1f3__section_gwt_rb1_rwb"/>

## Context

You are using the OAuth 2.0 Client Credentials grant or OAuth 2.0 SAML Bearer grant to access protected resources and would like to start using connectivity destination libraries.

The OAuth 2.0 Authentication process can be simplified by using connectivity destinations. These destinations provide additional flexibility and can be configured to suit your needs. Additionally, any future improvements to the destination library in terms of resilience will be automatically available with a version number increase. However, they should not be used if they do not provide the necessary resiliency for your case.



<a name="loioc8b8c06244864c328c84940ee1ffb1f3__section_fhp_5b1_rwb"/>

## Procedure

The Connectivity Destination library has two APIs that are relevant for OAuth 2.0 authentication in the Neo environment: `HttpDestination API` and `AuthenticationHeaderProvider API`.

The HttpDestination API automatically issues tokens based on the destination configuration when accessing protected resources with OAuth 2.0 Client Credentials grant.

In case the resource is protected with OAuth 2.0 SAML Bearer grant, the AuthenticationHeaderProvider API must be used. For detailed information about the AuthenticationHeaderProvider API see AuthenticationHeaderProvider API. This API can be used to generate OAuth Authorization Headers. To do this, please refer to the examples provided in the documentation: Generate Client Credentials Headers for Client Credentials and Generate OAuth2SAMLBearerAssertion Headers for OAuth 2.0 SAML Bearer grant headers.

The two APIs provided by the destination libraries to cache issued access tokens and automatically reuse them. The destination libraries additionally automatically renew the cached access token before it expires without any additional steps. This protects customers from potential degradations in the responsiveness of the OAuth Service and eliminates the need for writing custom source code for reusing tokens.

For even higher availability, SAP recommends the usage of tokens in JWT format. See [OAuth 2.0 JWT Token Types](oauth-2-0-jwt-token-types-3f26e04.md).

For special scenarios that require higher availability and decoupling from degradations in the resilience of the OAuth server, customers should refer to the customer scenarios section for the best approach to using the OAuth 2.0 Authentication on a case-by-case basis. Additionally, customers can combine the usage of the AuthenticationHeaderProvider API with the techniques described in the customer scenarios section.

See:

-   [Periodic Token-Based Operations](periodic-token-based-operations-ead7249.md)
-   [Using OAuth 2.0 Authorization at Irregular Intervals](using-oauth-2-0-authorization-at-irregular-intervals-7263696.md)

