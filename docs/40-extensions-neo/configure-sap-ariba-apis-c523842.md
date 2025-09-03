<!-- loioc523842b15224640ae262f847a7aeeac -->

# Configure SAP Ariba APIs



## Context

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/docs/btp/sap-business-technology-platform/sap-business-technology-platform?version=Cloud) .**

To be able to consume the SAP Ariba APIs, you need to register a dedicated application in SAP Ariba Developer Portal \([USA region](https://developer.ariba.com/api/) or [Europe region](https://eu.developer.ariba.com/api/)\). For each registered application, an application key is generated. You can use it to try out an API and start developing your extension application running on SAP BTP. When developing this application, you need to work against sandbox environment with mocked API data. Once your extension application is ready, follow the instructions on [https://developer.ariba.com/api/guides](https://developer.ariba.com/api/guides) to enable the application registered in SAP Ariba Developer Portal for production access.

You can find detailed information about each API in the *Discovery* section at [https://developer.ariba.com/api/apis](https://developer.ariba.com/api/apis) \(for the USA region\) or at [https://eu.developer.ariba.com/api/apis](https://eu.developer.ariba.com/api/apis) \(for the Europe region\).



### Configure SAP Ariba APIs

You have an SAP Ariba APIs account and have explored the available APIs. You can start configuring the SAP Ariba APIs to be able to accept requests from your application.

First, you register an application running on SAP BTP in SAP Ariba Developer Portal \([USA region](https://developer.ariba.com/api/) or [Europe region](https://eu.developer.ariba.com/api/)\). Once you do so, you receive an application key. Using this key, you can start exploring the APIs requests and responses in SAP Ariba APIs sandbox environment.

To access real data from SAP Ariba systems, you request production access for your registered application. When production access is granted, you receive an OAuth client for OAuth authentication or service provider credentials for basic authentication \(depending on the authentication mechanism a particular API uses\) that has to be used when calling the API.

For a full list of the SAP Ariba APIs, see [https://help.sap.com/viewer/p/ARIBA\_APIS](https://help.sap.com/viewer/p/ARIBA_APIS).



<a name="loioc523842b15224640ae262f847a7aeeac__steps_my5_gzz_41b"/>

## Procedure

1.  [Register an Application in SAP Ariba Developer Portal](register-an-application-in-sap-ariba-developer-portal-4616b20.md).

2.  [Promote the Application in SAP Ariba APIs to Production](promote-the-application-in-sap-ariba-apis-to-production-092c0ff.md).


