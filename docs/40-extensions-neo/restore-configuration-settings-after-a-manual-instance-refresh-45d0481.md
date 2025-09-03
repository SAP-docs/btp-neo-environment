<!-- loio45d048169c504a6a97d9a2ad0bb32389 -->

# Restore Configuration Settings After a Manual Instance Refresh

If your cloud operators have performed an instance refresh manually, you must restore your extension integration artifacts and configuration settings for the SAP SuccessFactors target company.



## Prerequisites

-   You have a dedicated SAP SuccessFactors company instance.

-   The cloud operators have performed an instance refresh manually.

-   You have a user with either assigned the `Administrator` predefined role or a custom platform role with the following scopes for the subaccount which you want to integrate with your SAP BTP system:

    -   readExtensionIntegration

    -   manageExtensionIntegration

    -   manageDestinations

    -   manageApplicationRoleProvider

    -   manageTrustSettings


    For more information, see [Platform Scopes](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/f2260746ed8e446fafdeaaa8ab43e307.html) and [Manage Custom Platform Roles in the Neo Environment](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/ede5f721e78e4d678c87c8a200c564ca.html).

-   You have integrated a subaccount in SAP BTP with your SAP SuccessFactors company.



## Context

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/docs/btp/sap-business-technology-platform/sap-business-technology-platform?version=Cloud) .**

In SAP SuccessFactors, instance refresh is a procedure in which the data and the settings of a source company instance are copied into another company instance. During the instance refresh the data of the target company instance is deleted and replaced by the data of the source company instance. Therefore, after an instance refresh, if the target company has been integrated with a subaccount in SAP BTP, the extension integration configuration settings and artifacts in the target company are overwritten by the configuration settings and data coming from the source company. The instance refresh can be triggered either automatically with the *Instance Refresh* tool, or manually. For more information about restoring the extension artifacts after an automated instance refresh, see [Restore Configuration Settings After an Automated Instance Refresh](restore-configuration-settings-after-an-automated-instance-refresh-e4ad14c.md).

The manual refresh is triggered by cloud operators. After your cloud operators have performed an instance refresh manually, you must trigger the operation for restoring the extension integration artifacts and configuration settings in the SAP SuccessFactors target company instance afterwards.

> ### Note:  
> This operation includes restoring the OAuth clients, the Assertion Consumer Services \(ACS\) of the target company instance created by the cloud platform, the *Extensions Admin* role and the *Extensions Administrators* group, and the outbound connections. The OAuth SAML Bearer destinations are recreated for the extension integration.



## Procedure

To restore the extension artifacts after a manual instance refresh, proceed as follows:

1.  In the SAP BTP Neo cockpit, navigate to **<your\_subaccount\>** \> *Integration Tokens*.

2.  In the *Integrated System* screen area, choose the *Refresh*.




## Results

You have restored the OAuth clients, the Assertion Consumer Services \(ACS\) of the target company instance created by the cloud platform, the *Extensions Admin* role and the *Extensions Administrators* group, and the outbound connections for the target company instance and deleted any extension integration configuration settings coming from the source company instance.

The following artifacts need to be restored manually:

-   Home page tiles

-   All permission roles but the default *Extensions Admin*.

-   All permission groups but the default *Extensions Administrators*.


In the *Solutions* view in SAP BTP cockpit

-   The home page tiles are missing.

-   The OAuth clients cannot be found because they have new IDs after the refresh.

-   The permission roles and permission groups are missing.




<a name="loio45d048169c504a6a97d9a2ad0bb32389__postreq_k3t_s3x_z4b"/>

## Next Steps

-   If you have used console client commands to configure the extension artifacts initially, proceed as follows to restore the home page tile, and the permission roles and groups:

    -   To restore the home page tiles, register the home page tiles you want to restore. See [Register a Home Page Tile for the Extension Application](register-a-home-page-tile-for-the-extension-application-6648ccf.md)

    -   To restore the permission roles and permission groups:
        1.  [Import the Extension Application Roles in the SAP SuccessFactors System](import-the-extension-application-roles-in-the-sap-successfactors-system-f0ed89f.md)

        2.  [Assign the Extension Application Roles to Users](assign-the-extension-application-roles-to-users-d838fff.md)
        3.  [Test the Role Assignments](test-the-role-assignments-00f238b.md)


-   If you have used Multitarget Applications \(MTA\) to configure the settings and have a solution in which the home page tiles, and the required permission roles and permission groups are defined, redeploy the solution. See [Operating Solutions](../30-development-neo/operating-solutions-2abf7d4.md).

