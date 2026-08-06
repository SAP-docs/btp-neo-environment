<!-- loiof5eac83ceb4d4d72b64424f518f878fd -->

# Revoke OAuth Access Tokens

With revoking access tokens, you can immediately reject access rights you have previously granted. You may wish to revoke an access token if you believe the token is be stolen, for example.

> ### Caution:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/docs/btp/sap-business-technology-platform/sap-business-technology-platform?version=Cloud) .**

> ### Tip:  
> Additional IP outbound addresses will soon be used in all regions in the Neo environment. For more information, see [Additional IP Addresses Added to SAP BTP, Neo Runtime Regions](https://help.sap.com/whats-new/cf0cb2cb149647329b5d02aa96303f56?version=Cloud&Component=Region&Valid_as_Of=2026-11-02:2026-11-02). To subscribe to such notifications, see SAP Note [3513325](https://me.sap.com/notes/3513325).

> ### Restriction:  
> You can revoke only the default persistent type of accesss tokes. If you use JWT tokens as access tokens, you cannot revoke them as they are not stored persistently. See [Best Practices for Resilient OAuth 2.0 Communication](best-practices-for-resilient-oauth-2-0-communication-11fe332.md).

There are two UIs for revoking access tokens:

-   The Cockpit - an administrator user may use the Cockpit to revoke tokens on behalf of different end users
-   The end user UI - an end user may access its tokens \(and no other user's\) and revoke the required using that UI

Using the Cockpit \(for administrators\):

1.  In your Web browser, open the Cockpit.
2.  Go to the *Security* \> *Authorizations* \> *Token* section.
3.  Search for access tokens either by client ID or by user ID.
4.  Choose *Revoke* for the required tokens.

![](images/Tokens_tab_8bc06d3.png)

Using the End User UI:

1.  In the Cockpit, choose the *Security* \> *OAuth* section, and go to the *Branding* tab.
2.  Click the *End User UI* link.You are now opening the end user UI in a new browser window. You can see all access tokens issued for the current user.
3.  Choose the *Revoke* button for the tokens to revoke.

![](images/Tokens_End_User_UI_9b38434.png)

