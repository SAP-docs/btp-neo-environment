<!-- loioe73bc61d0f5d463d82da4a7ee47da192 -->

# Remove the Extension Integration

You can remove the integration between an SAP SuccessFactors company and a subaccount in SAP BTP, Neo environment in the SAP BTP cockpit.



<a name="loioe73bc61d0f5d463d82da4a7ee47da192__prereq_rps_3c2_n3b"/>

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
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of the following technology portfolios: application development; process automation; integration; data, analytics, and enterprise planning; artificial intelligence. The platform offers users the ability to turn data into business value, compose end-to-end business processes, connect entire IT landscapes, and personalize, build and extend SAP applications. This reduces the overall total cost of ownership maintaining SAP landscapes and third-party software across end-to-end business processes.") :arrow_upper_right:.**

You can remove the extension integration between your SAP SuccessFactors company and the subaccount in SAP BTP. This will remove:

-   the company identity provider from the trusted identity providers in the subaccount. Only the identity providers that have been added during the configuration of the extension integration will be removed.

-   the SAP SuccessFactors company OAuth clients managed by the SAP BTP

-   all company Authorized SP Assertion Consumer Services \(ACS\) managed by SAP BTP

-   the home page tiles, if configured


> ### Note:  
> This will affect all applications that use the extension integration.



<a name="loioe73bc61d0f5d463d82da4a7ee47da192__steps_qlv_kk2_n2b"/>

## Procedure

1.  In the SAP BTP Neo cockpit, navigate to **<your\_subaccount\>** \> *Integration Tokens*.

2.  In the *Integrated System* screen area, choose the *Remove*.


