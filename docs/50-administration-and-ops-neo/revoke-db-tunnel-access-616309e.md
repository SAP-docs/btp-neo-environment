<!-- loio616309ea0ce64065813d1400a70de402 -->

# revoke-db-tunnel-access

This command revokes database access that has been given to another subaccount.



> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of the following technology portfolios: application development; process automation; integration; data, analytics, and enterprise planning; artificial intelligence. The platform offers users the ability to turn data into business value, compose end-to-end business processes, connect entire IT landscapes, and personalize, build and extend SAP applications. This reduces the overall total cost of ownership maintaining SAP landscapes and third-party software across end-to-end business processes.") :arrow_upper_right:.**



```
neo revoke-db-tunnel-access -h <host> -u <user> -a <my subaccount> --access-token <token>
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

`-- access-token`

</td>
<td valign="top">

Access token that identifies the permission to access the database

`Type`: string

</td>
</tr>
<tr>
<td valign="top">

`--silent`

</td>
<td valign="top">

\(optional\) Suppresses the command line confirmation prompt

`Type`: boolean

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

`--output`

</td>
<td valign="top">

Confirmation that the permission for opening the database tunnel from the other subaccount to the database was successfully revoked

`Type`: string

</td>
</tr>
</table>



## Example

```
neo revoke-db-tunnel-access -h hanatrial.ondemand.com -u mymail@example.com -a mysubaccount --access-token 31t0dpim6rtxa00wx5483vqe7in8i3c1phv759w9oqrutf638l
```

**Related Information**  


[grant-db-tunnel-access](grant-db-tunnel-access-7791e70.md "This command generates a token, which allows the members of another subaccount to access a database using a database tunnel.")

[list-db-tunnel-access-grants](list-db-tunnel-access-grants-21e4be8.md "This command lists all current database access permissions for databases in other subaccounts.")

[Revoke Tunnel Access to Databases for Other Subaccounts](https://help.sap.com/viewer/3fa880aa54b74110ae99ad01503fcd60/Cloud/en-US/a583f98202c44c408646f9885b45752a.html "You can revoke the permission to open database tunnels to an SAP HANA database in your subaccount for other subaccounts in the Neo environment.") :arrow_upper_right:

