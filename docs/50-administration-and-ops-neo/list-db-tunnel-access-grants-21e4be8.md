<!-- loio21e4be85b52448d0ad259a93fd6f51fd -->

# list-db-tunnel-access-grants

This command lists all current database access permissions for databases in other subaccounts.



> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**



```
neo list-db-tunnel-access-grants -h <host> -u <user> -a <my subaccount>
```

> ### Note:  
> The list does not include access permissions that have been revoked.



## Parameters


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

\(Optional\) Database ID

Lists only the access permissions for the specified database

`Type`: string



</td>
</tr>
</table>



## Example

```
neo list-db-tunnel-access-grants -a mysubaccount -h hanatrial.ondemand.com -u mymail@example.com -i mydb
```

The table below shows the currently active database tunnel access permissions:


<table>
<tr>
<th valign="top">

Database ID



</th>
<th valign="top">

Granted To



</th>
<th valign="top">

Access Token



</th>
</tr>
<tr>
<td valign="top">

myownhana



</td>
<td valign="top">

acmecorp



</td>
<td valign="top">

31t0dpim6rtxa00wx5483vqe7in8i3c1phv759w9oqrutf638l



</td>
</tr>
<tr>
<td valign="top">

myotherhana



</td>
<td valign="top">

acmetest



</td>
<td valign="top">

vm6431dhjcr2e3dbt0fk6jpzm2w7oo3q48yumf1c6uu8b9pt9z



</td>
</tr>
</table>

**Related Information**  


[revoke-db-tunnel-access](revoke-db-tunnel-access-616309e.md "This command revokes database access that has been given to another subaccount.")

[grant-db-tunnel-access](grant-db-tunnel-access-7791e70.md "This command generates a token, which allows the members of another subaccount to access a database using a database tunnel.")

[Give Other Subaccounts Permission to Open a Database Tunnel](https://help.sap.com/viewer/3fa880aa54b74110ae99ad01503fcd60/Cloud/en-US/6efad73a5cfa41b486348b6758a6a391.html "You can allow other subaccounts to open a tunnel to an SAP ASE database database in your subaccount in the Neo environment.") :arrow_upper_right:

