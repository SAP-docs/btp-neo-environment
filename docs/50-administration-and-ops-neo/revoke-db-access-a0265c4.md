<!-- loioa0265c4b575843e9904056c8a1cda28d -->

# revoke-db-access

This command revokes the database access permissions given to another subaccount.



> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of the following technology portfolios: application development; process automation; integration; data, analytics, and enterprise planning; artificial intelligence. The platform offers users the ability to turn data into business value, compose end-to-end business processes, connect entire IT landscapes, and personalize, build and extend SAP applications. This reduces the overall total cost of ownership maintaining SAP landscapes and third-party software across end-to-end business processes.") :arrow_upper_right:.**



```
neo revoke-db-access --account <subaccount_ID> --user <e-mail_or_user> --host <host> --id <database_ID> 
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

ID of the database to which access will be revoked.

</td>
</tr>
<tr>
<td valign="top">

`-to-account`

</td>
<td valign="top">

The subaccount from which access permissions will be revoked.

</td>
</tr>
<tr>
<td valign="top">

`-permissions`

</td>
<td valign="top">

Comma-separated list of ther permissions to be revoked. Acceptable values: 'TUNNEL', 'BINDING'.

</td>
</tr>
</table>



## Example

```
neo revoke-db-access --account myProviderSubaccount --user mymail@example.com --host hana.ondemand.com --id myDB --to-account myConsumerSubaccount --permissions BINDING
```

**Related Information**  


[grant-db-access](grant-db-access-e7d72bf.md "This command gives another subaccount permission to access a database. The subaccount providing the permission and the subaccount receiving the permission must be part of the same global account.")

[list-db-access-permissions](list-db-access-permissions-28a6218.md "This command lists the permissions that other subaccounts have for accessing databases in the specified subaccount.")

[Managing Access Permissions](https://help.sap.com/viewer/3fa880aa54b74110ae99ad01503fcd60/Cloud/en-US/9b7bb0f35d0c4b33868606448a48c13c.html "As a subaccount member with the administrator role, you can add, change, and revoke access permissions for subaccounts in your global account by using the cockpit or the console client in the Neo environment.") :arrow_upper_right:

[Sharing Databases in the Same Global Account](https://help.sap.com/viewer/3fa880aa54b74110ae99ad01503fcd60/Cloud/en-US/1cc5e1efb7f640329f419b53f21c0906.html "You can share SAP ASE databases that have been provisioned in a subaccount with other subaccounts of your global account in the Neo environment.") :arrow_upper_right:

