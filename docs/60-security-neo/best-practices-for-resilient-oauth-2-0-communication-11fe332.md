<!-- loio11fe332c05cb4d5fa9f752736f6b7575 -->

# Best Practices for Resilient OAuth 2.0 Communication

Use the following best practices to build resilient OAuth 2.0 communication.



<a name="loio11fe332c05cb4d5fa9f752736f6b7575__section_gv2_nzm_3qb"/>

## Key Points

-   Tokens can always be issued.
-   Persistent tokens cannot be validated in rare cases \(for example, DB outage and LRU cache miss\). In this case 401 would be returned.
-   JWT tokens can always be validated.



<a name="loio11fe332c05cb4d5fa9f752736f6b7575__section_fpm_nzm_3qb"/>

## JWT Tokens

An OAuth 2.0 Client can request one of the following two types of access tokens: persistent \(stored in the system database \(default situation\)\) or JWT \(on-demand\).

Using JWT tokens enables faster and more robust token validation than using the default persistent tokens. Hence, we recommend that JWT tokens are used whenever possible \(see some constraints below\).

They can be issued for the as access token for both Client Credentials Flow and Authorization Code Flow. Refresh tokens are always persistent.



<a name="loio11fe332c05cb4d5fa9f752736f6b7575__section_qh3_rzm_3qb"/>

## Requesting JWT Tokens

Append the following query parameter to the token request:

`“token_format=jwt”`

Note: For some Platform APIs, JWT tokens are used by default and cannot be switched off.



<a name="loio11fe332c05cb4d5fa9f752736f6b7575__section_upr_5zm_3qb"/>

## JWT Token Constraints

-   Their validity is maximum 12 hours or less. If you need a longer token validity, use the default persistent tokens.
-   They cannot be listed in the OAuth End User UI or the Cockpit, since they aren’t persisted/stored by the OAuth 2.0 Service.
-   They cannot be revoked.
-   Regardless of the expiration configuration of the OAuth client, if a JWT token is requested, the validity will be 12h or less.
-   Their size is in the 2-3kb range, compared to <40 bytes for the default persistent tokens



<a name="loio11fe332c05cb4d5fa9f752736f6b7575__section_gdp_zzm_3qb"/>

## Best Practices for Resilient OAuth Communication

-   Use JWT tokens whenever possible. Use persistent tokens only in the very limited cases when JWT tokens are not applicable.
-   Do not rely on the expiration time configured in the OAuth client. It is rather a hint to the OAuth server.

    The OAuth server may expire tokens earlier in critical situations or validation may be temporarily unavailable. Token issuing is always possible. So in case of a 401, implement a retry with issuing a new access token.

-   Ensure that the token used is valid at least a certain amount of time, for example, 1 hour. This will ensure that even if there is some temporary outage, the OAuth client will have a valid token during the outage.
    -   This can be achieved by requesting a new token at least 1 hour before the old one is expired. In case the token is successfully retrieved it can be used directly. And in case the OAuth 2.0 Service is unavailable, the old one can still be used.
    -   JWT tokens can be validated even if the OAuth 2.0 Service is down or not responding
    -   JWT and persistent tokens can always be issued.

-   Retry calls for issuing tokens
    -   HTTP protocol is unreliable and a call can fail for a multitude of reasons before it does HTTP Response is received
    -   Some short delay between calls is always reasonable.

-   Reuse tokens instead of issuing a new one every time.

