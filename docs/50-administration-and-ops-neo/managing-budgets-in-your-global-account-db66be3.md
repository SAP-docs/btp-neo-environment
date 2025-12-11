<!-- copydb66be3430664b57bc50bda73b423a65 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Managing Budgets in Your Global Account

Budgets allow you to better control your global account spending and plan for future consumption by setting up budget limits for your global account in SAP BTP.

Automatic email alerts notify global account administrators when spending exceeds defined thresholds, allowing for timely intervention. You can also leverage the SAP Alert Notification service for SAP BTP to create custom alerts according to your specific monitoring needs.

> ### Tip:  
> Remember to periodically review your budget settings and thresholds to ensure proactive financial management.



<a name="copydb66be3430664b57bc50bda73b423a65__section_wbk_2b4_hfc"/>

## Important Information

When you use budgets in your global account, please note the following important details:

-   Costs and usage values between the last balance statement and the current date are estimates and may change at the end of the month when the actual overall global account usage is aggregated for billing purposes. SAP does not guarantee the accuracy or reliability of real-time alerts based on these estimates. It is your responsibility to review and validate alerts before you make any decisions based on them.

-   The system doesn’t suspend costs and service usage when a budget amount or threshold is exceeded. It’s your responsibility to take the appropriate action within the global account to prevent overages.

-   There may be a delay between the time a budget threshold was exceeded and the time that you receive a notification. This may be due to delays in the update cycles of costs and service usage, as well as the periodic evaluations of budgets against your global account costs and usage.

-   If your global account combines both subscription and consumption-based commercial models, then any usage that falls within your prepaid quota, as defined by your subscription-based commercial agreement, is not evaluated by your budget.


<a name="copy7a771b37e3684850aa11f0650a4ff653"/>

<!-- copy7a771b37e3684850aa11f0650a4ff653 -->

## Accessing Your Global Account's Budgets

Access and manage your global account's budgets in SAP BTP cockpit. Monitor spending, view active and expired budgets, and configure table columns.



<a name="copy7a771b37e3684850aa11f0650a4ff653__prereq_xzv_cbq_hfc"/>

## Prerequisites

-   Your global account uses the SAP BTP Enterprise Agreement \(SAP BTPEA\), Cloud Platform Enterprise Agreement \(CPEA\), or Pay-As-You-Go for SAP BTP flavor of the consumption-based commercial model, or it combines one of these consumption-based flavors with the subscription-based commercial model.

    Note that the use of the consumption-based commercial model is subject to its availability in your country or region.

-   You must also be a global account administrator or global account viewer.




## Procedure

1.  Open SAP BTP cockpit.

2.  From the global account level, go to the *Costs and Usage* page.

3.  Click on the *Budgets* tab.

    The *Budgets* tab shows your global account's budgets in two separate tables:

    -   **Active Budgets**: All budgets that are currently active and monitoring spending in your global account.

        > ### Tip:  
        > Choose the *View in Billing Tab* action in the <span class="SAP-icons-V5"></span> \(Actions\) context menu of a budget to quickly open the Billing tab. This tab is then automatically filtered by the subaccounts and service plans defined in the budget's scope.

    -   **Expired Budgets**: All budgets whose end date surpasses the current date. Expired budgets are no longer active in your global account and don’t send alerts or events.


    > ### Tip:  
    > Click :gear: to set the columns you want to view in each table.

4.  Click on a budget to view its configuration and *History* chart.


<a name="copy7e1a74b115cf4b24b396eaec6ec375ed"/>

<!-- copy7e1a74b115cf4b24b396eaec6ec375ed -->

## Understanding Budget Settings



A budget configuration includes several settings:


<table>
<tr>
<th valign="top">

Setting

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

Budget Name and Description

</td>
<td valign="top">

A unique display name and short description for the budget.

</td>
</tr>
<tr>
<td valign="top">

Monthly Budget Amount

</td>
<td valign="top">

The amount allocated to the budget per month.

-   When the budget type \(see `Budget Type`\) is set to *Cost*, the specified amount represents a monetary value in the same currency as that of the global account.

-   When the budget type is set to *Charged Usage*, the specified amount corresponds to the unit of the metric \(for example: `API Calls`\) of the selected service plan \(see `Scope`\).




</td>
</tr>
<tr>
<td valign="top">

Time Period

</td>
<td valign="top">

Includes the budget start date and optional end date.

A budget without an end date never expires. Note however, that you are allowed up to 10 active budgets per global account.

</td>
</tr>
<tr>
<td valign="top">

Budget Type

</td>
<td valign="top">

Determines the type of data that the budget is based on:

-   *Cost*: The budget is based on list price data as shown in the *Billing* tab.

-   *Charged Usage*: The budget is based on charged usage data as shown in the *Billing* tab.




</td>
</tr>
<tr>
<td valign="top">

Scope

</td>
<td valign="top">

Determines which subaccounts and service plans in the global account are monitored by the set budget:

-   *Subacounts*: By default, the budget's scope covers all subaccounts, but you can choose specific subaccounts to monitor.

-   *Service Plans*: The service plans that are monitored by the budget depend on the budget's type:

    -   When the budget type is set to *Cost*, then by default all services and their plans are covered in the budget's scope, but you can choose specific plans to monitor.

    -   When the budget type is set to *Charged Usage*, you must specify a single service plan to be monitored by the budget. If a particular plan has multiple metrics, then you must choose a specific metric.


    > ### Note:  
    > You can only choose from services that currently have registered usage in your global account.




</td>
</tr>
<tr>
<td valign="top">

Budget Thresholds

</td>
<td valign="top">

\(Optional\) Define up to three threshold percentages ranging from 1% to 120% relative to the monthly budget amount.

When you configure a budget threshold and enable it \(by selecting its checkbox\), the threshold value is displayed over the *History* chart when you view a budget's details in the cockpit.

Additionally, you can:

-   Opt-in to send automatic email notifications to global account administrators when a threshold is exceeded.

-   Use the SAP Alert Notification service for SAP BTP to set up customized alerts for your preferred recipients, communication channels, and monitoring solutions.


For more information, see [Setting Up Budget Threshold Alerts](managing-budgets-in-your-global-account-db66be3.md#copy72b64bf5f5d34a1283e2de34a61b69cd).

</td>
</tr>
</table>

<a name="copycf3dfa6d15ca48908ac8ca758f3908e1"/>

<!-- copycf3dfa6d15ca48908ac8ca758f3908e1 -->

## Creating a Budget

Creating a budget allows you to monitor and manage spending in your global account. You can create a budget from scratch or from an existing budget that is active or has expired.

Each global account is allowed up to 10 active budgets. Active budgets have an end date in the future or no end date. Budgets expire automatically when the current date surpasses the end date of the budget.



## Procedure

1.  In the *Budgets* tab, click *Create*.

    > ### Tip:  
    > To duplicate a previous budget configuration, choose *Create as New Budget* in the budget's <span class="SAP-icons-V5"></span> \(Actions\) context menu. Note that when you use this option to create a new budget, you cannot change the budget type.

2.  Configure the budget's settings.

    For detailed information about each of the budget settings, see [Understanding Budget Settings](managing-budgets-in-your-global-account-db66be3.md#copy7e1a74b115cf4b24b396eaec6ec375ed).

    1.  Enter the budget name and an optional description.

    2.  Choose the budget type: *Cost* or *Charged Usage*.

    3.  \(Optional\) Define the budget's scope by selecting the applicable subaccounts and service plans.

    4.  Specify the budget amount.

    5.  Set the time period by entering the start date and optionally the end date. You cannot enter a start date that is in the past.

    6.  \(Optional\) Set up to three budget thresholds.


3.  View the budget amount and threshold in the *History Preview* chart below the *Scopes* section.

4.  Review your configuration and then click *Create*.


<a name="copyf8773fe63ce54820bbf7ac04dca28199"/>

<!-- copyf8773fe63ce54820bbf7ac04dca28199 -->

## Viewing a Budget's Details

Viewing a budget provides detailed information about the budget's configuration and status.



## Procedure

In the *Budgets* tab, click on a budget to display more details.

For detailed information about each of the budget settings, see [Understanding Budget Settings](managing-budgets-in-your-global-account-db66be3.md#copy7e1a74b115cf4b24b396eaec6ec375ed).

Use the *History* chart below the *Scopes* section to view the costs or charged usage in your global account over the past 12 months. The budget amount and threshold values are overlaid on the chart data, including budget exceedance information, if relevant.

<a name="copy80ba5a4bac9245c694874f1bee791107"/>

<!-- copy80ba5a4bac9245c694874f1bee791107 -->

## Editing a Budget

Editing a budget allows you to make changes to the budget's settings.

> ### Note:  
> When you make changes to an existing budget, previously sent alerts may not accurately reflect the new budget settings.
> 
> Any changes you make to budget amount will trigger alerts from the current month onward, not retroactively.



## Procedure

1.  In the *Budgets* tab, go to the Active Budgets table.

2.  Choose *Edit* in the budget's <span class="SAP-icons-V5"></span> \(Actions\) context menu.

3.  Make changes to the budget's editable settings.

    Note that you cannot change the start date and budget type of an existing budget.

    For detailed information about each of the budget settings, see [Understanding Budget Settings](managing-budgets-in-your-global-account-db66be3.md#copy7e1a74b115cf4b24b396eaec6ec375ed).

4.  Review your configuration and then click *Update*.

    > ### Tip:  
    > Whenever you change a budget's settings, we recommend you review and update your threshold values carefully to ensure they align with the new budget settings.


<a name="copyba54f4908e2646149ddc5cef3ad84d1f"/>

<!-- copyba54f4908e2646149ddc5cef3ad84d1f -->

## Deleting a Budget

Deleting a budget removes it permanently from your global account. Deleted budgets cannot be retrieved.

Before deleting a budget, we recommended that you first check with the user that created the budget. Open the budget's details to view this information.



## Procedure

1.  Go to the *Budgets* tab.

2.  Choose *Delete* in the budget's <span class="SAP-icons-V5"></span> \(Actions\) context menu.

3.  Confirm the delete action.


<a name="copy72b64bf5f5d34a1283e2de34a61b69cd"/>

<!-- copy72b64bf5f5d34a1283e2de34a61b69cd -->

## Setting Up Budget Threshold Alerts

Besides regularly checking the status and history graphs of active budgets for up-to-date information on spending, you can also configure alerts to notify relevant users and/or channels in your organization when a budget's threshold is exceeded.



Before you can set up the threshold alerts for an active budget, you first need to configure the threshold values in your budget's configuration. You can define up to three budget thresholds per budget. For example: 70%, 90%, and 100% of the monthly budget amount, respectively.

Then, once you've enabled these threshold values \(by selecting their checkboxes\), you can set up the following alert types:


<table>
<tr>
<th valign="top">

Alert Type

</th>
<th valign="top">

Description

</th>
<th valign="top">

Action Required

</th>
</tr>
<tr>
<td valign="top">

Automatic Alerts

</td>
<td valign="top">

Whenever a budget's threshold value is exceeded, the system automatically sends an email to all administrators of the global account.

This option is free of charge and requires no additional setup besides enabling the opt-in switch in the budget's configuration. By default, it is turned off per budget.

> ### Note:  
> You cannot customize the content of the email and to which global account administrators the email is sent.



</td>
<td valign="top">

Edit your budget, and then in the *Budget Thresholds* section, turn on the *Send alerts automatically to global account admins* option.

> ### Tip:  
> If you don't receive any emails, please check your spam or junk folder. You can also add the `btp.budgets@notifications.sap.com` to your address book or safe senders list.



</td>
</tr>
<tr>
<td valign="top">

Custom Alerts

</td>
<td valign="top">

Whenever a budget's threshold value is exceeded, we also automatically send an event to the SAP Alert Notification service for SAP BTP.

You can integrate with SAP Alert Notification Service to send custom alerts to your preferred recipients, communication channels, and monitoring solutions. This is a paid service. For pricing information, go to the [SAP Discovery Center](https://discovery-center.cloud.sap/serviceCatalog/sap-alert-notification-service).

> ### Note:  
> If you turn off the *Send alerts automatically to global account admins* option, budget events are still sent to the SAP Alert Notification Service when an enabled threshold is exceeded.



</td>
<td valign="top">

Subscribe to the budget events \(`BudgetAlertThresholdExceeded`\) using your own SAP Alert Notification Service instance and configure the custom alerts, as needed.

For more information, see:

-   [SAP Alert Notification for SAP BTP](https://help.sap.com/docs/alert-notification/sap-alert-notification-for-sap-btp/what-is-sap-alert-notification-service-for-sap-btp?version=Cloud)
-   [Budget Threshold Exceedance Event](https://help.sap.com/docs/alert-notification/sap-alert-notification-for-sap-btp/budget-threshold-exceedance?version=Cloud)



</td>
</tr>
</table>

**When working with budget threshold alerts, please consider the following:**

-   These alert types are independent of one another, you can use either one or both.

-   When you enable a threshold or change the budget amount in an existing budget, alerts will be triggered from the current month onward, not retroactively for previous months.

-   The automated mail and budget events are sent only once when a budget threshold is exceeded. We do not send a daily recurring email or event while the budget remains in excess.

-   If a set budget amount is exceeded and you haven't set a 100% threshold value nor opted to use any of the available alert types, you won't be automatically notified about the budget exceedance.

-   There may be a delay between the time a budget threshold was exceeded and the time that you receive an alert. This is due to delays between cost and service usage update cycles, along with the interval-based evaluations between budgets and your global account's overall costs and usage.

**Related Information**  


[Monitoring Usage and Consumption Costs in Your Global Account](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/de6f0db8919f4e6f97e54bc4ddaf2ab8.html "SAP BTP cockpit supports advanced usage and cost monitoring of services in your global account. You can compare the usage and costs of multiple services and subaccounts, see monthly trends, and drill down into subaccounts and service plans for detailed information.") :arrow_upper_right:

[SAP Alert Notification Service for SAP BTP](https://help.sap.com/docs/alert-notification/sap-alert-notification-for-sap-btp/what-is-sap-alert-notification-service-for-sap-btp?version=Cloud)

[Budget Threshold Exceedance Event](https://help.sap.com/docs/alert-notification/sap-alert-notification-for-sap-btp/budget-threshold-exceedance?version=Cloud)

