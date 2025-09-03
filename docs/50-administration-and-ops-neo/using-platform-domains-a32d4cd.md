<!-- loioa32d4cd65be344439d9ed752f182e609 -->

# Using Platform Domains

Using platform domains, you can configure the application network availability or authentication policy. You can achieve that by configuring the appropriate platform domain which will change the URL on which your application will be accessible.



## Prerequisites

You have installed and configured the console client for the Neo environment. For more information, see [Using the Console Client](using-the-console-client-8900b22.md).



## Context

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/docs/btp/sap-business-technology-platform/sap-business-technology-platform?version=Cloud) .**

The available platform domains are:

-   *hana.ondemand.com* - any application is accessible on this default domain after being deployed on the platform
-   *cert.hana.ondemand.com* - enables client certificate authentication
-   *svc.hana.ondemand.com* - provides access within the same region; for internal communication and not open on the Internet or other networks

You can configure the platform domains using the `application-domains` group of console client commands:

-   [Add a Platform Domain](using-platform-domains-a32d4cd.md#loio1c374b6349ab423eab16ab69d11b87d9)
-   [Check Configured Domains](using-platform-domains-a32d4cd.md#loio3142a5fb32724e2fa284a3f46eb13247)
-   [Remove Platform Domains](using-platform-domains-a32d4cd.md#loioa18bdb1fd07249288f8c287b3d29f62d)

<a name="loio1c374b6349ab423eab16ab69d11b87d9"/>

<!-- loio1c374b6349ab423eab16ab69d11b87d9 -->

## Add a Platform Domain



## Context

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/docs/btp/sap-business-technology-platform/sap-business-technology-platform?version=Cloud) .**



<a name="loio1c374b6349ab423eab16ab69d11b87d9__steps_u5v_sgz_4p"/>

## Procedure

1.  Open the command prompt and navigate to the folder containing `neo.bat/neo.sh`\(`<SDK installation folder>/tools`\).

2.  Configure the platform domain you have chosen by executing the `add-platform-domain` command.

    ```
    neo add-platform-domain --account mysubaccount --application myapp --user myuser --host hana.ondemand.com --platform-domain cert.hana.ondemand.com
    ```

    As a result, the specified application will be accessible on `cert.hana.ondemand.com` and on the default `hana.ondemand.com` domain.


<a name="loio3142a5fb32724e2fa284a3f46eb13247"/>

<!-- loio3142a5fb32724e2fa284a3f46eb13247 -->

## Check Configured Domains



## Context

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/docs/btp/sap-business-technology-platform/sap-business-technology-platform?version=Cloud) .**



<a name="loio3142a5fb32724e2fa284a3f46eb13247__steps_lpr_jns_fq"/>

## Procedure

1.  To make sure the new platform domain is configured, execute the `list-application-domains` command:

    ```
    neo list-application-domains --account mysubaccount --application myapp --user myuser --host hana.ondemand.com
    ```

2.  Check if the returned list of domains contains the platform domain you set.


<a name="loioa18bdb1fd07249288f8c287b3d29f62d"/>

<!-- loioa18bdb1fd07249288f8c287b3d29f62d -->

## Remove Platform Domains



## Context

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/docs/btp/sap-business-technology-platform/sap-business-technology-platform?version=Cloud) .**



<a name="loioa18bdb1fd07249288f8c287b3d29f62d__steps_yrv_rns_fq"/>

## Procedure

1.  When you no longer want the application to be accessible on the configured platform domain, remove it by executing the `remove-platform-domain` command:

    ```
    neo remove-platform-domain --account mysubaccount --application myapp --user myuser --host hana.ondemand.com --platform-domain cert.hana.ondemand.com
    ```

2.  Repeat the step for each platform domain you want to remove.


**Related Information**  


[add-platform-domain](add-platform-domain-7afd450.md "Adds a platform domain (under hana.ondemand.com) on which the application will be accessed.")

[list-application-domains](list-application-domains-51f8bd8.md "Lists all domain names on which an application can be accessed.")

[remove-platform-domain](remove-platform-domain-96c6d24.md "Removes a platform domain (under hana.ondemand.com) as an access point for an application.")

