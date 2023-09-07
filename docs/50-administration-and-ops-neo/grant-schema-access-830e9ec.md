<!-- loio830e9ec114da4404bc68171772e8e707 -->

# grant-schema-access

This command gives an application in another subaccount access to a schema based on a one-time access token. The access token is used to bind the schema to the application.



> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**



```
neo grant-schema-access --host <host> --account <subaccount_technical_name> --application <application_name> --user <e-mail_or_user> --id <schema_ID> 

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

The application \(specified in the format <subaccount\>:<application\>\) to which the schema can be bound using the created token

`Type`: string



</td>
</tr>
<tr>
<td valign="top">

`-h`, `--host`



</td>
<td valign="top">

Enter a region host.

`Type`: URL. For acceptable values see [Regions](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/350356d1dc314d3199dca15bd2ab9b0e.html "You can deploy applications in different regions. Each region represents a geographical location (for example, Europe, US East) where applications, data, or services are hosted.") :arrow_upper_right:



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
neo grant-schema-access --host hanatrial.ondemand.com --account mysubaccount --application salescorp:salesapp --user mymail@example.com --id myschema
```

**Related Information**  


[list-schema-access-grants](list-schema-access-grants-371711d.md "This command lists all current schema access grants for a specified subaccount.")

[revoke-schema-access](revoke-schema-access-a92c08a.md "This command revokes the schema access granted to an application in another account.")

[Managing Access to Databases for Other Subaccounts](https://help.sap.com/viewer/3fa880aa54b74110ae99ad01503fcd60/Cloud/en-US/65d582dc5f0f4c5092acc2bedc9f636d.html "As a subaccount member with the administrator role, you can manage access to databases for other subaccounts in the Neo environment.") :arrow_upper_right:

[Sharing Databases with Other Subaccounts](https://help.sap.com/viewer/3fa880aa54b74110ae99ad01503fcd60/Cloud/en-US/322080db84734e9b8812ede13703b83c.html "You can share a SAP ASE database that is owned by a subaccount with other subaccounts in the Neo environment.") :arrow_upper_right:

[Grant Access to Schemas](https://help.sap.com/viewer/d4790b2de2f4429db6f3dff54e4d7b3a/Cloud/en-US/a3142222d2cb40b0b473f53855f571b0.html "As a subaccount member who is assigned the Administrator or Developer role, you can grant applications in other subaccounts access to any of your subaccount’s schemas in the Neo environment.") :arrow_upper_right:

[bind-schema](bind-schema-ce689b2.md "This command binds a schema to a Java application via a data source. If a data source name is not specified, the schema will be automatically bound to the default data source of the application.")

