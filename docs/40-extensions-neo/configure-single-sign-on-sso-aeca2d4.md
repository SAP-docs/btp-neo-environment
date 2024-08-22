<!-- loioaeca2d4572ae47ff93e352bdbf321d2d -->

# Configure Single Sign-On \(SSO\)



## Context

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of the following technology portfolios: application development; process automation; integration; data, analytics, and enterprise planning; artificial intelligence. The platform offers users the ability to turn data into business value, compose end-to-end business processes, connect entire IT landscapes, and personalize, build and extend SAP applications. This reduces the overall total cost of ownership maintaining SAP landscapes and third-party software across end-to-end business processes.") :arrow_upper_right:.**

SAP BTP introduces Single Sign-On \(SSO\) through SAML2.0. In SAP BTP, identity information is provided by identity providers, and not stored on the cloud platform itself. If you have configured corporate identity provider in SAP Ariba, you have to configure the same identity provider for SAP BTP to have seamless application login experience for the users. To enable this seamless login experience you need to:

-   Perform a few configuration tasks on SAP BTP

-   Change some of the SAP Ariba configurations if you don't use SAML 2.0 compliant authentication mechanism




## Procedure

1.  Configure SSO between SAP Ariba and your identity provider. See [Set Up Trust Between SAP Ariba and Corporate Identity Provider Using SAML 2.0](set-up-trust-between-sap-ariba-and-corporate-identity-provider-using-saml-2-0-3108789.md).

2.  Configure SSO between SAP BTP and your identity provider. See [Set Up Trust Between Corporate Identity Provider and SAP BTP](set-up-trust-between-corporate-identity-provider-and-sap-btp-0f61725.md).


