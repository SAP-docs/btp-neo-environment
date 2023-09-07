<!-- loio9d3f8090a0044b18acb69702d0ad8d6f -->

# Refresh the Extension Integration for SAP SuccessFactors



<a name="loio9d3f8090a0044b18acb69702d0ad8d6f__prereq_rps_3c2_n3b"/>

## Prerequisites

Your user has assigned either the `Administrator` predefined role or a custom platform role with the following scopes for the subaccount which you want to integrate with your SAP BTP system:

-   readExtensionIntegration

-   manageExtensionIntegration

-   manageDestinations

-   manageApplicationRoleProvider

-   manageTrustSettings


For more information, see [Platform Scopes](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/f2260746ed8e446fafdeaaa8ab43e307.html) and [Manage Custom Platform Roles in the Neo Environment](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/ede5f721e78e4d678c87c8a200c564ca.html).



## Context

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**

You can refresh the extension integration for the SAP SuccessFactors company and the respective subaccounts.



<a name="loio9d3f8090a0044b18acb69702d0ad8d6f__steps_qlv_kk2_n2b"/>

## Procedure

1.  In the SAP BTP Neo cockpit, navigate to **<your\_subaccount\>** \> *Integration Tokens*.

2.  In the *Integrated System* screen area, choose the *Refresh*.




<a name="loio9d3f8090a0044b18acb69702d0ad8d6f__result_mnk_lk2_n2b"/>

## Results

During the refresh:

-   The trust between the subaccount in SAP BTP and the SAP SuccessFactors company instance is reconfigured, and generates a local service provider for this subaccount only if there isn't one.

-   The *Authorized SP Assertion Consumer Service* \(ACS\) configured with the `hcmcloud-enable-application-access` command and the ones created during the integration process settings are recreated for the extension integration. If there are ACSes configured manually in the SAP SuccessFactors company and related to applications running in this subaccount they will not be recreated by the refresh process.

-   The OAuth clients created by the `hcmcloud-create-connection` command and the automated integration process are recreated.

-   The OAuth SAML Bearer destinations created for the extension integration are updated.

    > ### Note:  
    > If you have manually deleted an OAuth SAML Bearer destination with system user, after the refresh, this destination will be recreated with all the properties it used to have except the *System User*. For the *System User* property, it will be set the value `##REPLACE_USER##`. You need to manually edit this destination in the SAP BTP cockpit and replace the *System User* value with a real technical user.
    > 
    > Note that the *System User* property is deprecated and will be removed soon. We recommend that you work on behalf of specific \(named\) users instead of working with a technical user.
    > 
    > See [OAuth SAML Bearer Assertion Authentication](https://help.sap.com/viewer/cca91383641e40ffbe03bdc78f00f681/Cloud/en-US/c69ea6aacd714ad2ae8ceb5fc3ceea56.html "Create and configure an OAuth SAML Bearer Assertion destination for an application in the Cloud Foundry environment.") :arrow_upper_right:.

-   The *Extensions Admin* role and the *Extensions Administrators* group are recreated if they do not already exist, and the *Extensions Admin* role is reassigned to the *Extensions Administrators* group.


