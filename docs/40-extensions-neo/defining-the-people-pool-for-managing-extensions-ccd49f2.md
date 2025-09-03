<!-- loioccd49f261d664ea4a0e8e18cdf44ddd4 -->

# Defining the People Pool for Managing Extensions

Once you have performed the automated configuration, you include members in the *Extensions Administrators* group to define who can access the extension management page from SAP SuccessFactors.



## Prerequisites

-   You have the role-based permission environment enabled for the SAP SuccessFactors customer instance \(company\).

-   You have a *Security Admin* user for SAP SuccessFactors and have access to the functionality on the SAP SuccessFactors *Admin Center* page.
-   You have configured the SAP BTP extension integration with SAP SuccessFactors.



<a name="loioccd49f261d664ea4a0e8e18cdf44ddd4__context_dd4_hh3_d2b"/>

## Context

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/docs/btp/sap-business-technology-platform/sap-business-technology-platform?version=Cloud) .**

The extension management page in SAP SuccessFactors is restricted to users who have the `Extensions Admin` role. This role together with the `Extensions Administrators` group to which it is granted, are created automatically during the cofiguration of the extension integration. To manage the users that have this role, see [Using Role-Based Permissions](https://help.sap.com/viewer/b569eee64d3f4159b2b5272ba7d6b127/LATEST/en-US/c7591a6c4e8e4ea6be131330a54dca3e.html).

> ### Caution:  
> You must not rename or delete the `Extensions Administrators` group and the `Extensions Admin` permission role. Otherwise, you will not be able to use the extension management UI in SAP SuccessFactors.

