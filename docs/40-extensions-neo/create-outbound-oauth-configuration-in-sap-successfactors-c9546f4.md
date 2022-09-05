<!-- loioc9546f46c5a842b5873c48e49598e3b3 -->

# Create Outbound OAuth Configuration in SAP SuccessFactors



<a name="loioc9546f46c5a842b5873c48e49598e3b3__prereq_spt_nly_kcb"/>

## Prerequisites

You have an OAuth client in SAP BTP created. See [Create OAuth Client in SAP BTP](create-oauth-client-in-sap-btp-67f43e2.md).



## Context

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**

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


