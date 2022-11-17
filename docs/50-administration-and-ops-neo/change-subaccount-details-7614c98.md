<!-- copy7614c98f7bce477da9bf057649c78b05 -->

# Change Subaccount Details

Edit subaccounts using the SAP BTP cockpit.



## Context

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**

You edit a subaccount by choosing the relevant action on its tile. It's available in the global account view, which shows all its subaccounts.

The subaccount technical name is a unique identifier of the subaccount on SAP BTP that is generated when the subaccount is created.

You can change to the following subaccount details:

**Editable Subaccount Details**


<table>
<tr>
<th valign="top">

Field



</th>
<th valign="top">

Details



</th>
</tr>
<tr>
<td valign="top">

Display Name



</td>
<td valign="top">

Specify a human-readable name for your subaccount and change it later on, if necessary. This way you can distinguish between multiple subaccounts.



</td>
</tr>
<tr>
<td valign="top">

Description



</td>
<td valign="top">

\(Optional\) Specify a short descriptive text about the subaccount.



</td>
</tr>
<tr>
<td valign="top">

Used for production



</td>
<td valign="top">

Select this option if your subaccount is being used for production purposes.

This does not change the configuration of your subaccount. Use this flag for your internal use to operate your production subaccounts in your global account and systems more efficiently. Your cloud operator may also use this flag to take appropriate action when handling incidents related to mission-critical accounts in production systems.

Do not select this option if your account is used for non-production purposes, such as development, testing, and demos.



</td>
</tr>
<tr>
<td valign="top">

Enable beta features



</td>
<td valign="top">

\(Optional\) Enable the subaccount to use services and applications which are occasionally made available by SAP for beta usage on SAP BTP. This option is available to administrators only and is, by default, unselected.

> ### Caution:  
> You shouldn't use SAP BTP beta features in subaccounts that belong to productive enterprise accounts. For more information, see [Important Disclaimers and Legal Information](https://help.sap.com/viewer/disclaimer).

> ### Note:  
> Once you have enabled this setting in a subaccount you cannot disable it.



</td>
</tr>
</table>



<a name="copy7614c98f7bce477da9bf057649c78b05__steps_jgs_mxw_z5"/>

## Procedure

1.  Choose the subaccount for which you'd like to make changes and choose ![](images/Edit_Icon_abfe424.png) on its tile.

    You can view more details about the subaccount such as its description and additional attributes by choosing *Show More*.

2.  Make your changes and save them.


**Related Information**  




[Using Beta Features with Subaccounts](../10-concepts-neo/account-model-722a475.md#copyb7af89ba49504c5997d409f49cc5d3ae "SAP may offer, and a customer may choose to accept access to functionality, such as a service or application, which is not generally available and has not been validated and quality assured in accordance with SAP standard processes.")

