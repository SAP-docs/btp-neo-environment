<!-- loio0ac0dc9b3f3e4a07ba64cbac74a23327 -->

# Configure the OAuth Client for OData Access

In SAP Cloud for Customer, use this procedure to configure the OAuth client for OData access to SAP Cloud for Customer OData APIs.



## Context

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of the following technology portfolios: application development; process automation; integration; data, analytics, and enterprise planning; artificial intelligence. The platform offers users the ability to turn data into business value, compose end-to-end business processes, connect entire IT landscapes, and personalize, build and extend SAP applications. This reduces the overall total cost of ownership maintaining SAP landscapes and third-party software across end-to-end business processes.") :arrow_upper_right:.**



## Procedure

1.  Log on to your SAP Cloud for Customer system as an administrator. Go to *ADMINISTRATOR* \> *OAUTH2.0 CLIENT REGISTRATION*.

2.  Choose *New*.

3.  Specify a client secret, description, and token lifetime \(in seconds\). For example, 3600 seconds.

4.  In the *Issuer Name* field, use the dropdown list to specify the identity provider you are using:

    -   if you have triggered an automated integration between SAP Cloud for Customer and SAP BTP, the identity provider was registered during this automated integration. To check which is this identity provider, go to SAP BTP cockpit and then choose *Security* \> *Trust* \> *Local Service Provider*. The value of the *Local Service Provider* field is the identity provider you need to select from the dropdown list.

    -   if you don't use an automated integration, use the identity provider that you created in the document [Configure OAuth Identity Provider in SAP Cloud for Customer](configure-oauth-identity-provider-in-sap-cloud-for-customer-ba893b5.md).


5.  Copy the entry in the *Client ID* field. You will need it later when creating the HTTP destination with OAuth authentication required for the connectivity to the SAP Cloud for Customer OData APIs.

6.  In the *Scope* list, select the *UIWC:CC\_HOME* scope.

7.  Choose *Save and Close*.




## Next Steps

On the SAP BTP side configure the HTTP destination required to create an HTTP client for the OData API, and thus ensure the connectivity toSAP Cloud for Customer. For more information, see [Create and Configure the HTTP Destination](create-and-configure-the-http-destination-9292948.md).

**Related Information**  


[Configuring OAuth 2.0](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/7e658b3e4cea4a79b035d0f1d2798c1f.html)

