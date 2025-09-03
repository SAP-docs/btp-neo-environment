<!-- loioce689b2f0d4c434cb820f945a0a3ae18 -->

# bind-schema

This command binds a schema to a Java application via a data source. If a data source name is not specified, the schema will be automatically bound to the default data source of the application.



> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/docs/btp/sap-business-technology-platform/sap-business-technology-platform?version=Cloud) .**



You can only bind a schema to an application if the application is deployed.

```
neo bind-schema -a <subaccount_technical_name> -b <application_name> -h <host> -u <e-mail_or_user> -i <schema_ID>

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

`-b`, `--application` 

</td>
<td valign="top">

Application name

`Type`: string \(up to 30 characters; lowercase letters and numbers, starting with a letter\)

</td>
</tr>
<tr>
<td valign="top">

`-h`, `--host`

</td>
<td valign="top">

Enter a region host.

`Type`: URL, for acceptable values see [Regions and Hosts Available for the Neo Environment](../10-concepts-neo/regions-and-hosts-available-for-the-neo-environment-d722f7c.md)

</td>
</tr>
<tr>
<td valign="top">

`-i`, `--id`

</td>
<td valign="top">

Schema ID

`Type`: string

</td>
</tr>
<tr>
<td valign="top">

`--access-token`

</td>
<td valign="top">

Identifies a schema access grant. The access token and schema ID parameters are mutually exclusive.

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


<table>
<tr>
<th valign="top" colspan="2">

Optional

</th>
</tr>
<tr>
<td valign="top">

`-s`, `--data-source`

</td>
<td valign="top">

Data source name

The application will be able to access the schema via the specified data source.

Type: string \(uppercase and lowercase letters, numbers, and the following special characters: \`/\`, \`\_\`, \`-\`, \`@\`. Do not use special characters as first or last charachters of the data source name.\)

</td>
</tr>
</table>



## Example

```
neo bind-schema -a mysubaccount -b myapp -h hanatrial.ondemand.com -u mymail@example.com -i myschema -s datasource1
```

**Related Information**  


[Example Scenarios](https://help.sap.com/viewer/d4790b2de2f4429db6f3dff54e4d7b3a/Cloud/en-US/7e5b0443011d4b46bac953d729eadd2c.html "Perform the most typical use case scenarios in the Neo environment either in the cockpit or by using the console client.") :arrow_upper_right:

[Bind Schemas](https://help.sap.com/viewer/d4790b2de2f4429db6f3dff54e4d7b3a/Cloud/en-US/5936fbafb1384df49dd9bba7cd71219d.html "Bind a schema in the Neo environment to an application.") :arrow_upper_right:

[grant-schema-access](grant-schema-access-830e9ec.md "This command gives an application in another subaccount access to a schema based on a one-time access token. The access token is used to bind the schema to the application.")

[unbind-schema](unbind-schema-41e70ab.md "This command unbinds a schema from an application for a particular data source.")

[bind-hana-dbms](bind-hana-dbms-affa782.md "This command binds a Java application to an SAP HANA single-container database system (XS) via a data source.")

[unbind-hana-dbms](unbind-hana-dbms-de4022e.md "This command unbinds a productive SAP HANA database system from a Java application for a particular data source.")

