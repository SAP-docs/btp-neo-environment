<!-- loio2f76c6cfade04d8a954bdcc15313bfcb -->

# Achieving Resilient OAuth 2.0 Authorization

Increase the resilience and fault tolerance to sporadic degradations in the responsiveness of the OAuth Service.

> ### Caution:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/docs/btp/sap-business-technology-platform/sap-business-technology-platform?version=Cloud) .**

> ### Tip:  
> Additional IP outbound addresses will soon be used in all regions in the Neo environment. For more information, see [Additional IP Addresses Added to SAP BTP, Neo Runtime Regions](https://help.sap.com/whats-new/cf0cb2cb149647329b5d02aa96303f56?version=Cloud&Component=Region&Valid_as_Of=2026-11-02:2026-11-02). To subscribe to such notifications, see SAP Note [3513325](https://me.sap.com/notes/3513325).



<a name="loio2f76c6cfade04d8a954bdcc15313bfcb__section_bc4_w11_rwb"/>

## The Problem

Customers who are not following the guidelines laid down below are more likely to experience general slowdown or difficulty consuming their OAuth 2.0 protected resources during periods of degradation in the resilience of the OAuth Service. Several techniques can be used to mitigate this risk and bring it to a minimum.



<a name="loio2f76c6cfade04d8a954bdcc15313bfcb__section_mv4_y11_rwb"/>

## Guidelines

-   Reuse OAuth 2.0 access tokens instead of creating new ones for each request. This also reduces the chance of token issuing failures and customer requests being slowed down by the OAuth's rate limiter. By reusing tokens, network bandwidth and OAuth resources are conserved, which increases the system's resilience. Additionally, the more a singular token is used, the more likely it is to be successfully verified even during temporary degradations of the OAuth Service. This is thanks to the caching mechanism implemented by the OAuth Service.

-   Use access tokens with validity as short as possible. Access tokens with long validity expose its users to security risks in case they leak and subsequently are used by malicious actors. To avoid that, we recommend using tokens in JWT format, which have a maximum validity of 12 hours.

-   In the event of token issuing failures, it is recommended to implement a token issuing retry mechanism. This is due to the unreliability of the HTTP protocol, which can cause calls to fail before receiving an HTTP response for various reasons. It is advised to limit the number of retry attempts for access token issuing to only 1 or 2 to avoid the possibility of having your requests slowed down by the OAuth Service’s rate limiter.


> ### Note:  
> The expiration time configured for the OAuth 2.0 client should not be relied upon as always true. This is merely a hint to the OAuth server and the SAP BTP Neo OAuth Service might prematurely expire tokens under certain circumstances. If this happens, HTTP 401 error will be returned. It is recommended that in such cases a new access token is issued and used for authorization.

The following OAuth 2.0 Scenario documents provide guidance on when you should issue a new token while reusing it. It is recommended to request a new token some time before the previous one expires. This will ensure that even if there is some temporary responsiveness degradation in the OAuth Service, the OAuth client will have a valid token to use during the brief downtime.

See:

[Using OAuth 2.0 Authorization at Irregular Intervals](using-oauth-2-0-authorization-at-irregular-intervals-7263696.md)

[Periodic Token-Based Operations](periodic-token-based-operations-ead7249.md)

