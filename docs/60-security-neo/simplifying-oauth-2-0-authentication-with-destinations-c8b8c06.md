<!-- loioc8b8c06244864c328c84940ee1ffb1f3 -->

# Simplifying OAuth 2.0 Authentication with Destinations

You can simplify the OAuth 2.0 authentication process by using destinations. They provide automation, flexibility and reusable configuration suited for your scenario. In addition, you automatically benefit from the updates and upgrades in the Destination API library.



Destinations are provided by SAP BTP Connectivity Service. They are the recommended approach to handle connectivity within SAP BTP. They are applicable to your OAuth scenario if you are using the OAuth 2.0 *client credentials* or *SAML bearer assertion* grant to access protected resources.



The Destination APIs relevant for OAuth 2.0 authentication in the Neo environment are the [HttpDestination API](https://help.sap.com/docs/CP_CONNECTIVITY/b865ed651e414196b39f8922db2122c7/462dbffef4614044b5c727c9de37672e.html?version=Cloud&locale=en-US) and [AuthenticationHeaderProvider API](https://help.sap.com/docs/CP_CONNECTIVITY/b865ed651e414196b39f8922db2122c7/df6c1ffd39f0451594d737cf7638ce00.html?version=Cloud&locale=en-US).

Both APIs cache issued access tokens and automatically reuse them. In addition, they automatically renew the cached access token before it expires. This improves the responsiveness of the OAuth Service, and eliminates the need for writing custom source code for reusing tokens.


<table>
<tr>
<th valign="top">

Scenario

</th>
<th valign="top">

Use Connectivity API

</th>
<th valign="top">

Details

</th>
</tr>
<tr>
<td valign="top">

Client credentials

</td>
<td valign="top">

HttpDestination API

AuthenticationHeaderProvider API

</td>
<td valign="top">

If you use the HttpDestination API, a token is automatically issued based on the destination configuration when accessing protected resources.

If you use the AuthenticationHeaderProvider API, you need to generate client credentials headers and insert them in your request. See [Generate Client Credentials Headers](https://help.sap.com/docs/CP_CONNECTIVITY/b865ed651e414196b39f8922db2122c7/df6c1ffd39f0451594d737cf7638ce00.html?version=Cloud&locale=en-US).

</td>
</tr>
<tr>
<td valign="top">

SAML bearer assertion

</td>
<td valign="top">

AuthenticationHeaderProvider API

</td>
<td valign="top">

Generates OAuth authorization headers. See [Generate OAuth2SAMLBearerAssertion Headers](https://help.sap.com/docs/CP_CONNECTIVITY/b865ed651e414196b39f8922db2122c7/df6c1ffd39f0451594d737cf7638ce00.html?version=Cloud&locale=en-US)

</td>
</tr>
</table>

> ### Tip:  
> For even higher availability, we recommend using tokens in JWT format. See [OAuth 2.0 JWT Token Types](oauth-2-0-jwt-token-types-3f26e04.md).

See also:

-   [Periodic Token-Based Operations](periodic-token-based-operations-ead7249.md)
-   [Using OAuth 2.0 Authorization at Irregular Intervals](using-oauth-2-0-authorization-at-irregular-intervals-7263696.md)

