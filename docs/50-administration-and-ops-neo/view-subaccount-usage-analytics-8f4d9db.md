<!-- loio8f4d9db9ecb34b08865c2c7a61d7719f -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# View Subaccount Usage Analytics

You can explore, compare, and analyze all your actual usage data for the services and applications that are available in your subaccount.

To monitor and track usage in a subaccount, open the subaccount in the SAP BTP cockpit and choose *Usage Analytics* in the navigation area.



<a name="loio8f4d9db9ecb34b08865c2c7a61d7719f__section_xyh_sjc_tdb"/>

## Views in the Subaccount 'Usage Analytics' Page

The subaccount *Usage Analytics* page contains views that display usage at different levels of detail:


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

**Subaccount** 

</td>
<td valign="top">

Displays high-level usage information for your subaccount relating to services and business application subscriptions.

Some information in this view is displayed only for global account admins.

</td>
</tr>
<tr>
<td valign="top">

**Services** 

</td>
<td valign="top">

Displays usage per service plan for the region of the subaccount, and the selected metric and period. Information is shown for all services whose metered consumption in the subaccount is greater than zero.

</td>
</tr>
</table>

> ### Note:  
> The information displayed in this page depends on the environments that are enabled for your subaccount. For example, information about spaces is displayed only for subaccounts in the Cloud Foundry environment.

Usage values are updated every 24 hours.

Usage data displayed in this cockpit page refers to actual usage, not billed usage.

> ### Tip:  
> -   If your subaccount is in a global account that uses the consumption-based commercial model, you can view information about your billed usage for billable services in your global acccount's *Usage Analytics* page. The global account's *Usage Analytics* page also provides information about cloud-credit usage. A directory's *Usage Analytics* page also allows you to view usage information for each subaccount that is located in the directory.
> -   If you use directories to group your subaccounts, you can view usage information by directory in your global account's *Usage Analytics* page or directly in the directory's *Usage Analytics* page.
> 
> For more information, see [Monitoring Usage and Consumption Costs in Your Global Account](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/de6f0db8919f4e6f97e54bc4ddaf2ab8.html "SAP BTP cockpit supports advanced usage and cost monitoring of services in your global account. You can compare the usage and costs of multiple services and subaccounts, see monthly trends, and drill into subaccounts and service plans for detailed information.") :arrow_upper_right: and [View Directory Usage Analytics](view-directory-usage-analytics-a287782.md).



<a name="loio8f4d9db9ecb34b08865c2c7a61d7719f__section_ynm_hd4_tdb"/>

## Working with the Tables and Charts

In the *Services* view, the usage information is displayed in both tabular and chart formats.

-   The tables present accumulated usage values based on the aggregation logic of each service plan and its metric over the selected time period. The usage values are broken down by resource.
-   The charts present usage values for one or more service plans or spaces that you select in the adjacent tables. The resolution of the charts is automatically set to days, weeks, or months, depending on the range of the selected time period.

You can perform various actions within the tables and charts:

-   In the *Services* view, select a table row to display the usage information in the chart. You can also select multiple rows to compare usage between service plans in the same service. Multi-row selection in the table is possible only when you have selected a single service in the *Service* filter and the row items share the same metric.
-   In the charts, you can view the data as a column chart or as a line chart.
-   To display a larger view of a chart, choose the <span style="font-size:16px;"><span class="SAP-icons-V5"></span></span> \(Zoom\) button.
-   Some rounding or shortening is applied to large values. You can mouse over values in the table to view the exact values as tooltips.



<a name="loio8f4d9db9ecb34b08865c2c7a61d7719f__section_xg2_mmm_wlb"/>

## Using the Filters

Use the filters in the *Services* view to choose which usage information to display.

You can apply the *Metric* filter only when you have selected a service with more than one metric.

Click the <span style="font-size:16px;"><span class="SAP-icons-V5"></span></span> \(Reset\) icon to reset the filters to their default settings.

**Related Information**  


[Org Administration Using the Cockpit](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/c4c25cc63ac845779f76202360f98694.html "In the Cloud Foundry enviroment, manage orgs, spaces and space quota plans using the SAP BTP cockpit.") :arrow_upper_right:

[Monitoring Usage and Consumption Costs in Your Global Account](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/de6f0db8919f4e6f97e54bc4ddaf2ab8.html "SAP BTP cockpit supports advanced usage and cost monitoring of services in your global account. You can compare the usage and costs of multiple services and subaccounts, see monthly trends, and drill into subaccounts and service plans for detailed information.") :arrow_upper_right:

[What Is the Consumption-Based Commercial Model?](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/7047eb4a15a84ac7be3c8612179e6d1f.html "With the consumption-based model, your organization purchases an entitlement to all current and future SAP BTP services that are eligible for this model. Throughout the duration of your contract, you have complete flexibility to turn services on and off and to switch between services as your business requires.") :arrow_upper_right:

[View Directory Usage Analytics](view-directory-usage-analytics-a287782.md "You can explore, compare, and analyze all your actual usage data for the services and applications that are available in your directory.")

[Monitoring Usage Information Using APIs of the SAP Usage Data Management Service \[Feature Set B\]](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/bf2b3043d0474ea0a2c11c0390460d85.html "Provides information about using the Resource Consumption APIs of the SAP Usage Data Management service for SAP BTP for gathering, storing, and making usage information available for all services and applications in all regions in a cloud deployment. This information is for the purpose of central analysis, reporting, and license auditing.") :arrow_upper_right:

