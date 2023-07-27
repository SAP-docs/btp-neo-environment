<!-- loio94f2c1f7c2a149a4a9569266f71c7b1b -->

# Configuring the SAP BTP Application Connectivity to SAP Cloud for Customer APIs

You configure the connectivity to enable the use of SAP Cloud for Customer OData APIs.

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://launchpad.support.sap.com/#/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**

-   Create and configure the OAuth client for OData access to enable the connectivity to SAP Cloud for Customer OData APIs. For more information, see [Configure the OAuth Client for OData Access](configure-the-oauth-client-for-odata-access-0ac0dc9.md).

-   Configure the HTTP destination required to create an HTTP client for the OData API. For more information, see [Create and Configure the HTTP Destination](create-and-configure-the-http-destination-9292948.md).

When your extension application needs to do read and write operations from/to the SAP Cloud for Customer system, you have to configure the connectivity to enable the use of SAP Cloud for Customer OData APIs. You need such connectivity to be established also when you want to embed the UIs of the extension solution into the SAP Cloud for Customer user interface.

The connectivity configuration steps are required on both systems and can be implemented with the following options depending on the security mechanisms for protecting the connectivity:

**Using OAuth**

> ### Note:  
> OAuth can be used only when a common identity provider is configured for both systems.

-   On SAP Cloud for Customer side:

    -   [Configure OAuth Identity Provider in SAP Cloud for Customer](configure-oauth-identity-provider-in-sap-cloud-for-customer-ba893b5.md)

    -   [Configure the OAuth Client for OData Access](configure-the-oauth-client-for-odata-access-0ac0dc9.md)



-   On the SAP BTP side:

    -   Create an HTTP destination with OAuthSAMLBearerAssertion for authentication method. For more details, see [Create and Configure the HTTP Destination](create-and-configure-the-http-destination-9292948.md).



**Using Basic Authentication**

-   On SAP Cloud for Customer side:

    -   \(If not available\) Create a technical user with permissions to access the required SAP Cloud for Customer OData APIs and use it for the HTTP destination configuration when you choose Basic authentication for protecting the connectivity.



-   On the SAP BTP side:

    -   Create an HTTP destination with Basic authentication using the credentials of a technical user in the SAP Cloud for Customer system. For more details, see [Create and Configure the HTTP Destination](create-and-configure-the-http-destination-9292948.md).



