<!-- loio7791e70cdc434350bd40188ca49ab0f3 -->

# grant-db-tunnel-access

This command generates a token, which allows the members of another subaccount to access a database using a database tunnel.



> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of the following technology portfolios: application development; process automation; integration; data, analytics, and enterprise planning; artificial intelligence. The platform offers users the ability to turn data into business value, compose end-to-end business processes, connect entire IT landscapes, and personalize, build and extend SAP applications. This reduces the overall total cost of ownership maintaining SAP landscapes and third-party software across end-to-end business processes.") :arrow_upper_right:.**



```
neo grant-db-tunnel-access -h <host> -u <user> -a <my subaccount> -i <mydatabase> --to-account <other subaccount>
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

`-i`, `--id`

</td>
<td valign="top">

Database ID

`Type`: string

</td>
</tr>
<tr>
<td valign="top">

`--to-account`

</td>
<td valign="top">

Subaccount technical name

The subaccount to be granted database tunnel access, based on the access token

`Type`: string

</td>
</tr>
</table>



## Example

```
neo grant-db-tunnel-access -h hanatrial.ondemand.com -u mymail@example.com -a mysubaccount -i mydb --to-account other subaccount
```

**Related Information**  


[Give Other Subaccounts Permission to Open a Database Tunnel](https://help.sap.com/viewer/3fa880aa54b74110ae99ad01503fcd60/Cloud/en-US/6efad73a5cfa41b486348b6758a6a391.html "You can allow other subaccounts to open a tunnel to an SAP ASE database database in your subaccount in the Neo environment.") :arrow_upper_right:

[list-db-tunnel-access-grants](list-db-tunnel-access-grants-21e4be8.md "This command lists all current database access permissions for databases in other subaccounts.")

[revoke-db-tunnel-access](revoke-db-tunnel-access-616309e.md "This command revokes database access that has been given to another subaccount.")

