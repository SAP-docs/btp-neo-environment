<!-- loioa6663f02b4f9467f921b21f364abda48 -->

# Configure Availability Checks for SAP HANA XS Applications from the Cockpit

In the SAP BTP cockpit, you can configure availability checks for the SAP HANA XS applications running on your productive SAP HANA database system.



<a name="loioa6663f02b4f9467f921b21f364abda48__prereq_cb4_pn4_jdb"/>

## Prerequisites

-   The *manageMonitoringConfiguration* scope is assigned to the used platform role for the subaccount. For more information, see [Platform Scopes](../50-administration-and-ops-neo/platform-scopes-f226074.md).

-   You have deployed and started an SAP HANA XS application in your subaccount.




## Context

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**



<a name="loioa6663f02b4f9467f921b21f364abda48__steps_jbf_23y_qn"/>

## Procedure

1.  Open the subaccount in the SAP BTP cockpit.

2.  Choose *Applications* \> *HANA XS Applications* in the navigation area of the subaccount.

3.  Select an application from the list, and in the *Application Details* panel, configure the check.

    -   To create a new check, choose *Create Availability Check*.
    -   To view a created availability check, choose *Details*.
    -   To update a created availability check, choose *Details* \> *Edit*.
    -   To delete a created availability check, choose *Details* \> *Delete*.

4.  In the dialog that appears, select or enter the URL you want to monitor and fill in values for warning and critical thresholds if you want them to be different from the current ones. The default values are 50 seconds for a warning threshold and 60 seconds for a critical threshold.

5.  Save your configuration.

    When your availability check is created, you can view your application's latest HTTP response code and response time as well as a status icon showing whether your application is up or down. If you want to receive alerts when your application is down, you have to configure alerting.


**Related Information**  


[Alerting](https://help.sap.com/viewer/64f7d2b06c6b40a9b3097860c5930641/Cloud/en-US/2f782d7f73304426b287f4b25e47f0b1.html "Configure a channel in SAP Monitoring service to receive alert notifications when your applications and database systems are in a problematic state or have recovered from such a state.") :arrow_upper_right:

[SAP BTP Cockpit](https://help.sap.com/viewer/ea72206b834e4ace9cd834feed6c0e09/Cloud/en-US/19d7119265474dd18ec16fad2a0b28c1.html)

[Availability Checks](https://help.sap.com/viewer/64f7d2b06c6b40a9b3097860c5930641/Cloud/en-US/68f46b7fea21462b9c1c345b75524bec.html "Create an availability check for a Java or an SAP HANA XS application to track if the application is available and to receive alerts for it.") :arrow_upper_right:

[Configure Availability Checks for SAP HANA XS Applications from the Console Client](configure-availability-checks-for-sap-hana-xs-applications-from-the-console-client-951d9b8.md "In the console client, you can configure an availability check for your SAP HANA XS application and subscribe recipients to receive alert e-mail notifications when it is down or responds slowly.")

