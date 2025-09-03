<!-- loio82a99117f07d4147b4041e645eb1e6b7 -->

# delete-schema

This command deletes the specified schema, including all data it contains. A schema cannot be deleted if it is still bound to an application. To enforce the deletion, use the force parameter but bear in mind that this will also delete all bindings that still exist.



> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/docs/btp/sap-business-technology-platform/sap-business-technology-platform?version=Cloud) .**



Schema backups are kept for 14 days and may be used to restore mistakenly deleted data \(available by special request only\).

```
neo delete-schema -a <subaccount_technical_name> -h <host> -u <e-mail_or_user> -i <schema_ID>

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

`-h`, `--host`

</td>
<td valign="top">

Enter a region host.

Type: URL, for acceptable values see [Regions](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/350356d1dc314d3199dca15bd2ab9b0e.html "You can deploy applications in different regions. Each region represents a geographical location (for example, Europe, US East) where applications, data, or services are hosted.") :arrow_upper_right:

</td>
</tr>
<tr>
<td valign="top">

`-i`, `--id`

</td>
<td valign="top">

HANA database or schema ID

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


<table>
<tr>
<th valign="top" colspan="2">

Optional

</th>
</tr>
<tr>
<td valign="top">

`-f`, `--force` 

</td>
<td valign="top">

Forcefully deletes the schema, including all application bindings

`Default`: *off*

`Type`: switch, takes no value

</td>
</tr>
<tr>
<td valign="top">

`--silent`

</td>
<td valign="top">

Suppresses the command line confirmation prompt

`Default`: *off*

`Type`: switch, takes no value

</td>
</tr>
</table>



## Example

```
neo delete-schema -a mysubaccount -h hanatrial.ondemand.com -u mymail@example.com -i myschema
```

**Related Information**  


[Administering Database Schemas](https://help.sap.com/viewer/d4790b2de2f4429db6f3dff54e4d7b3a/Cloud/en-US/2040a8a60de84c09994f64f74896b18f.html "An overview of the different tasks you can perform to administer database schemas in the Neo environment.") :arrow_upper_right:

