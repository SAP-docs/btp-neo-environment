<!-- loiod1e1e182d8544acbb6506ffdb6a1f26d -->

# SAP ID Service

The default platform identity provider and application identity provider of SAP BTP is SAP ID service.

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of the following technology portfolios: application development; process automation; integration; data, analytics, and enterprise planning; artificial intelligence. The platform offers users the ability to turn data into business value, compose end-to-end business processes, connect entire IT landscapes, and personalize, build and extend SAP applications. This reduces the overall total cost of ownership maintaining SAP landscapes and third-party software across end-to-end business processes.") :arrow_upper_right:.**

Trust to SAP ID service in your subaccount is pre-configured in SAP BTP by default, so you can start using it without further configuration. Optionally, you can add additional trust settings or set the default trust to inactive, for example if you prefer to use another SAML 2.0 identity provider. Using the SAP BTP cockpit you can make changes by navigating to your respective subaccount and choosing *Security* \> *Authorization*.

If you want to add new users to a subscribed app, or if you want to add users to a service, such as Web IDE, you can add those users to SAP ID service in your subaccount. See [Add Users to SAP ID Service in the Neo Environment](add-users-to-sap-id-service-in-the-neo-environment-e6dcbf4.md).

> ### Note:  
> If you want to use a custom IdP, you must establish trust to your custom SAML 2.0 identity provider. We describe a custom trust configuration using the example of SAP Cloud Identity Services - Identity Authentication.
> 
> For more information, see [Trust and Federation with Identity Providers](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/cb1bc8f1bd5c482e891063960d7acd78.html "") :arrow_upper_right:.

