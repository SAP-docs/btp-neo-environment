<!-- loio00f238b092cb4402b00adfd10209f37d -->

# Test the Role Assignments

To test the role assignments you first start the deployed extension application to make it available for requests, and then try to access it with the users with different level of granted access to the application.



## Prerequisites

-   You have downloaded and configured SAP BTP console client. For more information, see [Console Client for the Neo Environment](../50-administration-and-ops-neo/console-client-for-the-neo-environment-7613230.md).

-   You have made yourself familiar with the SAP BTP cockpit concepts. For more information, see [Account Administration in the Cockpit](../50-administration-and-ops-neo/account-administration-in-the-cockpit-71eaba1.md).



## Context

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**



<a name="loio00f238b092cb4402b00adfd10209f37d__steps_mns_hgg_dq"/>

## Procedure

1.  Open the command prompt and navigate to the folder containing `neo.bat/sh` \(<code><i class="varname">&lt;SDK installation folder&gt;</i>/tools</code>\).

2.  Start the deployed application using the following command:

    ```
    neo start --account <subaccount_name> --application <application_name> --user <e-mail_or_user> --host <host>
    ```

3.  Access the application using users with different roles assigned to them.

    To access the application, use the application URL. To get the login URL of an application deployed in your extension subaccount, open the SAP BTP cockpit, and navigate to*Account* \> **<subaccount\_name\>** \> *Java Applications* \> **<name\_of\_your\_extension\_application\>** \> *Application URLs*.


