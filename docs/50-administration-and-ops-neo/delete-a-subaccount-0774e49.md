<!-- copy0774e491af8e4ba4941cbc8f51501c22 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Delete a Subaccount

Delete subaccounts using the SAP BTP cockpit to clean up your account hierarchy, free up quota used by services in your subaccounts, and to reduce overall costs.

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**

<a name="task_r4z_jv3_bvb"/>

<!-- task\_r4z\_jv3\_bvb -->

## Delete a Subaccount \[Feature Set B\]



<a name="task_r4z_jv3_bvb__prereq_s4z_jv3_bvb"/>

## Prerequisites

-   You're a global account administrator.

-   You have removed any unused custom domains and corresponding SSL hosts and certificates. Otherwise, you may still be charged for them.

    > ### Note:  
    > A custom domain is configured on a global account level, which means that one custom domain can be part of business scenarios in several subaccounts. Before you delete a subaccount:
    > 
    > 1.  Make sure that the custom domain isn't used outside of the subaccount that you want to delete. If you are sure that it isn’t, remove the custom domain to avoid being charged for it. Once you delete the subaccount, you won't be able to remove the custom domain.
    > 
    > 2.  If the custom domain is still being used in other subaccounts, don't delete the custom domain. You can proceed with the deletion of the subaccount.
    > 
    > 
    > If you decide to remove the custom domain, see [Remove the Custom Domain](https://help.sap.com/docs/BTP/ea72206b834e4ace9cd834feed6c0e09/318a016c3a234370a60475625b947de0.html).




<a name="task_r4z_jv3_bvb__steps_u4z_jv3_bvb"/>

## Procedure

1.  In the cockpit, go to the *Account Explorer* page of your global account.

2.  In the account hierarchy, locate the subaccount that you want to delete.

3.  In the *Actions* \(<span class="SAP-icons"></span> \) context menu of the subaccount, choose *Delete*.

    > ### Caution:  
    > The cockpit uses a **force-delete** mechanism, which permanently deletes all the data in the subaccount without any recovery option. This could include productive data, such as applications, active services, subscriptions, and members. Therefore, you must use the delete function with extreme caution.
    > 
    > It is your responsibility to check if the subaccount is safe to delete.

    > ### Tip:  
    > If you are a subaccount administrator, you can go to the subaccount's *Overview* page to make sure that the subaccount does not contain important data that might be lost during the deletion process. If you are not a subaccount administrator, you can request from another subaccount administrator in your organization to check.

4.  Once you've a checked that it is safe to permanently remove the subaccount and its data, if such data exists, then you can approve the deletion operation in the *Delete Subaccount with Content* dialog box.

    > ### Note:  
    > The deletion may take a while to to complete depending on the amount of content in your subaccount. If your subaccount contains service instances, subscriptions, and runtime environments, these need to be deprovisioned as part of the purge operation, which is a timely process. After the subaccount is deleted, it could take a few more days for some related services to be deleted. Note that you won't be charged for any continued usage of these services in the subaccount during the deletion cleanup.


**Related Information**  


[Relationship Between Global Accounts and Subaccounts](../10-concepts-neo/account-model-722a475.md#copy2c2dd70587104f459b97019691480ff6 "A global account can group together different subaccounts that an administrator makes available to users. Administrators can assign the available quotas of a global account to its different subaccounts and move it between subaccounts that belong to the same global account.")

[Remove the Custom Domain](remove-the-custom-domain-318a016.md "If you do not want to use the custom domain any longer, you can remove it using the console client commands. As a result, your application will be accessible only on its default hana.ondemand.com domain and you won't be charged for the custom domain anymore.")

[Cloud Management Tools — Feature Set Overview](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/caf4e4e23aef4666ad8f125af393dfb2.html "Cloud management tools represent the group of technologies designed for managing SAP BTP.") :arrow_upper_right:

<a name="task_u4n_wn3_bvb"/>

<!-- task\_u4n\_wn3\_bvb -->

## Delete a Subaccount \[Feature Set A\]



<a name="task_u4n_wn3_bvb__prereq_v4n_wn3_bvb"/>

## Prerequisites

-   You're a global account administrator.

-   You're a subaccount security administrator.

-   The subaccount doesn't contain any active subscriptions, service instances, brokers, or platforms. Active subscriptions, service instances, brokers, or platforms can be removed by roles that are environment-specific.

-   You have removed any unused custom domains and corresponding SSL hosts and certificates. Otherwise, you may still be charged for them.

    > ### Note:  
    > A custom domain is configured on a global account level, which means that one custom domain can be part of business scenarios in several subaccounts. Before you delete a subaccount:
    > 
    > 1.  Make sure that the custom domain isn't used outside of the subaccount that you want to delete. If you are sure that it isn’t, remove the custom domain to avoid being charged for it. Once you delete the subaccount, you won't be able to remove the custom domain.
    > 
    > 2.  If the custom domain is still being used in other subaccounts, don't delete the custom domain. You can proceed with the deletion of the subaccount.




<a name="task_u4n_wn3_bvb__context_y4n_wn3_bvb"/>

## Context

To prevent accidental deletion of subaccounts and creation of orphaned data, any active subscriptions, service instances, brokers, or platforms must be removed from the subaccount before it can be deleted. Only subaccount administrators can remove such content from a subaccount.



<a name="task_u4n_wn3_bvb__steps_z4n_wn3_bvb"/>

## Procedure

1.  In the cockpit, navigate into the subaccount that you want to delete.

2.  Choose *Delete Subaccount* and confirm the operation.


**Related Information**  


[Relationship Between Global Accounts and Subaccounts](../10-concepts-neo/account-model-722a475.md#copy2c2dd70587104f459b97019691480ff6 "A global account can group together different subaccounts that an administrator makes available to users. Administrators can assign the available quotas of a global account to its different subaccounts and move it between subaccounts that belong to the same global account.")

[Remove the Custom Domain](remove-the-custom-domain-318a016.md "If you do not want to use the custom domain any longer, you can remove it using the console client commands. As a result, your application will be accessible only on its default hana.ondemand.com domain and you won't be charged for the custom domain anymore.")

[Cloud Management Tools — Feature Set Overview](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/caf4e4e23aef4666ad8f125af393dfb2.html "Cloud management tools represent the group of technologies designed for managing SAP BTP.") :arrow_upper_right:

