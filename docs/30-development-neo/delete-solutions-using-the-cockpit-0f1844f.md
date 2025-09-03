<!-- loio0f1844f268b54943b260374229534b18 -->

# Delete Solutions Using the Cockpit

Delete a solution from your subaccount following the steps for the corresponding solution types.



<a name="loio0f1844f268b54943b260374229534b18__prereq_eyz_hhr_nz"/>

## Prerequisites

You have a valid role for your subaccount as described in [Operating Solutions](operating-solutions-2abf7d4.md)



<a name="loio0f1844f268b54943b260374229534b18__context_d5c_tdy_pz"/>

## Context

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/docs/btp/sap-business-technology-platform/sap-business-technology-platform?version=Cloud) .**

> ### Note:  
> -   Some parts of the solution might be shared and used by other entities within the SAP BTP. Such parts of the solution have to be removed manually.
> -   SAP SuccessFactors roles are not deleted.
> -   Custom application destinations and subaccount destinations are also deleted.
> -   Deleted solutions and their components cannot be restored.
> -   Currently, deleting a solution that has been provided for subscription is not automated. Subaccounts consuming your provided solutions have to delete their subscribed solutions before you delete that solution from your subaccount.
> -   If the solution has been provided to you for subscription from a provider subaccount, your entitlement is not deleted. You will be able to subscribe again to the provided solution.

To delete a solution from your subaccount, proceed as described below.



<a name="loio0f1844f268b54943b260374229534b18__steps_g33_nlz_jz"/>

## Procedure

1.  In the cockpit, choose *Solutions* in the navigation area.

2.  In the solution list, select the tile of the solution you want to undeploy, and afterward choose *Delete*. As a result, the *Delete a Solution* dialog appears.

3.  Optionally, you can perform the following:

    1.  Deselect the *Delete data source bindings* checkbox.

        > ### Note:  
        > If the *Delete data source* checkbox is selected, any deployed database binding will be deleted. Note that your database credentials will not be removed from your database and can be used again.

    2.  Select the *Ignore solution component deletion errors* checkbox.

        > ### Note:  
        > If set, any errors during deletion that are external to SAP BTP \(for example, a SuccessFactors system\) are ignored.
        > 
        > Typical use case is to be able to delete a solution that is linked to a now nonexistent external system. Then, if the *Ignore solution component deletion errors* checkbox is not selected, the deletion process will fail with an error. When the *Ignore solution component deletion errors* is selected the deletion process will ignore the error and continue.

        > ### Note:  
        > If the *Ignore solution component deletion errors* checkbox is selected and an error that originates from an external to SAP BTP instance occurs, it will be ignored. As a result all the data stored in the SAP BTP for that solution will be deleted. However, external systems might still contain some data that is not deleted.


4.  Select the *Confirm solution deletion* checkbox, and choose *Delete*.

    The solution deletion dialog remains on the screen during the process. А confirmation appears when the deletion is completed.

    If you close the dialog while the process is running, you can open it again by choosing *Check Progress* of the corresponding operation, located in the *Ongoing Operations* table in the solution overview page.




<a name="loio0f1844f268b54943b260374229534b18__result_ybx_vlr_nz"/>

## Results

The solution is deleted from the SAP BTP.

**Related Information**  


[Deploying Solutions Using the Cockpit](deploying-solutions-using-the-cockpit-a5db17e.md "")

