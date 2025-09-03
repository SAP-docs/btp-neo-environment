<!-- copy7614c98f7bce477da9bf057649c78b05 -->

# Change Subaccount Details

Edit subaccounts using the SAP BTP cockpit.



## Context

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/docs/btp/sap-business-technology-platform/sap-business-technology-platform?version=Cloud) .**

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

Parent

</td>
<td valign="top">

Change the parent of your subaccount.

When you create a subaccount, this is added as a direct child of the global account you created it in. You can change your subaccount's parent and add it to a directory, move it from one directory to another, or remove from a directory by making the global account its parent once again.

</td>
</tr>
<tr>
<td valign="top">

Used for production

</td>
<td valign="top">

\(Optional\) Select this option if your subaccount is being used for production purposes.

This does not change the configuration of your subaccount. Use this flag for your internal use to operate your production subaccounts in your global account and systems more efficiently. Your cloud operator may also use this flag to take appropriate action when handling incidents related to mission-critical accounts in production systems. Since subaccounts that are marked as used for production cannot be force deleted, this option also prevents an accidental forced deletion of the account.

Do not select this option if your account is used for non-production purposes, such as development, testing, and demos.

</td>
</tr>
<tr>
<td valign="top">

Labels

</td>
<td valign="top">

\(Optional\) Assign, change, or remove labels from your subaccount. Labels help to make organizing and filtering your subaccounts easier. For more information, see [Labels](../10-concepts-neo/account-model-722a475.md#loioe8663c08ead648faa673b0d63c5b478e).

> ### Tip:  
> -   When adding multiple values to a label, press [Enter\] after each value.
> -   When you start typing, any matching label names and values that are already assigned to other subaccounts in your global account are offered as suggestions.



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

> ### Note:  
> If you enable this setting in a subaccount that is already consuming services and subscriptions, these consumed resources will not be automatically updated to beta versions if they exist.



</td>
</tr>
</table>



<a name="copy7614c98f7bce477da9bf057649c78b05__steps_jgs_mxw_z5"/>

## Procedure

1.  Choose the subaccount for which you'd like to make changes and choose ![](images/Edit_Icon_abfe424.png) on its tile.

    You can view more details about the subaccount such as its description and additional attributes by choosing *Show More*.

2.  Make your changes and save them.


**Related Information**  


 <?sap-ot O2O class="- topic/link " href="b2a50bae5f22426ea876233e03a44bab.xml" text="" desc="" xtrc="link:1" xtrf="file:/home/builder/src/dita-all/jjq1673438782153/loio9fe952ba277c471bbad80cd40548bb84_en-US/src/content/localization/en-us/7614c98f7bce477da9bf057649c78b05.xml" output-class="" outputTopicFile="file:/home/builder/tp.net.sf.dita-ot/2.3/plugins/com.elovirta.dita.markdown_1.3.0/xsl/dita2markdownImpl.xsl" ?> 

[Using Beta Features with Subaccounts](../10-concepts-neo/account-model-722a475.md#copyb7af89ba49504c5997d409f49cc5d3ae "SAP may offer, and a customer may choose to accept access to functionality, such as a service or application, which is not generally available and has not been validated and quality assured in accordance with SAP standard processes.")

