<!-- loio3f26e04c9c2b49fca2592dc28e74e996 -->

# OAuth 2.0 JWT Token Types

OAuth 2.0 tokens in JWT format provide a secure way to access data and services and offer the benefit of increased resilience.



<a name="loio3f26e04c9c2b49fca2592dc28e74e996__section_ws2_xyb_rwb"/>

## Tokens in JWT Format in OAuth 2.0 on SAP BTP

An OAuth 2.0 Client can request one of the following two types of access tokens: opaque \(default type, which requires communication between the application server and the OAuth Service for verification\) or JWT \(self-contained\). When using JWT tokens, the need for the application to call the OAuth Service for token verification is eliminated as the tokens are self-contained and can be validated by the runtime. This approach decouples the application from the OAuth Service, improving its robustness and resilience. It is worth noting that the runtime handles the verification process automatically, and customers do not need to worry about the technical details regarding token verification.

> ### Note:  
> It is not recommended to protect applications with SAP BTP Neo OAuth Service outside of SAP BTP, Neo environment, due to specifics that must be taken into consideration during token verification.

Currently, JWT Token format is supported for:

-   OAuth 2.0 Client Credentials Authorization Grant
-   OAuth SAML 2.0 Bearer Assertion Authorization Grant.

Using tokens in JWT format enables faster and more robust token validation than using the default opaque tokens. Hence, we recommend that tokens in JWT format are used whenever possible \(see some constraints below\).



<a name="loio3f26e04c9c2b49fca2592dc28e74e996__section_e4s_3zb_rwb"/>

## Requesting JWT Tokens

By default, the OAuth Service issues tokens in opaque format. To request a token in JWT format, an additional parameter should be given either as part of the request body or the query path. The name and the value of the parameter are:

```
token_format=jwtrfc
```

> ### Note:  
> A use case into which you might want to provide the necessary parameter as part of the query path is when you are using a destination \(or alternative configuration\) and you cannot change the source code, or you want to try out the feature with the least changes.

> ### Note:  
> The token format query parameter can also have the following value:
> 
> ```
> token_format=jwt
> ```
> 
> We recommend using value `jwtrfc`.

> ### Note:  
> If you are using OAuth client for a platform API, you do not need to take any action. For some platform APIs, tokens in JWT format are always issued by default and opaque tokens cannot be used. In case you are observing that the token issued for a Platform API Client is in opaque format, that means the given Platform API does not support the usage of JWT Token format yet. If you encounter problems using Platform APIs with JWT Token format, create an incident in the component for that service. See [Getting Support, Neo Environment](../70-getting-support-neo/getting-support-neo-environment-fc2bf6a.md).

> ### Note:  
> Tokens in JWT format are typically more than 40 bytes and do not have fixed length. Due to that, customers should not do any length checks on the token issuing responses.



<a name="loio3f26e04c9c2b49fca2592dc28e74e996__section_mw5_f1c_rwb"/>

## JWT Token Benefits

JWT Tokens can be validated regardless of the OAuth Service availability for most cases. Despite that, there are some exceedingly rare situations where the token verification will fail.

-   JWT Token issuing operations, in comparison to other operations, have a higher chance of being successfully processed during degradations in the responsiveness of the OAuth Service. That is because they are being handled with bigger priority.
-   JWT token issuing requests have higher thresholds for rate limiting and are less likely to be throttled as they take up less resources of the OAuth Service.
-   JWT Token issuing requests are faster as they do not require persistence into data storage.
-   Their short validity lowers the risk of leaked tokens for an extended period of time.



<a name="loio3f26e04c9c2b49fca2592dc28e74e996__section_ztj_k1c_rwb"/>

## JWT Token Constraints

-   Their validity is capped at 12 hours. If you need a longer token validity, please reexamine your scenario, and consider alternatives, or as a last resort use the default opaque tokens.
-   Since JWT tokens are not stored by the OAuth Service, they cannot be listed or revoked from the End User UI or the BTP Cockpit.

**Related Information**  


[RFC 7519: JSON Web Token \(JWT\)](https://datatracker.ietf.org/doc/rfc7519/)

