<!-- loioaeca2d4572ae47ff93e352bdbf321d2d -->

# Configure Single Sign-On \(SSO\)



## Context

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/docs/btp/sap-business-technology-platform/sap-business-technology-platform?version=Cloud) .**

SAP BTP introduces Single Sign-On \(SSO\) through SAML2.0. In SAP BTP, identity information is provided by identity providers, and not stored on the cloud platform itself. If you have configured corporate identity provider in SAP Ariba, you have to configure the same identity provider for SAP BTP to have seamless application login experience for the users. To enable this seamless login experience you need to:

-   Perform a few configuration tasks on SAP BTP

-   Change some of the SAP Ariba configurations if you don't use SAML 2.0 compliant authentication mechanism




## Procedure

1.  Configure SSO between SAP Ariba and your identity provider. See [Set Up Trust Between SAP Ariba and Corporate Identity Provider Using SAML 2.0](set-up-trust-between-sap-ariba-and-corporate-identity-provider-using-saml-2-0-3108789.md).

2.  Configure SSO between SAP BTP and your identity provider. See [Set Up Trust Between Corporate Identity Provider and SAP BTP](set-up-trust-between-corporate-identity-provider-and-sap-btp-0f61725.md).


