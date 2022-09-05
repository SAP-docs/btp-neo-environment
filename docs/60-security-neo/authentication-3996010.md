<!-- loio3996010faedc404e97d300f12e3bc988 -->

# Authentication

SAP BTP uses the Security Assertion Markup Language \(SAML\) 2.0 protocol for authentication and single sign-on.

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**

By default, the SAP BTP is configured to use the SAP ID service as identity provider \(IdP\), as specified in SAML 2.0. You can configure a trust relationship to your custom IdP to provide access to the cloud using your own user database. For information, see [Application Identity Provider](application-identity-provider-dc61853.md#loiodc618538d97610148155d97dcd123c24).

HTML5 applications are protected with SAML2 authentication by default. For publicly accessible applications, the authentication can be switched off. For information about how to switch off authentication, see [Authentication](../30-development-neo/authentication-de16793.md).

