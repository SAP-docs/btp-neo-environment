<!-- loioc9546f46c5a842b5873c48e49598e3b3 -->

# Create Outbound OAuth Configuration in SAP SuccessFactors



<a name="loioc9546f46c5a842b5873c48e49598e3b3__prereq_spt_nly_kcb"/>

## Prerequisites

You have an OAuth client in SAP BTP created. See [Create OAuth Client in SAP BTP](create-oauth-client-in-sap-btp-67f43e2.md).



## Context

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/docs/btp/sap-business-technology-platform/sap-business-technology-platform?version=Cloud) .**

Based on the OAuth client, you have to create an outbound OAuth configuration in the SAP SuccessFactors system.



## Procedure

1.  Log on to the SAP SuccessFactors system, and go to the *Integration Center*.

2.  In the *Integration Center*, choose the *Security Center* tile and then choose the *Outbound OAuth Configurations*.

3.  Choose *Add* to create a new outbound OAuth configuration.

4.  In the *Configuration Name* field, enter a name for this outbound OAuth configuration.

5.  In the *OAuth Type* drop-down menu, select *OAuth 2.0*.

6.  In the *Grant Type* drop-down menu, select *Client\_Credentials*.

7.  In the *Client ID* field, paste the value of the *ID* field of the OAuth client that you have created in the SAP BTP cockpit.

8.  In the *Client Secret* field, enter the value of the *Secret* field of the OAuth client that you have created in the SAP BTP cockpit.

9.  In the *Token URL* field, paste the value of the Token URL from the *Token Endpoint* field in the *Security* \> *OAuth* \> *Branding* \> *OAuth URLs*.

10. In the *Token Method* field, select *POST*.

11. Choose *Save*.


