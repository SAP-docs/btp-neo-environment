<!-- loio2fcdea4c0bb14987b8893e8877bf1508 -->

# Create Outbound OAuth Configuration in SAP SuccessFactors



<a name="loio2fcdea4c0bb14987b8893e8877bf1508__prereq_spt_nly_kcb"/>

## Prerequisites

-   You have an OAuth client in SAP BTP created. See [Create OAuth Client in SAP BTP](create-oauth-client-in-sap-btp-67f43e2.md).

-   You have created an OAuth X509 key and have saved the X509 certificate on your local file system. See [Generate OAuth X509 Key in SAP SuccessFactors](generate-oauth-x509-key-in-sap-successfactors-f636503.md).

-   You have registered the X509 certificate when creating a trusted identity provider in the SAP BTP cockpit. See [Create Trusted Identity Provider in SAP BTP Cockpit](create-trusted-identity-provider-in-sap-btp-cockpit-83e5ad2.md).




## Context

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/docs/btp/sap-business-technology-platform/sap-business-technology-platform?version=Cloud) .**

Based on the X509 certificate and OAuth client, you have to create an outbound OAuth configuration in the SAP SuccessFactors system.



## Procedure

1.  Log on to the SAP SuccessFactors system, and go to the *Integration Center*.

2.  In the *Integration Center*, choose the *Security Center* tile and then choose the *Outbound OAuth Configurations*.

3.  Choose *Add* to create a new outbound OAuth configuration.

4.  In the *Configuration Name* field, enter a name for this outbound OAuth configuration.

5.  In the *Client ID* field, paste the value of the *ID* field of the OAuth client that you have created in the SAP BTP cockpit.

6.  In the *Client Secret* field, enter the value of the *Secret* field of the OAuth client that you have created in the SAP BTP cockpit.

7.  In the *OAuth Type* drop-down menu, select *OAuth 2.0 with SAML Flow*.

8.  In the *Token URL* field, paste the value of the Token URL from the *Token Endpoint* field in the *Security* \> *OAuth* \> *Branding* \> *OAuth URLs*.

9.  In the *Token Method* field, select *POST*.

10. In the *Audience* field, paste the local service provider name for your account from the SAP BTP cockpit.

    > ### Note:  
    > Open the SAP BTP cockpit and go to *Security* \> *Trust* \> *Local Service Provider* \> *Local Provider Name*. See [Principal Propagation to OAuth-Protected Applications](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/310f39e504024079933066db8b6c6d00.html).

11. In the *Recipient* field, enter the same value as the one in the *Token URL* field.

12. In the *Issuer* field, copy and paste the same value as the *Name* field of the trusted identity provider you created in the SAP BTP cockpit. See [Create Trusted Identity Provider in SAP BTP Cockpit](create-trusted-identity-provider-in-sap-btp-cockpit-83e5ad2.md).

13. In the *X509 Keys*, select the OAuth X509 key you created. See [Generate OAuth X509 Key in SAP SuccessFactors](generate-oauth-x509-key-in-sap-successfactors-f636503.md).

14. Choose *Save*.


