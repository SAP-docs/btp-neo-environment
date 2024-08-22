<!-- loio139d777900c94d36b0a93f76cd3947b1 -->

# Configure the SAP Connectivity service to SAP Ariba APIs



## Context

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of the following technology portfolios: application development; process automation; integration; data, analytics, and enterprise planning; artificial intelligence. The platform offers users the ability to turn data into business value, compose end-to-end business processes, connect entire IT landscapes, and personalize, build and extend SAP applications. This reduces the overall total cost of ownership maintaining SAP landscapes and third-party software across end-to-end business processes.") :arrow_upper_right:.**

You can configure connectivity from SAP BTP to SAP Ariba APIs sandbox and production environment.

-   APIs published on SAP Ariba APIs sandbox environment are meant for exploring and testing.

    To configure connectivity to an API published on SAP Ariba APIs sandbox environment, you create an HTTP destination for this API.

-   APIs published on SAP Ariba APIs production environment are secured with OAuth or Basic authentication depending on the API .

    This means that your extension application may need connectivity to the SAP Ariba APIs OAuth Server as well.

    To configure connectivity to an API published on SAP Ariba APIs productive environment, you create:

    -   an HTTP destination for this API


    -   an HTTP destination for SAP Ariba APIs OAuth Server if needed


    > ### Note:  
    > We recommend that you create both HTTP destinations for the SAP Ariba APIs and for the SAP Ariba APIs OAuth Server on application level.


> ### Note:  
> By updating the URL field in the HTTP destination for the API, you can easily switch from SAP Ariba APIs sandbox to production environment and vice-versa.



## Procedure

1.  Configure the SAP Connectivity service to SAP Ariba APIs Sandbox Environment. See [Using Sandbox Environment](using-sandbox-environment-81ddfa5.md).

2.  Configure the SAP Connectivity service to SAP Ariba APIs Productive Environment. See [Using Production Environment](using-production-environment-039cce8.md).


