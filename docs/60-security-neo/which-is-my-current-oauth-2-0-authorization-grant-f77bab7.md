<!-- loiof77bab79e2d24f488cd232466730e945 -->

# Which Is My Current OAuth 2.0 Authorization Grant?

Use this information if you're not sure which OAuth 2.0 authorization grant is in place.



The OAuth 2.0 authorization grants supported by OAuth 2.0 Service are:

-   *Client credentials*
-   *Authorization code*
-   *SAML bearer assertion*

For more information, see [Which OAuth 2.0 Authorization Grant Should I Use?](which-oauth-2-0-authorization-grant-should-i-use-f5a9246.md).



<a name="loiof77bab79e2d24f488cd232466730e945__section_pfv_pp1_rwb"/>

## OAuth 2.0 Communication Using Destinations

If you are authenticating to an OAuth-protected resource through a destination, the grant type that you are using can be either OAuth 2.0 *client credentials* or OAuth 2.0 *SAML bearer*. Which one of these you are using can be easily determined by the authentication type of the destination. This can be checked the following way:

1.  In your Web browser, log on the BTP cockpit, and select the subaccount where the destination is created.

2.  Locate the destination.

    If it's on subscription level: go to *Applications* \> *Subscriptions* section, and select the subscription that you are using. After that, click on the *Destinations* section and the destination you are using.

    If it's on application level: go to *Applications* \> *Java Applications*, and select the application that you are using. After that click on *Configuration* \> *Destinations*, and select the destination you are using.

    If it's on subaccount level: go to *Connectivity* \> *Destinations*, and select the destination you are using.

3.  The grant type corresponds to the authentication type \(the *Authentication* field\) of the destination - *OAuth2ClientCredentials* shows you are using *client credentials*, and *OAuth2SAMLBearerAssertion* shows *SAML bearer assertion* respectively.




<a name="loiof77bab79e2d24f488cd232466730e945__section_xz5_zrn_twb"/>

## How to Identify Authorization Code Grant

The only way to use an *authorization code* grant is to configure an OAuth 2.0 application client with *Authorization Grant* equal to *Authorization Code*. You can check it in the following way:

1.  In your Web browser, log on to the BTP cockpit , and select the subaccount where the OAuth client is created.
2.  In the *Security* \> *OAuth* section, go to the *Clients* tab.
3.  Find the client you are using based on *Name*, *Client Id*, *Description*, and so on.
4.  Click on it to inspect its information and check the value *Authorization Grant* field.
    -   If it is *Authorization Code*, you are using the *authorization code* grant.
    -   If it is *Client Credentials*, you are using either *client credentials* or *SAML bearer assertion* grant.


There are cases when you do not have access to the subaccount containing the client, but only to *client id* and the *source code* with the implementation of authentication to OAuth 2.0-protected resource. In these cases, you can check the token issuing request and determine the authorization grant by the query parameters that they are sending. If the query parameter with name `grant_type` is equal to `code`, then the *authorization code* grant is used.

> ### Note:  
> The query parameter with name `grant_type` can be sent as part of the request body as well.



<a name="loiof77bab79e2d24f488cd232466730e945__section_zng_zp1_rwb"/>

## How to Identify Client Credentials or SAML Bearer Assertion

The OAuth 2.0 *client credentials* and the *SAML bearer assertion* grant can be identified by following the steps for *authorization code*.

To determine which one of the two grants is used for the given client, examine the destinations in the subaccount. The OAuth 2.0 *SAML bearer assertion* grant is generally used through destinations. See [Simplifying OAuth 2.0 Authentication with Destinations](simplifying-oauth-2-0-authentication-with-destinations-c8b8c06.md).

If you cannot find a destination using the given client, this generally means that the OAuth 2.0 *client credentials* grant type is used, since OAuth 2.0 *SAML bearer assertion* grant usage is more widespread in the form of destination consumption. Nevertheless, to be sure, the token issuing source code must be examined. The authorization grant can be determined based on the value of the query parameter with name `grant_type` \(it may be sent as part of the request body as well\).

