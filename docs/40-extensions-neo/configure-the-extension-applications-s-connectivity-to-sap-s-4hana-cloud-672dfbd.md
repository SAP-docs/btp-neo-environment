<!-- loio672dfbdd740944eaad45d063bf90440c -->

# Configure the Extension Applications's Connectivity to SAP S/4HANA Cloud

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**

To set up the connectivity from a subaccount in SAP BTP to an SAP S/4HANA Cloud tenant, you need to create HTTP destinations in the SAP BTP cockpit. These destinations provide data communication via HTTP protocol. For more information, see [HTTP Destinations](https://help.sap.com/viewer/cca91383641e40ffbe03bdc78f00f681/Cloud/en-US/b068356dd7c34cf7ad6b6023deeb317d.html).

When creating an HTTP destination, you can use different authentication types for access control:



<a name="loio672dfbdd740944eaad45d063bf90440c__section_cqs_5tn_4cb"/>

## Basic Authentication

Using authentication method you need to provide username and password. When configuring the HTTP destination in the cockpit, the username must correspond to the communication user in the SAP S/4HANA Cloud tenant.

See [Using Basic Authentication](using-basic-authentication-f4c0ad4.md#loiof4c0ad4a1c7d44e992826bb5c939c487).



<a name="loio672dfbdd740944eaad45d063bf90440c__section_ny4_5tn_4cb"/>

## Client Certificate Authentication

To configure a client certificate authentication, you need a client certificate signed by a trusted certificate authority \(CA\). You upload the public key when creating a communication user in the SAP S/4HANA Cloud tenant, and then, you add the corresponding keystore to the HTTP destination in the cockpit.

See [Using Client Certificate Authentication](using-client-certificate-authentication-d360a3d.md#loiod360a3d2af2d426d8243e44bd8ef6a30).



<a name="loio672dfbdd740944eaad45d063bf90440c__section_nsq_stn_4cb"/>

## SAML Bearer Assertion Authentication

You can use the SAML Bearer assertion flow for consuming OAuth-protected resources. Users are authenticated by using SAML against the configured trusted identity providers. The SAML assertion is then used to request an access token from an OAuth authorization server. This access token is automatically injected in all HTTP requests to the OAuth-protected resources.

See [Using SAML Bearer Assertion Authentication](using-saml-bearer-assertion-authentication-a4f1d55.md#loioa4f1d55c57b446fc8d66a9f59009225f).

