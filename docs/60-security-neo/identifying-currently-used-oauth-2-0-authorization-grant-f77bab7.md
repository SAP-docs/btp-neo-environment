<!-- loiof77bab79e2d24f488cd232466730e945 -->

# Identifying Currently Used OAuth 2.0 Authorization Grant

Use this information when you are not sure which OAuth 2.0 authorization grant is currently being used.



The currently supported OAuth 2.0 authorization grants are:

Client Credentials grant

Authorization code grant

SAML Bearer Assertion grant

For detailed information about their use cases see OAuth 2.0 Authorization grants use cases.



<a name="loiof77bab79e2d24f488cd232466730e945__section_pfv_pp1_rwb"/>

## OAuth 2.0 Communication Using Destinations

In case you are authenticating to an OAuth-protected resource through a destination, the grant type that you are using can be either OAuth 2.0 Client Credentials grant or OAuth 2.0 SAML Bearer grant. Which one of these you are using can be easily determined by the authentication type of the destination. This can be checked the following way:

1.  In your Web browser, log on to the BTP cockpit, and select the subaccount where the destination is created.

2.  In case the destination is in subscription context: go to *Applications Subscriptions* section and select the subscription that you are using. After that, click on the *Destinations* section and the destination you are using.

3.  In case the destination is not in subscription context: go to *Connectivity Destinations* section and click on the destination that you are using.

4.  The Authorization Grant can be determined based on the authentication type of the used destination. In case the Authentication field is equal to “OAuth2ClientCredentials” then you are using the OAuth 2.0 Client Credentials grant. In case the Authentication field is OAuth2SAMLBearerAssertion, then you are using the OAuth 2.0 SAML Bearer Assertion grant.




<a name="loiof77bab79e2d24f488cd232466730e945__section_zng_zp1_rwb"/>

## How to Identify Client Credentials Grant or OAuth 2.0 SAML Bearer Grant

The OAuth 2.0 Client Credentials and the OAuth 2.0 SAML Bearer grant can be identified by following the steps in “How to identify Authorization code grant” up to step 6 – there the “Authorization Grant” field should be equal to “Client Credentials”.

To determine which one of the two possible grants is used for the given client, the destinations in the subaccount need to be examined. The OAuth 2.0 SAML Bearer grant is generally used through destinations. See the section OAuth 2.0 Communication through destinations in order to determine which one of the two grants is used, in case OAuth 2.0 Authorization in your scenario is done using with destinations.

In case you cannot find a destination using the given client, this generally means that the OAuth 2.0 Client Credentials grant type is used, since OAuth 2.0 SAML Bearer grant usage is more widespread in the form of destination consumption. Nevertheless, in order to be sure, the token issuing source code must be examined. The authorization grant can be determined based on the value of the query parameter with name “grant\_type”.

