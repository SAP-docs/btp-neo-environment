<!-- loio425f7287294a4b4aa6d0f96b4fabb8b2 -->

# Security Testing

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**

This section describes how you can test the security you have implemented in your Java applications.

First, you need to test your application on your local runtime. If you use the Eclipse Tools, you can easily test with local users. This is useful if you are implementing role-based identity management in your application.

Then, if everything goes well on the local runtime, you can deploy your application on SAP BTP, and test how the application works on the Cloud with your local SAML 2.0 identity provider. This makes use if you are implementing SAML 2.0 identity federation.

**Related Information**  


[Test Security Locally](test-security-locally-fe47e02.md "When you add user authentication to your application, you can test it first on the local server before uploading it to SAP BTP.")

[Test Security on the Cloud \(with a Local Identity Provider\)](test-security-on-the-cloud-with-a-local-identity-provider-754818e.md "You can use a local test identity provider (IdP) to test single sign on (SSO) and identity federation of an SAP BTP application end-to-end.")

