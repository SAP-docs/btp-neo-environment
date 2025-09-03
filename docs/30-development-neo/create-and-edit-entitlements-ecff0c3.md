<!-- loioecff0c3481d54c22a01041ff62119123 -->

# Create and Edit Entitlements

After the deployment of a solution, which is going to be provided for subscription, create the entitlements that are going to be granted to the subaccounts of the subscribers.



<a name="loioecff0c3481d54c22a01041ff62119123__prereq_btx_2xg_kz"/>

## Prerequisites

You have an administrator role for your subaccount.



## Context

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/docs/btp/sap-business-technology-platform/sap-business-technology-platform?version=Cloud) .**



<a name="loioecff0c3481d54c22a01041ff62119123__steps_whm_24l_jz"/>

## Procedure

1.  Open the solution that is provided for subscription.

2.  Choose *Entitlements* in the navigation area.

3.  Choose *New Entitlement*.

    The *New Entitlement* dialog box appears.

4.  Enter the details for the new entitlement:

    -   *Global Account ID* - the global account ID of the entitled subaccount. Consumers can obtain their global account ID by navigating to their cockpit global accounts page, and then choosing the *Show More* option on their global account tile.

        Note that by granting entitlements to a given global account, it will be accessible by all subaccounts of that global account.

    -   *Effective from* - the start date from witch the provided solution is going to be available for subscription

        > ### Note:  
        > The default value is the current date.

    -   *Granted Entitlements* - the number of subaccounts part of the global account, which are going to be able to subscribe to the provided solution

        > ### Note:  
        > Currently it is not possible to decrease the number of granted entitlements per particular global account.


5.  Choose *Save* and then *Close*.




<a name="loioecff0c3481d54c22a01041ff62119123__result_sbk_dxl_jz"/>

## Results

You have created a new entitlement for a particular global account.

<a name="task_xxl_j3m_jz"/>

<!-- task\_xxl\_j3m\_jz -->

## Edit the Number of Granted Entitlements



<a name="task_xxl_j3m_jz__prereq_c2p_s3m_jz"/>

## Prerequisites

You have an administrator role for your subaccount.

You have granted an entitlement to a particular global account.



<a name="task_xxl_j3m_jz__steps_twn_53m_jz"/>

## Procedure

1.  Open the solution that is provided for subscription.

2.  Choose *Entitlements* in the navigation area.

3.  Choose the *Edit* button under *Actions* of the entitlements you want to edit.

    The *Edit Entitlement* dialog box appears.

4.  Edit the number of granted entitlements.

    > ### Note:  
    > Currently it is not possible to decrease the number of granted entitlements per particular global account.

5.  Choose *Edit* to complete the operation.




<a name="task_xxl_j3m_jz__result_wvn_1km_jz"/>

## Results

You have edited the number of granted entitlements for a particular global account.

**Related Information**  


[Defining MTA Extension Descriptors](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/50df803465324d36851c79fd07e8972c.html "") :arrow_upper_right:

[Troubleshooting](troubleshooting-b3f6b49.md "")

[Monitor Solutions Using the Cockpit](monitor-solutions-using-the-cockpit-5d5debc.md "When deployed to your SAP BTP subaccount, a solution consists of various solution components. Each solution component originates from a certain MTA module that in turn can result in several solution components. That is, one MTA module corresponds to given solution components.")

[Delete Solutions Using the Cockpit](delete-solutions-using-the-cockpit-0f1844f.md "Delete a solution from your subaccount following the steps for the corresponding solution types.")

