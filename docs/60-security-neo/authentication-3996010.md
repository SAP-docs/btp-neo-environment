<!-- loio3996010faedc404e97d300f12e3bc988 -->

# Authentication

SAP BTP uses the Security Assertion Markup Language \(SAML\) 2.0 protocol for authentication and single sign-on.

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/docs/btp/sap-business-technology-platform/sap-business-technology-platform?version=Cloud) .**

By default, the SAP BTP is configured to use the SAP ID service as identity provider \(IdP\), as specified in SAML 2.0. You can configure a trust relationship to your custom IdP to provide access to the cloud using your own user database. For information, see [Application Identity Provider](application-identity-provider-dc61853.md#loiodc618538d97610148155d97dcd123c24).

HTML5 applications are protected with SAML2 authentication by default. For publicly accessible applications, the authentication can be switched off. For information about how to switch off authentication, see [Authentication](../30-development-neo/authentication-de16793.md).

