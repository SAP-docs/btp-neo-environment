<!-- loioa2877827b9f644a29e508a4d2864b2e8 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# View Directory Usage Analytics

You can explore, compare, and analyze all your actual usage data for the services and applications that are available in your directory.

To monitor and track usage in a directory, open your directory from the *Account Explorer* in the SAP BTP cockpit, and then go to the *Usage Analytics* page in the navigation area.

> ### Note:  
> This cockpit page is available only for directories that have user management enabled.
> 
> You must also be assigned as an admin of the directory. For the more information, see [Create a Directory](create-a-directory-b8ef1c4.md) and [Manage Users in Directories](manage-users-in-directories-ff4d4a4.md).



<a name="loioa2877827b9f644a29e508a4d2864b2e8__section_xyh_sjc_tdb"/>

## Views in the Directory 'Usage Analytics' Page

The directory *Usage Analytics* page contains two views that display the same usage information; however, your entry point is different – either from a service/subscription or a directory/subaccount:


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

**Service Usage** 

</td>
<td valign="top">

Displays high-level usage information for a selected service or business application subscriptions according to the directory from which you accessed the *Usage Analytics* page. You can also drill down and view usage data for specific subdirectories and subaccounts that are located in this directory.

</td>
</tr>
<tr>
<td valign="top">

**Directory/Subaccount Usage** 

</td>
<td valign="top">

Displays high-level usage information for all services and business application subscriptions according to the directory from which you accessed the *Usage Analytics* page. You can also drill down and view usage data for specific subdirectories and subaccounts that are located in this directory.

</td>
</tr>
</table>

Information is shown only for those services and subscriptions whose metered consumption in the directory is greater than zero.

Usage values are updated every 24 hours. Usage data displayed in this cockpit page refers to actual usage, not billed usage.

> ### Tip:  
> -   If your directory is in a global account that uses the consumption-based commercial model, you can view information about your billed usage for billable services in your global acccount's *Usage Analytics* page. The global account's *Usage Analytics* page also provides information about cloud-credit usage. For more information, see [Monitoring Usage and Consumption Costs in Your Global Account](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/de6f0db8919f4e6f97e54bc4ddaf2ab8.html "SAP BTP cockpit supports advanced usage and cost monitoring of services in your global account. You can compare the usage and costs of multiple services and subaccounts, see monthly trends, and drill into subaccounts and service plans for detailed information.") :arrow_upper_right:.
> -   You can also view usage information by subaccount directly in a subaccount's *Usage Analytics* page. For more information, see [View Subaccount Usage Analytics](view-subaccount-usage-analytics-8f4d9db.md).



<a name="loioa2877827b9f644a29e508a4d2864b2e8__section_ynm_hd4_tdb"/>

## Working with the Tables and Charts

Both the *Service Usage* and *Directory/Subaccount Usage* views display the usage information in tabular and chart formats.

-   The tables present accumulated usage values based on the aggregation logic of each service plan and its metric over the selected time period. The usage values are broken down by resource.
-   The charts present usage values for one or more service plans that you select in the adjacent tables.

Select a table row to display the usage information in the chart. You can also compare usage between service plans in the same service by selecting multiple rows. To compare usage, the rows items must also share the same metric.

In the charts, you can view the data as a column chart or as a line chart.

To display a larger view of a chart, choose the <span style="font-size:16px;"><span class="SAP-icons-V5"></span></span> \(Zoom\) button.

Some rounding or shortening is applied to large values. You can mouse over values in the table to view the exact values as tooltips.

**Related Information**  


[Org Administration Using the Cockpit](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/c4c25cc63ac845779f76202360f98694.html "In the Cloud Foundry enviroment, manage orgs, spaces and space quota plans using the SAP BTP cockpit.") :arrow_upper_right:

[Cloud Management Tools — Feature Set Overview](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/caf4e4e23aef4666ad8f125af393dfb2.html "Cloud management tools represent the group of technologies designed for managing SAP BTP.") :arrow_upper_right:

[Monitoring Usage and Consumption Costs in Your Global Account](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/de6f0db8919f4e6f97e54bc4ddaf2ab8.html "SAP BTP cockpit supports advanced usage and cost monitoring of services in your global account. You can compare the usage and costs of multiple services and subaccounts, see monthly trends, and drill into subaccounts and service plans for detailed information.") :arrow_upper_right:

[What Is the Consumption-Based Commercial Model?](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/7047eb4a15a84ac7be3c8612179e6d1f.html "With the consumption-based model, your organization purchases an entitlement to all current and future SAP BTP services that are eligible for this model. Throughout the duration of your contract, you have complete flexibility to turn services on and off and to switch between services as your business requires.") :arrow_upper_right:

[View Subaccount Usage Analytics](view-subaccount-usage-analytics-8f4d9db.md "You can explore, compare, and analyze all your actual usage data for the services and applications that are available in your subaccount.")

[Monitoring Usage Information Using APIs of the SAP Usage Data Management Service \[Feature Set B\]](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/bf2b3043d0474ea0a2c11c0390460d85.html "Provides information about using the Resource Consumption APIs of the SAP Usage Data Management service for SAP BTP for gathering, storing, and making usage information available for all services and applications in all regions in a cloud deployment. This information is for the purpose of central analysis, reporting, and license auditing.") :arrow_upper_right:

[Manage Users in Directories](manage-users-in-directories-ff4d4a4.md "Manage members in your directory using the SAP BTP cockpit.")

