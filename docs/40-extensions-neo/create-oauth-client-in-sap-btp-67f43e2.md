<!-- loio67f43e2f9afb4dffb56c9ce35b4e6169 -->

# Create OAuth Client in SAP BTP



## Context

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/docs/btp/sap-business-technology-platform/sap-business-technology-platform?version=Cloud) .**

You have to create an OAuth client in SAP BTP with ID and secret. Later on, you will add these client ID and secret when creating the outbound OAuth configuration in SAP SuccessFactors system.



## Procedure

1.  Go to the SAP BTP cockpit and open the extension subaccount.

2.  Choose *Security* \> *OAuth*. Choose the *Clients* tab.

3.  Choose *Register New Client*. The ID is automatically generated.

4.  Enter a name for the client, for example, `intsvcOAuthClient`.

5.  In the *Subscription* field, select the extension application that you want to be notified.

6.  In the *Authorization Grant* field, select *Client Credentials*.

7.  In the *Secret* field, define a password of your choice.

8.  Choose *Save*.


