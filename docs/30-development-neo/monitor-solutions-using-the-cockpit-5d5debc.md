<!-- loio5d5debce48ce42bf9d10ac050d4c2c74 -->

# Monitor Solutions Using the Cockpit

When deployed to your SAP BTP subaccount, a solution consists of various solution components. Each solution component originates from a certain MTA module that in turn can result in several solution components. That is, one MTA module corresponds to given solution components.



<a name="loio5d5debce48ce42bf9d10ac050d4c2c74__prereq_vrr_t4r_nz"/>

## Prerequisites

You have a valid role for your subaccount as described in [Operating Solutions](operating-solutions-2abf7d4.md)



## Context

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**



<a name="loio5d5debce48ce42bf9d10ac050d4c2c74__steps_q5h_ch5_jz"/>

## Procedure

1.  To see a status overview of an individual solution or solution components in your subaccount, proceed as follows:

2.  Log on to the SAP BTP and select a subaccount.

3.  In the cockpit, choose *Solutions* in the navigation area.

    You can monitor the overall status of the deployed and available for subscription solutions.

    > ### Note:  
    > The overall status of a solution is a combination of the statuses of all its internal parts and the statuses of any ongoing operations for that particular solution.

4.  In the solution list, select the tile of the solution for which you want to see details.

    > ### Note:  
    > If you have selected a solution that is available for subscription but not yet subscribed to, you can monitor only a limited set of its properties.

    The following details are available:

    -   Overview - it displays the solution name and status. For more information about the solution states, see *Solutions* page help in the cockpit.
    -   Description - a short descriptive text about the solution, typically stating what it does.
    -   Additional Information- contains information about the provisioning type, the provider's subaccount, and the organization.
    -   Ongoing Operations - the ongoing operations for the solution.
    -   Solution components - a list of the components that are part of the solution, the states of these components and their types.

    For more information about the possible states of a solution component and what they mean, see your Solution page help in the cockpit.

5.  If you have provided a solution that is available for subscription to another subaccount, you can monitor the licenses and subscribers of a provided solution as follows:

    1.  In the solution list under the *Solutions Provided for Subscription* category, select the tile of the solution for which you want to see details.

    2.  Choose *Entitlement* in the navigation area of the cockpit.

        You can monitor the granted entitlements for that solution as well as the parts that were deployed to the subscribers subaccounts.

        > ### Note:  
        > Monitoring granted licenses is only available for you if you have the subaccount administrator role.





<a name="loio5d5debce48ce42bf9d10ac050d4c2c74__result_ktx_ppr_nz"/>

## Results

Depending on the solution type, the following components can be monitored:

<a name="loio5d5debce48ce42bf9d10ac050d4c2c74__table_jry_vlj_ty"/>Solution Components


<table>
<tr>
<th valign="top" rowspan="2">

MTA Modules



</th>
<th valign="top" colspan="3">

Results in One or More of the Following Solution Components



</th>
</tr>
<tr>
<th valign="top">

Standard Solution



</th>
<th valign="top">

Provided Solution



</th>
<th valign="top">

Subscribed Solution



</th>
</tr>
<tr>
<td valign="top">

`com.sap.java`



</td>
<td valign="top">

-   Java Application
-   Data Source Binding
-   SAP SuccessFactorss Connection
-   SAP SuccessFactors Homepage Tile
-   SAP SuccessFactors Application Access
-   SAP SuccessFactors Role Provider
-   Subaccount Destination



</td>
<td valign="top">

-   Java Application
-   Database Binding
-   Subaccount Destination



</td>
<td valign="top">

-   Java Application Subscription
-   SAP SuccessFactors Application Access
-   SAP SuccessFactors Homepage Tile
-   SAP SuccessFactors Role Provider
-   SAP SuccessFactors Connection
-   Subaccount Subscription Destination



</td>
</tr>
<tr>
<td valign="top">

`com.sap.hcp.html5`



</td>
<td valign="top">

-   HTML5 Application
-   SAP SuccessFactors Application Access
-   SAP SuccessFactors Homepage Tile



</td>
<td valign="top">

HTML5 Application



</td>
<td valign="top">

-   HTML5 Application Subscription
-   SAP SuccessFactors Application Access
-   SuccessFactors Homepage Tile



</td>
</tr>
<tr>
<td valign="top">

`com.sap.fiori`



</td>
<td valign="top">

Fiori Content



</td>
<td valign="top">

Fiori Content



</td>
<td valign="top">

Fiori Content



</td>
</tr>
<tr>
<td valign="top">

`com.sap.fiori.app`



</td>
<td valign="top">

HTML5 Application



</td>
<td valign="top">

HTML5 Application



</td>
<td valign="top">

HTML5 Application Subscription



</td>
</tr>
<tr>
<td valign="top">

`com.sap.fiori.role`



</td>
<td valign="top">

Role



</td>
<td valign="top">

Role



</td>
<td valign="top">

Role



</td>
</tr>
<tr>
<td valign="top">

`com.sap.odp.config`



</td>
<td valign="top">

OData Service



</td>
<td valign="top">

OData Service



</td>
<td valign="top">

OData Service



</td>
</tr>
<tr>
<td valign="top">

`com.sap.hcp.sfsf-roles`



</td>
<td valign="top">

SAP SuccessFactors Role



</td>
<td valign="top">

 



</td>
<td valign="top">

SAP SuccessFactors Role



</td>
</tr>
<tr>
<td valign="top">

`com.sap.hcp.destination`



</td>
<td valign="top">

Subaccount Destination



</td>
<td valign="top">

Subaccount Destination



</td>
<td valign="top">

Subaccount Destination



</td>
</tr>
</table>

**Related Information**  


[Deploying Solutions Using the Cockpit](deploying-solutions-using-the-cockpit-a5db17e.md "")

