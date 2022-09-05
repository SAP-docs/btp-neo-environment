<!-- loioa8a5c418821245e3bc55191382fac7b6 -->

# Configuring Single Sign-On Using Identity Authentication

To ensure the required security for your landscape you need to perform a few configuration tasks on all the sides - SAP BTP, Identity Authentication and SAP Cloud for Customer.



## Context

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**

The following procedure describes how to configure Identity Authentication and SAP Cloud for Customer to use the authentication and single sign-on capabilities based on the industry standard SAML 2.0. You can also find information about how to configure the trust between Identity Authentication and the SAP BTP subaccount, in case it is not configured by default.



## Procedure

1.  Configure the trust settings between Identity Authentication and your SAP Cloud for Customer system. For more information, see [Setting Up Trust Between Identity Authentication and SAP Cloud for Customer](setting-up-trust-between-identity-authentication-and-sap-cloud-for-customer-e8b6db5.md).

    > ### Note:  
    > If you already have a SAP Cloud for Customer system with existing users, you need to define these users in the Identity Authentication service as well. To do that, export as a CSV file the users of your company employees from your SAP Cloud for Customer system and import it into Identity Authentication.

2.  Configure the SAP BTP trust settings and add the tenant of Identity Authentication available for your company as a SAML identity provider. For more information, see: [Setting Up Trust Between Identity Authentication and SAP BTP](setting-up-trust-between-identity-authentication-and-sap-btp-0df6abc.md).

    > ### Note:  
    > Use **Step 2** of this procedure only if the trust between the SAP BTP subaccount and Identity Authentication has not been automatically configured after you have purchased a subscription for your Identity Authentication tenant.


