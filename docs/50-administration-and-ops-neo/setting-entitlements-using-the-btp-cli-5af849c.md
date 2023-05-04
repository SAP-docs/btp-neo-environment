<!-- loio5af849ce877d44d3b6b861141ccabd13 -->

# Setting Entitlements Using the btp CLI

Use the SAP BTP command line interface \(btp CLI\) to set entitlements to define the functionality or permissions available for users of global accounts, directories, and subaccounts.

> ### Tip:  
> By default, all commands are executed in the global account you're logged into. To change this to a directory or subaccount, use `btp target`. See [Set a Target for Subsequent Commands with btp target](set-a-target-for-subsequent-commands-with-btp-target-720645a.md).


<table>
<tr>
<th valign="top">

Task



</th>
<th valign="top">

Run the command...



</th>
<th valign="top">

Command help



</th>
</tr>
<tr>
<td valign="top">

Get all the entitlements and quota assignments for a global account, directories, and subaccounts



</td>
<td valign="top">

`btp list accounts/entitlement`

> ### Restriction:  
> It is not possible to list the entitlements of a Neo subaccount with `btp list accounts/entitlements --subaccount <ID>`. You can, however, list the entitlements for a directory that includes Neo subaccounts with `btp list accounts/entitlements --directory <ID>`.



</td>
<td valign="top">

[btp list accounts/entitlement](https://help.sap.com/docs/BTP/btp-cli/btp-list-accounts-entitlement.html)



</td>
</tr>
<tr>
<td valign="top">

Assign or update an entitlement to a subaccount or a directory



</td>
<td valign="top">

`btp assign accounts/entitlement`



</td>
<td valign="top">

[btp assign accounts/entitlement](https://help.sap.com/docs/BTP/btp-cli/btp-assign-accounts-entitlement.html)



</td>
</tr>
</table>

**Related Information**  


[Working with Global Accounts, Directories, and Subaccounts Using the btp CLI](working-with-global-accounts-directories-and-subaccounts-using-the-btp-cli-85a683e.md "Use the SAP BTP command line interface (btp CLI) to manage operations with global accounts, directories, and subaccounts.")

[btp CLI Command Reference](https://help.sap.com/docs/BTP/btp-cli/intro.html)

[Entitlements and Quotas](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/00aa2c23479d42568b18882b1ca90d79.html "When you purchase an enterprise account, you’re entitled to use a specific set of resources, such as the amount of memory that can be allocated to your applications.") :arrow_upper_right:

