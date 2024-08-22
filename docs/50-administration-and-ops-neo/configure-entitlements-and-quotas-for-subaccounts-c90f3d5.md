<!-- copyc90f3d522ee04e65bd87cdec8808e5ce -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Configure Entitlements and Quotas for Subaccounts

Distribute the entitlements that are available in your global account by adding service plans and their allowed quotas to your subaccounts using SAP BTP cockpit.



<a name="copyc90f3d522ee04e65bd87cdec8808e5ce__prereq_rzj_njy_dcb"/>

## Prerequisites

-   You must be a global account administrator to configure subaccount assignments.

-   The service and applications that you intend to assign to your subaccounts must be entitled with the required quota to your global account.

    -   For enterprise accounts that use the subscription-based commercial model, your account receives only the services that you've already purchased and subscribed to according to your SAP BTP contract. To access additional services, at an extra cost, you can modify your contract via your sales representative or account executive.

    -   For enterprise accounts that use the consumption-based commercial model, your global account receives all pay-for-use and free services that are eligible for this commercial model.

    -   If you have a trial account, you'll receive a restricted set of free platform resources and services for a limited time period. To access additional services, you'll have to switch to an enterprise account.


-   To assign beta service plans, your subaccount must have the *Enable beta features* option selected. See [Change Subaccount Details](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/567d4a84bfdc428f8f3640e07261f73a.html "Edit subaccounts using the SAP BTP cockpit.") :arrow_upper_right:. Only applies to non-production subaccounts.




<a name="copyc90f3d522ee04e65bd87cdec8808e5ce__context_oqd_ck3_vhb"/>

## Context

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of the following technology portfolios: application development; process automation; integration; data, analytics, and enterprise planning; artificial intelligence. The platform offers users the ability to turn data into business value, compose end-to-end business processes, connect entire IT landscapes, and personalize, build and extend SAP applications. This reduces the overall total cost of ownership maintaining SAP landscapes and third-party software across end-to-end business processes.") :arrow_upper_right:.**

You can distribute assignments and quotas across subaccounts within a global account from these places in the cockpit:

-   The *Entitlements* \> *Entity Assignments* page at the global account level \(visible only to global account administrators\).
-   The *Entitlements* \> *Entity Assignments* page at the directory level by first navigating into the directory from the *Account Explorer*. This applies only subaccounts that resides in the path of a directory that is configured to manage entitlements.
-   The *Entitlements* page at the subaccount level \(visible to all subaccount members, but editable only by global account administrators\) by first navigating into the subaccount from the *Account Explorer*.

For more information, see [Managing Entitlements and Quotas Using the Cockpit](managing-entitlements-and-quotas-using-the-cockpit-23e9ad3.md).

> ### Tip:  
> To get an overview of all the services and plans available in your global account, navigate to the *Entitlements* \> *Service Assignments* page. There you can see the global usage of each service plan in the *All Services* view, as well as the detailed assignments of each service across subaccounts and directories in the *Assignments by Service* view.
> 
> -   The *Service Assignments* page is for viewing purposes only; you cannot make any assignment changes from it.
> 
> -   In the *All Services* view of this page, the *Assigned To* column shows you the total number of directories and subaccounts to which each service plan is assigned in your global account. You can click on the links in this column to quickly navigate to the selected service in the *Assignments by Service* view and display more details about these assignments.
> 
> -   You can turn on the *Show commercial info* toggle option in this page to displays additional table columns that can help you to gain a better understanding of the relationship between contractual service entitlements and the technical assets \(services and plans\) in your global account; in other words, how each entitled plan was added to your global account.
> 
> 
> If you navigate to a subaccount from the *Account Explorer*, you view its assignments in its *Overview* page view.

<a name="task_lzl_bpb_vhb"/>

<!-- task\_lzl\_bpb\_vhb -->

## Configure Assignments and Quotas from Your Global Account



<a name="task_lzl_bpb_vhb__steps_jqt_vpb_vhb"/>

## Procedure

1.  Navigate to your global account.

2.  \[Feature Set B\] Choose *Entitlements* \> *Entity Assignments* from the left hand-side navigation.

    > ### Remember:  
    > There are other ways you can access the subaccount to manage its assignments, such as navigating to the subaccount or its managed directory from the *Account Explorer*. See above for more information.

3.  Open the *Manage Assignments* view \(tab\).

    Skip this step if you have a trial account.

    > ### Tip:  
    > You can use the *View Commercial Information* view in this page to display comprehensive commercial information about the entitlements in your global account \(you cannot make assignments in this view\). Note that this view is not available for trial accounts.

4.  Select the <span class="SAP-icons-V5"></span> icon in the *Directories / Subaccounts* dropdown menu.

5.  In the *Select Subaccounts and Directories* dialog box, select all the subaccounts that you want to manage assignments.

6.  Choose *Select* to apply the filter.

    You get a table for each of the subaccounts you selected, displaying the current assignments and quota.

    > ### Tip:  
    > Under the *Service Technical Name* column, click on the <span class="SAP-icons-V5"></span> \(Service Details\) icon of any service to access its service-related links to documentation, support information, and SAP Discovery Center.

7.  Choose *Edit* to start editing assignments for a particular subaccount.

    > ### Note:  
    > You can only edit assignments for one subaccount at a time.

8.  You can now edit the assignments table:


    <table>
    <tr>
    <th valign="top">

    Action
    
    </th>
    <th valign="top">

    Steps
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    **Add new service plans to the subaccount**
    
    </td>
    <td valign="top">
    
    Choose *Add Service Plans* and from the dialog box, select the services and the service plans from each service that you would like to add to the subaccount. Choose *Add <x\> Service Plans* in the dialog box to confirm.

    Remember, the services that you see depend on the type of global account you have and your contract details \(see the prerequisites above for more information\).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    **Edit the quota for one or more assigned service plans**
    
    </td>
    <td valign="top">
    
    Use :heavy_plus_sign: and :heavy_minus_sign: in the *Quota Assignment* column to increase or decrease the quota for each service plan.

    Note some service plans do not have a numeric quota assignment. In other words, you do not assign a specific quantity but grant access to the plan by simply assigning it to the subaccount. See *Quotas* in [Managing Entitlements and Quotas Using the Cockpit](managing-entitlements-and-quotas-using-the-cockpit-23e9ad3.md).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    **Set a quota limit to unlimited service plans that use the consumption-based commercial model**
    
    </td>
    <td valign="top">
    
    The usage of most service plans is unlimited by default in global accounts that use the consumption-based commercial model. To control costs of such plans, you can set a quota limit on the service plans for this subaccount by first selecting the checkbox in the *Set Quota Limit* column.

    Now, you can increase or decrease the quota for this service plan in the *Quota Assignment* column by using :heavy_plus_sign: and :heavy_minus_sign:.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    **Delete a service plan and its quota from the subaccount**
    
    </td>
    <td valign="top">
    
    Choose :wastebasket: from the *Actions* column.
    
    </td>
    </tr>
    </table>
    
9.  Once you're done, choose *Save* to save the changes and exit edit mode for that subaccount.

10. **Optional:** Repeat steps 7 to 9 to configure assignments for the other selected subaccounts.


<a name="task_h3v_xmb_vhb"/>

<!-- task\_h3v\_xmb\_vhb -->

## Configure Assignments and Quotas from a Subaccount

If you're working in a subaccount and realize you’re missing assignments or quota, you can edit the assignments directly from that subaccount.



<a name="task_h3v_xmb_vhb__prereq_dml_p3h_jhb"/>

## Prerequisites

In addition to being a global account administrator, you must also be a member of the subaccount to be able to access that subaccount.



<a name="task_h3v_xmb_vhb__steps_j1l_3nb_vhb"/>

## Procedure

1.  Navigate into the subaccount where you would like to configure the assignments.

2.  Choose *Entitlements* from the left hand-side navigation to see the assignments for your subaccount.

3.  Choose *Edit*.

4.  You can now edit the assignments table as described in the procedure above.

5.  Once you're satisfied with the changes, choose *Save* to save and exit edit mode.


**Related Information**  


[Managing Entitlements and Quotas Using the Cockpit](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/c8248745dde24afb91479361de336111.html "When you purchase an enterprise account, you are entitled to use a specific set of resources, such as the amount of memory that can be allocated to your applications.") :arrow_upper_right:

