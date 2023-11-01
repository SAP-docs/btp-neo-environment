<!-- loio28a621871d5b49ddb03fd7748e6c49f9 -->

# list-db-access-permissions

This command lists the permissions that other subaccounts have for accessing databases in the specified subaccount.



> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**



```
neo list-db-access-permissions --account <subaccount_ID> --user <e-mail_or_user> --host <host> --id <database_ID> 
--to-account <to-subaccount_technical_name> --permissions <permission_type>
```



## Parameters


<table>
<tr>
<th valign="top" colspan="2">

Required

</th>
</tr>
<tr>
<td valign="top">

`-a`, `--account`

</td>
<td valign="top">

ID of the subaccount providing the database.

`Type`: string \(up to 30 characters; lowercase letters and numbers, starting with a letter\)

</td>
</tr>
<tr>
<td valign="top">

`-u`, `--user`

</td>
<td valign="top">

Use your e-mail, SAP ID, or user name

`Type`: string

</td>
</tr>
<tr>
<td valign="top">

`-p`, `--password`

</td>
<td valign="top">

To protect your password, enter it only when prompted by the console client and not explicitly as a parameter in the properties file or the command line.

`Type`: string

</td>
</tr>
<tr>
<td valign="top">

`-h`, `--host`

</td>
<td valign="top">

Enter a region host.

`Type`: URL. For acceptable values see [Regions](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/350356d1dc314d3199dca15bd2ab9b0e.html "You can deploy applications in different regions. Each region represents a geographical location (for example, Europe, US East) where applications, data, or services are hosted.") :arrow_upper_right:.

</td>
</tr>
</table>


<table>
<tr>
<th valign="top" colspan="2">

Optional

</th>
</tr>
<tr>
<td valign="top">

`-i`, `--id`

</td>
<td valign="top">

Specify a database to view the permissions only to that database.

</td>
</tr>
<tr>
<td valign="top">

`-to-account`

</td>
<td valign="top">

Specify an subaccount to view the permissions only for that subaccount.

</td>
</tr>
<tr>
<td valign="top">

`-permissions`

</td>
<td valign="top">

Filter the result by permission. Acceptable values: comma separated list of 'TUNNEL', 'BINDING'.

</td>
</tr>
</table>



## Example

```
neo list-db-access-permissions --account myProviderSubaccount --user mymail@example.com --host hana.ondemand.com --permissions TUNNEL, BINDING
```

**Related Information**  


[revoke-db-access](revoke-db-access-a0265c4.md "This command revokes the database access permissions given to another subaccount.")

[grant-db-access](grant-db-access-e7d72bf.md "This command gives another subaccount permission to access a database. The subaccount providing the permission and the subaccount receiving the permission must be part of the same global account.")

[Sharing Databases in the Same Global Account](https://help.sap.com/viewer/3fa880aa54b74110ae99ad01503fcd60/Cloud/en-US/1cc5e1efb7f640329f419b53f21c0906.html "You can share SAP ASE databases that have been provisioned in a subaccount with other subaccounts of your global account in the Neo environment.") :arrow_upper_right:

[Managing Access Permissions](https://help.sap.com/viewer/3fa880aa54b74110ae99ad01503fcd60/Cloud/en-US/9b7bb0f35d0c4b33868606448a48c13c.html "As a subaccount member with the administrator role, you can add, change, and revoke access permissions for subaccounts in your global account by using the cockpit or the console client in the Neo environment.") :arrow_upper_right:

