<!-- loiodbd314ae30f7493a8c21033b53c02bb5 -->

# Handle Unplanned Downtime

In the event of unplanned downtime when there is no application process able to serve HTTP requests, a default error is shown to users. To prevent this, an operator can configure a custom downtime page using a downtime application, which takes over the HTTP traffic if an unplanned downtime occurs.



## Prerequisites

> ### Note:  
> Not applicable to *hanatrial.ondemand.com*.

-   You have downloaded and configured the console client. We recommend that you use the latest SDK. For more information, see [Set Up the Console Client](../30-development-neo/set-up-the-console-client-7613dee.md).
-   You have deployed and started your own downtime application in the same SAP BTP subaccount as the application itself.
-   The downtime application has to be developed in a way that it returns an HTTP 503 return code. That is especially important if availability checks are configured for the original applications so that unplanned downtimes are properly detected.



## Context

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://launchpad.support.sap.com/#/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**



<a name="loiodbd314ae30f7493a8c21033b53c02bb5__steps_kvy_z2t_mn"/>

## Procedure

1.  Open the command prompt and navigate to the folder containing *neo.bat/sh* \(`<SDK installation folder>/tools`\).

2.  Configure the downtime application by executing `neo set-downtime-app` in the command line.

    ```
    neo set-downtime-app --host <host> --account <subaccount_name> --application <application_name>  --user <e-mail_or_user> 
    --downtime-application <downtime_application_name>
    
    ```

3.  \(optional\) If the downtime page is no longer needed \(for example, if the original application has been undeployed\), you can remove it by executing `clear-downtime-app` command.

    ```
    neo clear-downtime-app --host <host> --account <subaccount_name> --application <application_name>  --user <e-mail_or_user>
    
    ```


**Related Information**  


[set-downtime-app](set-downtime-app-1672997.md "This command configures a custom downtime page (downtime application) for an application. The downtime page is shown to the user in the event of unplanned downtime of the original application.")

[clear-downtime-app](clear-downtime-app-c9ae25a.md "The command deregisters a previously configured downtime page for an application. After you execute the command, the default HTTP error will be shown to the user in the event of unplanned downtime.")

