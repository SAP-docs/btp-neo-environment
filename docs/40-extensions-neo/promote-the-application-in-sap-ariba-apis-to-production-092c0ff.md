<!-- loio092c0ffec9fd488c807730f171ddfed6 -->

# Promote the Application in SAP Ariba APIs to Production



<a name="loio092c0ffec9fd488c807730f171ddfed6__prereq_scq_5c1_p1b"/>

## Prerequisites

-   Have an SAP Ariba APIs account. See [Get an SAP Ariba APIs Account](get-an-sap-ariba-apis-account-f7dbeb2.md).

-   Have your application registered in SAP Ariba Developer Portal \([USA region](https://developer.ariba.com/api/) or [Europe region](https://eu.developer.ariba.com/api/)\). See [Register an Application in SAP Ariba Developer Portal](register-an-application-in-sap-ariba-developer-portal-4616b20.md).




## Context

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/docs/btp/sap-business-technology-platform/sap-business-technology-platform?version=Cloud) .**

You have registered an application running on SAP BTP in SAP Ariba Developer Portal and have explored different APIs published on SAP Ariba APIs sandbox environment. Then, you want to promote the registered application to production access.

A registered application promoted to production access in SAP Ariba Developer Portal is enabled for access to an SAP Ariba system and has an OAuth client, or a service provider account with credentials.

You use the OAuth client ID and client secret \(in case of OAuth authentication\) or the service provider credentials \(in case of Basic authentication\) to manage the authentication with an API published on SAP Ariba APIs production environment.



<a name="loio092c0ffec9fd488c807730f171ddfed6__steps_btg_jcg_j1b"/>

## Procedure

1.  Request production access for your registered application.

2.  Find your application client ID. The client ID was generated when the production access was granted.

3.  Generate a client secret. To execute an OAuth authentication, you will need the client secret for your application.

    > ### Note:  
    > Some APIs use Basic authentication and for them you don't need the client secret. You can find more information at [SAP Ariba Developer Portal](https://developer.ariba.com/api/welcome).

    For more details, follow the steps from SAP Ariba APIs guide:

    [https://developer.ariba.com/api/guides](https://developer.ariba.com/api/guides) \(for the USA region\) or [https://eu.developer.ariba.com/api/guides](https://eu.developer.ariba.com/api/guides) \(for the Europe region\).


