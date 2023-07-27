<!-- loioe4ad14c1ec72412ea06b7e862a86165f -->

# Restore Configuration Settings After an Automated Instance Refresh

If you have performed an automated instance refresh with the *Instance Refresh* tool, you restore some of your extension integration artifacts and configuration settings for the SAP SuccessFactors target company manually.



## Prerequisites

-   You have a dedicated SAP SuccessFactors company instance.
-   You have Provisioning access and administrator permissions.
-   You have integrated a subaccount in SAP BTP with your SAP SuccessFactors company.
-   You have performed the instance refresh with the *Instance Refresh* tool.



## Context

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://launchpad.support.sap.com/#/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**

In SAP SuccessFactors, instance refresh is a procedure in which the data and the settings of a source company instance are copied into another company instance. During the instance refresh the data of the target company instance is deleted and replaced by the data of the source company instance. Therefore, after an instance refresh, if the target company has been integrated with a subaccount in SAP BTP, the extension integration configuration settings and artifacts in the target company are overwritten by the configuration settings and data coming from the source company.

The instance refresh can be triggered automatically with the *Instance Refresh* tool. If you have performed an instance refresh with the *Instance Refresh* tool, the OAuth clients, the Assertion Consumer Services \(ACS\) of the target company instance created by the cloud platform, and the OAuth SAML Bearer destinations, and the inbound connections are recreated for the extension integration.

> ### Note:  
> The OAuth clients are recreated but they are assigned new IDs. This does not affect the configuration settings.

However, you must reconfigure the following artifacts and settings in the SAP SuccessFactors target company instance:

-   Custom home page tiles

-   Permission roles

-   Permission groups

-   Outbound connections \(can be recreated with a solution deployment only\)


The automated refresh results in the following behavior in the *Solutions* view in SAP BTP cockpit

-   The custom home page tiles are missing.

-   The OAuth clients cannot be found because they have new IDs after the refresh.

-   The permission roles and permission groups are missing.

-   The outbound connections are missing.




## Procedure

1.  To restore the configuration settings after an automated instance refresh, proceed as follows:

    -   If you have used console client commands to configure the extension artifacts initially, proceed as follows:
        -   To restore the home page tiles, register the home page tiles you want to restore. See [Register a Home Page Tile for the Extension Application](register-a-home-page-tile-for-the-extension-application-6648ccf.md)

        -   To restore the permission roles and permission groups:
            1.  [Import the Extension Application Roles in the SAP SuccessFactors System](import-the-extension-application-roles-in-the-sap-successfactors-system-f0ed89f.md)
            2.  [Assign the Extension Application Roles to Users](assign-the-extension-application-roles-to-users-d838fff.md)
            3.  [Test the Role Assignments](test-the-role-assignments-00f238b.md)


    -   If you have used Multitarget Applications \(MTA\) to configure the settings and have a solution in which the home page tiles, the required permission roles and permission groups, and the outbound connections are defined, redeploy the solution. See [Operating Solutions](../30-development-neo/operating-solutions-2abf7d4.md).

2.  Delete any unneeded extension integration configuration settings coming from the source company instance.




## Results

-   You have restored the extension integration artifacts and configuration setting of the target company instance and deleted any extension integration configuration settings coming from the source company instance.

-   The *Solutions* view in SAP BTP cockpit displays the home page tiles.

-   If you have redeployed a solution, the OAuth client IDs have been reverted to the initial ones and they can be found in the *Solution* view.

    > ### Note:  
    > If you have used console client commands to restore the extension artifacts, the OAuth clients cannot be found in the *Solutions* view because they have new IDs after the refresh but they are restored.


