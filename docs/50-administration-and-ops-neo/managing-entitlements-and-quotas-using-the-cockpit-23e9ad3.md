<!-- copy23e9ad3fbf3f4423aeef8f915ef54846 -->

# Managing Entitlements and Quotas Using the Cockpit

When you purchase an enterprise account, you are entitled to use a specific set of resources, such as the amount of memory that can be allocated to your applications.

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of the following technology portfolios: application development; process automation; integration; data, analytics, and enterprise planning; artificial intelligence. The platform offers users the ability to turn data into business value, compose end-to-end business processes, connect entire IT landscapes, and personalize, build and extend SAP applications. This reduces the overall total cost of ownership maintaining SAP landscapes and third-party software across end-to-end business processes.") :arrow_upper_right:.**

An entitlement equals your right to provision and consume a resource. A quota represents the numeric quantity that defines the maximum allowed consumption of that resource.

Entitlements are managed at the global account level, where services plans and their allowed quota are distributed to subaccounts, and then consumed by the subaccounts. When quota is freed at the subaccount level, it becomes available again at the global account level.

> ### Note:  
> Only global account administrators can configure entitlements and quotas for subaccounts.

There are two places in the SAP BTP cockpit where you can view entitlements and assign service plans and quotas for subaccounts - at the global account level and at the subaccount level. Depending on your permissions, you may only have access to one of these pages. You can find more details below:

**Entitlements Pages**


<table>
<tr>
<th valign="top">

Page in cockpit

</th>
<th valign="top">

Navigation Level

</th>
<th valign="top">

Visible to

</th>
<th valign="top">

Permissions

</th>
</tr>
<tr>
<td valign="top">

*Entitlements* \> *Entity Assignments*

</td>
<td valign="top">

Global account level

</td>
<td valign="top">

Global account administrators only

</td>
<td valign="top">

-   View & Edit - Global account administrators



</td>
</tr>
<tr>
<td valign="top">

*Entitlements* \> *Service Assignments*

</td>
<td valign="top">

Global account level

</td>
<td valign="top">

Global account administrators only

</td>
<td valign="top">

-   View - Global account administrators \(you cannot make changes to entitlements or quota assignments from this page\)



</td>
</tr>
<tr>
<td valign="top">

*Entitlements*

</td>
<td valign="top">

Subaccount level

</td>
<td valign="top">

Subaccount members \(regardless of whether they are also global account administrators or not\)

</td>
<td valign="top">

-   View - Subaccount members who are not global account administrators



</td>
</tr>
</table>

> ### Note:  
> You can also assign service plans to directories. These directories must be configured to manage entitlements. See [Configure Entitlements and Quotas for Directories](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/37f8871865114f44aebee3db6ac64b72.html "Distribute entitlements that are available in your global account to directories by adding service plans and their allowed quotas by using SAP BTP cockpit.") :arrow_upper_right:.
> 
> To assign plans to managed directories you must a global account administrator.
> 
> Similarly, if you're assigning plans to a subaccount that is under a directory that has the user management feature enabled, then you must be the directory administrator or a global account administrator.

The *Entitlements* \> *Entity Assignments* is where you view and edit assignments and quota from the perspective of subaccounts and directories. This page contains these views \(tabs\):


<table>
<tr>
<th valign="top">

View

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

*Manage Assignments*

</td>
<td valign="top">

Allows global account admins to distribute the entitled service plans of their global account to subaccounts and directories.

</td>
</tr>
<tr>
<td valign="top">

*View Commercial Information*

</td>
<td valign="top">

Allows global account admins and viewers to view the commercial source of their service entitlements. This feature is not available for trial accounts.

</td>
</tr>
</table>

For information about setting assignments and quota, see:

-   [Configure Entitlements and Quotas for Directories](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/37f8871865114f44aebee3db6ac64b72.html "Distribute entitlements that are available in your global account to directories by adding service plans and their allowed quotas by using SAP BTP cockpit.") :arrow_upper_right:
-   [Configure Entitlements and Quotas for Subaccounts](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/5ba357b4fa1e4de4b9fcc4ae771609da.html "Distribute the entitlements that are available in your global account by adding service plans and their allowed quotas to your subaccounts using SAP BTP cockpit.") :arrow_upper_right:

The *Entitlements* \> *Service Assignments* is where you view assignments and quota from the perspective of services. This page contains these views \(tabs\):


<table>
<tr>
<th valign="top">

View

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

*All Services*

</td>
<td valign="top">

Provides an overview of all available service entitlements of your global account.

> ### Tip:  
> The *Assigned To* column in this view shows you the total number of directories and subaccounts to which each service plan is assigned in your global account. You can click on the links in this column to quickly navigate to the selected service in the *Assignments by Service* view and display more details about these assignments.
> 
> Turn on the *Show commercial info* option to display additional columns in the main table. These columns can help you to gain a better understanding of the relationship between contractual service entitlements and the technical assets \(services and plans\) in your global account.



</td>
</tr>
<tr>
<td valign="top">

*Assignments by Service*

</td>
<td valign="top">

Allows you to choose specific services and see how their service plans are assigned to subaccounts and directories within your global account.

> ### Tip:  
> Turn on the *Show commercial info* option to display additional columns in the main table. These columns can help you to gain a better understanding of the relationship between contractual service entitlements and the technical assets \(services and plans\) in your global account.



</td>
</tr>
</table>

**Related Information**  


[Configure Entitlements and Quotas for Subaccounts](configure-entitlements-and-quotas-for-subaccounts-c90f3d5.md "Distribute the entitlements that are available in your global account by adding service plans and their allowed quotas to your subaccounts using SAP BTP cockpit.")

[Add Quotas to Subaccounts Using the Console Client](add-quotas-to-subaccounts-using-the-console-client-f073eaf.md "You can use the Neo console client to add quotas to subaccounts")

[**Troubleshooting**: Entitlement and Quota Problems](https://ga.support.sap.com/dtp/viewer/index.html#/tree/2065/actions/26547:27066)

