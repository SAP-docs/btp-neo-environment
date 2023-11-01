<!-- loio05ebe394ab3f491380209e4df3713662 -->

# create-schema

This command creates a HANA database or schema with the specified ID on a shared or dedicated database.



> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**



> ### Caution:  
> This command is not supported for productive SAP HANA database systems. For more information about how to create schemas on productive SAP HANA database systems, see [Binding SAP HANA Databases to Java Applications](https://help.sap.com/viewer/d4790b2de2f4429db6f3dff54e4d7b3a/Cloud/en-US/1742986c3cfa47099442aee0cf8df5e9.html "Establish a data source binding between your applications and the SAP HANA database in the Neo environment using the SAP BTP cockpit or the console client.") :arrow_upper_right:.



```
neo create-schema --account <subaccount_technical_name> --host <host> --id <schema_ID> --user <e-mail_or_user> --dbtype <database_type>

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

Subaccount technical name

`Type`: string \(up to 30 characters; lowercase letters and numbers, starting with a letter\)

</td>
</tr>
<tr>
<td valign="top">

`-d`, `--dbtype`

</td>
<td valign="top">

Creates the HANA database or schema on a shared database system. Syntax: 'type:version'. Version is optional.

Available database types: 'MaxDB', 'HANA', and 'HANAXS' \(case-insensitive\)

To see which versions are available, execute the `list-dbms` command.

`Type`: string

</td>
</tr>
<tr>
<td valign="top">

`--dbsystem`

</td>
<td valign="top">

Creates the schema on a dedicated database system. To see the available dedicated database systems, execute the `list-dbms` command.

`Type`: string

> ### Caution:  
> The `list-dbms` command lists different database types, including productive SAP HANA database systems. Do not use the `create-schema` command for productive SAP HANA database systems. For more information about how to create schemas on productive SAP HANA database systems, see [Binding SAP HANA Databases to Java Applications](https://help.sap.com/viewer/d4790b2de2f4429db6f3dff54e4d7b3a/Cloud/en-US/1742986c3cfa47099442aee0cf8df5e9.html "Establish a data source binding between your applications and the SAP HANA database in the Neo environment using the SAP BTP cockpit or the console client.") :arrow_upper_right:.



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

`-i`, `--id`

</td>
<td valign="top">

HANA database or schema ID

It must start with a letter and can contain lowercase letters \('a' - 'z'\) and numbers \('0' - '9'\). For schemas IDs, uppercase letters \('A' - 'Z'\) and the special characters '.' and '-' are also allowed.

The ID must be unique within the subaccount.

Note that the actual ID assigned in the database will be different to this version.

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

`-u`, `--user`

</td>
<td valign="top">

Use your e-mail, SAP ID, or user name

`Type`: string

</td>
</tr>
</table>



## Example

```
neo create-schema --account mysubaccount --host hanatrial.ondemand.com -i myschema --user mymail@example.com --dbtype hana
```

**Related Information**  


[Example Scenarios](https://help.sap.com/viewer/d4790b2de2f4429db6f3dff54e4d7b3a/Cloud/en-US/7e5b0443011d4b46bac953d729eadd2c.html "Perform the most typical use case scenarios in the Neo environment either in the cockpit or by using the console client.") :arrow_upper_right:

[Administering Database Schemas](https://help.sap.com/viewer/d4790b2de2f4429db6f3dff54e4d7b3a/Cloud/en-US/2040a8a60de84c09994f64f74896b18f.html "An overview of the different tasks you can perform to administer database schemas in the Neo environment.") :arrow_upper_right:

