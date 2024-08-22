<!-- loio67f43e2f9afb4dffb56c9ce35b4e6169 -->

# Create OAuth Client in SAP BTP



## Context

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of the following technology portfolios: application development; process automation; integration; data, analytics, and enterprise planning; artificial intelligence. The platform offers users the ability to turn data into business value, compose end-to-end business processes, connect entire IT landscapes, and personalize, build and extend SAP applications. This reduces the overall total cost of ownership maintaining SAP landscapes and third-party software across end-to-end business processes.") :arrow_upper_right:.**

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


