<!-- loio951d9b8728384e4f80ad3ddfa4d18267 -->

# Configure Availability Checks for SAP HANA XS Applications from the Console Client

In the console client, you can configure an availability check for your SAP HANA XS application and subscribe recipients to receive alert e-mail notifications when it is down or responds slowly. For how to configure alerting, see the Related Information section.



<a name="loio951d9b8728384e4f80ad3ddfa4d18267__prereq_N10015_N10012_N10001"/>

## Prerequisites

-   You have a productive SAP HANA database on the platform.

    For more information, see [Using an SAP HANA XS Database System](using-an-sap-hana-xs-database-system-c6f5764.md).

-   You have set up the console client.

    For more information, see [Set Up the Console Client](set-up-the-console-client-7613dee.md).

-   The *manageMonitoringConfiguration* scope is assigned to the used platform role for the subaccount. For more information, see [Platform Scopes](../50-administration-and-ops-neo/platform-scopes-f226074.md).




## Context

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**



<a name="loio951d9b8728384e4f80ad3ddfa4d18267__steps_bhy_5gv_bm"/>

## Procedure

1.  Open the command prompt and navigate to the folder containing `neo.bat/sh (<SDK installation folder>/tools)`.

2.  Create the availability check.

    Execute:

    ```
    neo create-availability-check -a mysubaccount -b myhana:myhanaxsapp -u myuser -U /heartbeat.xsjs -C 6 -W 4 --host hana.ondemand.com
    ```

    -   Replace **"mysubaccount"**, **"myhana:myhanaxsapp"** and **"myuser"** with the technical name of your subaccount, and the names of the productive SAP HANA database, application, and user respectively.
    -   The availability URL \(**/heartbeat.xsjs** in this case\) is not provided by default by the platform. Replace it with a suitable URL that is already exposed by your SAP HANA XS application or create it. Keep in mind the limitations for availability URLs. For more information, see [Availability Checks](https://help.sap.com/viewer/64f7d2b06c6b40a9b3097860c5930641/Cloud/en-US/68f46b7fea21462b9c1c345b75524bec.html "Create an availability check for a Java or an SAP HANA XS application to track if the application is available and to receive alerts for it.") :arrow_upper_right:.

        > ### Note:  
        > In case you want to create an availability check for a protected SAP HANA XS application, you need to create a subpackage, in which to create an `.xsaccess` file with the following content:
        > 
        > ```json
        > {
        > 	"exposed": true,
        > 	"authentication": null,
        > 	"authorization": null
        > }
        > 
        > ```
        > 
        > In the SAP HANA XS Administration Tool \(https://<productive SAP HANA name\><subaccount\>.<host\>/sap/hana/xs/admin/\), find the subpackage and activate public access to it. After this, you will be able to monitor the resources on and under the subpackage level, that is, you will be able to create an availability check for your protected application. Note that in the availability URL, you have to provide the path to the resource in the subpackage that you will be monitoring, for example **/heartbeat.xsjs**.

    -   The check will trigger warnings **"-W 4"** if the response time is above **4** seconds and critical alerts **"-C 6"** if the response time is above 6 seconds or the application is not available.
    -   Use the respective host for your subaccount type.


**Related Information**  


[Alerting](https://help.sap.com/viewer/64f7d2b06c6b40a9b3097860c5930641/Cloud/en-US/2f782d7f73304426b287f4b25e47f0b1.html "Configure a channel to receive alert notifications from SAP Monitoring service when your applications and database systems are in a problematic state or have recovered from such a state.") :arrow_upper_right:

[Configure Availability Checks for SAP HANA XS Applications from the Cockpit](configure-availability-checks-for-sap-hana-xs-applications-from-the-cockpit-a6663f0.md "In the SAP BTP cockpit, you can configure availability checks for the SAP HANA XS applications running on your productive SAP HANA database system.")

[Regions and Hosts Available for the Neo Environment](../10-concepts-neo/regions-and-hosts-available-for-the-neo-environment-d722f7c.md "Each region represents a geographical location (for example, Europe, US East) where applications, data, or services are hosted.")

**Availability Checks Commands**  


[list-availability-check](../50-administration-and-ops-neo/list-availability-check-d37bcfc.md "Lists the availability checks.")

[create-availability-check](../50-administration-and-ops-neo/create-availability-check-83d4582.md "Creates an availability check.")

[delete-availability-check](../50-administration-and-ops-neo/delete-availability-check-2a387e4.md "Deletes an availability check.")

