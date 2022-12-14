<!-- copy0774e491af8e4ba4941cbc8f51501c22 -->

# Delete a Subaccount

Delete subaccounts using the SAP BTP cockpit.



<a name="copy0774e491af8e4ba4941cbc8f51501c22__prereq_dhn_pr2_qbb"/>

## Prerequisites

-   You're a global account administrator.

-   You're a subaccount security administrator.

-   The subaccount doesn't contain any active subscriptions, service instances, brokers, or platforms.

-   You have removed any unused custom domains and corresponding SSL hosts and certificates. Otherwise, you may still be charged for them.

    > ### Note:  
    > A custom domain is configured on a global account level, which means that one custom domain can be part of business scenarios in several subaccounts. Before you delete a subaccount:
    > 
    > 1.  Make sure that the custom domain isn't used outside of the subaccount that you want to delete. If you are sure that it isn’t, remove the custom domain to avoid being charged for it. Once you delete the subaccount, you won't be able to remove the custom domain.
    > 
    > 2.  If the custom domain is still being used in other subaccounts, don't delete the custom domain. You can proceed with the deletion of the subaccount.




<a name="copy0774e491af8e4ba4941cbc8f51501c22__context_usz_pr2_qbb"/>

## Context

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**

To prevent accidental deletion of subaccounts and creation of orphaned data, any active subscriptions, service instances, brokers, or platforms must be removed from the subaccount before it can be deleted. Only subaccount administrators can remove such content from a subaccount.



<a name="copy0774e491af8e4ba4941cbc8f51501c22__steps_jgs_mxw_z5"/>

## Procedure

1.  Navigate into the subaccount you want to delete.

2.  Choose the subaccount that you want to delete.

3.  Choose *Delete Subaccount* and confirm the operation.


**Related Information**  




[Relationship Between Global Accounts and Subaccounts](../10-concepts-neo/account-model-722a475.md#copy2c2dd70587104f459b97019691480ff6 "A global account can group together different subaccounts that an administrator makes available to users. Administrators can assign the available quotas of a global account to its different subaccounts and move it between subaccounts that belong to the same global account.")

