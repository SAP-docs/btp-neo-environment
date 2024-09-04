<!-- loioe6dcbf41cee1443a899d3a6275715f7b -->

# Add Users to SAP ID Service in the Neo Environment

Before you can assign roles or role collections to a user in SAP ID service, you have to ensure that this user is assigned to SAP ID service.



<a name="loioe6dcbf41cee1443a899d3a6275715f7b__prereq_mvk_fdf_bhb"/>

## Prerequisites

The user you want to add to SAP ID service must have an SAP user account \(for example, an S-user or P-user\). For more information, see [Create SAP User Accounts](https://help.sap.com/viewer/ea72206b834e4ace9cd834feed6c0e09/Cloud/en-US/51ec990e1d6e42468eafb733a503c92b.html) .



<a name="loioe6dcbf41cee1443a899d3a6275715f7b__context_vnf_r3c_t3b"/>

## Context

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of the following technology portfolios: application development; process automation; integration; data, analytics, and enterprise planning; artificial intelligence. The platform offers users the ability to turn data into business value, compose end-to-end business processes, connect entire IT landscapes, and personalize, build and extend SAP applications. This reduces the overall total cost of ownership maintaining SAP landscapes and third-party software across end-to-end business processes.") :arrow_upper_right:.**



<a name="loioe6dcbf41cee1443a899d3a6275715f7b__steps_unm_1rf_bhb"/>

## Procedure

1.  Go to your subaccount and choose *Security* \> *Authorizations*.

2.  Choose the trust configuration for SAP ID service.

3.  Enter the business user's name in the *User* field, for example `john.doe@example.com`.

    > ### Remember:  
    > If the user identifier you entered does not have an SAP user account or has never logged on to an application in this subaccount, SAP BTP cannot automatically verify the user name. To avoid mistakes, you must ensure that the user name is correct and that it exists in SAP ID service.


**Related Information**  


[Platform Identity Provider for Tools](../60-security-neo/platform-identity-provider-for-tools-80edbe7.md "Configure the platform identity provider to be used for authentication in service and platform tools (for example, Neo console client, Cloud Connector, SAP Git Service, and so on). The default user base is provided by SAP ID Service. You can switch to an Identity Authentication tenant if you want to use a custom user base.")

