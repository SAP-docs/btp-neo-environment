<!-- loio01a21776a8dc498397b8435fd185c574 -->

# create-db-ase

This command creates an ASE database with the specified ID and settings on an ASE database system.



> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/docs/btp/sap-business-technology-platform/sap-business-technology-platform?version=Cloud) .**



```
neo create-db-ase -a <subaccount_technical_name> -h <host> -u <e-mail_or_user> --dbsystem <database_system> -i <database_ID> --db-user <dbuser> --db-password <database_user_password> --db-size <database_size>
```



<a name="loio01a21776a8dc498397b8435fd185c574__section_xh2_vc5_5fb"/>

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

Subaccount technical name

`Type`: string \(up to 30 characters; lowercase letters and numbers, starting with a letter\)

</td>
</tr>
<tr>
<td valign="top">

`-h`, `--host`

</td>
<td valign="top">

Enter a region host.

`Type`: URL, for acceptable values see [Regions](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/350356d1dc314d3199dca15bd2ab9b0e.html "You can deploy applications in different regions. Each region represents a geographical location (for example, Europe, US East) where applications, data, or services are hosted.") :arrow_upper_right:

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

`-i`, `--id`

</td>
<td valign="top">

ASE database ID

`Type`: string

</td>
</tr>
<tr>
<td valign="top">

`--dbsystem`

</td>
<td valign="top">

ID of a productive ASE database system

`Type`: string

</td>
</tr>
<tr>
<td valign="top">

`--db-user`

</td>
<td valign="top">

Name of the user for the ASE database

`Type`: string \(up to 30 characters, starting with a letter\)

</td>
</tr>
<tr>
<td valign="top">

`--db-password`

</td>
<td valign="top">

Password of the database user used to access the ASE database \(optional, queried at the command prompt if omitted\)

</td>
</tr>
<tr>
<td valign="top">

`--db-size`

</td>
<td valign="top">

Size of the database in MB

> ### Note:  
> This parameter sets the maximum database size. The minimum database size is 24 MB. You receive an error if you enter a database size that exceeds the quota for this database system.
> 
> The size of the transaction log will be at least 25% of the database size you specify.



</td>
</tr>
</table>

> ### Note:  
> There is a limit to the number of databases you can create, and you'll see an error message when you reach the maximum number of databases. For more information on user database limits, see [Creating Databases](https://help.sap.com/viewer/3fa880aa54b74110ae99ad01503fcd60/Cloud/en-US/533384eda57e428f98a43815e6a11119.html "Use the cockpit to create databases on SAP ASE database systems in your subaccount in the Neo environment, and set properties, such as the database size.") :arrow_upper_right:.



## Example

```
neo create-db-ase -a mysubaccount -h hana.ondemand.com -u mymail@example.com --dbsystem mydbsys -i mydb --db-user mydbuser --db-password SECRET --db-size mydbsize
```

**Related Information**  


[Create SAP ASE Tenant Databases](https://help.sap.com/viewer/3fa880aa54b74110ae99ad01503fcd60/Cloud/en-US/d9532969173d4d9bad67ed033d5c0969.html "Use the cockpit to create an SAP ASE tenant database on an SAP ASE database system in your subaccount and assign properties like database size.") :arrow_upper_right:

[delete-db-ase](delete-db-ase-9f0785d.md "This command deletes the ASE database with the specified ID.")

