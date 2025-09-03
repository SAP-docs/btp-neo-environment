<!-- loio9f0785db4cbf4712a6ecfae5b3ae1055 -->

# delete-db-ase

This command deletes the ASE database with the specified ID.



> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/docs/btp/sap-business-technology-platform/sap-business-technology-platform?version=Cloud) .**



## Parameters

```
neo delete-db-ase -a <subaccount_technical_name> -h <host> -u <e-mail_or_user> -i <database_ID>

```


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
</table>


<table>
<tr>
<th valign="top" colspan="2">

Optional

</th>
</tr>
<tr>
<td valign="top">

`--force or -f`

</td>
<td valign="top">

Forcefully deletes the ASE database, including all application bindings

</td>
</tr>
<tr>
<td valign="top">

`--silent`

</td>
<td valign="top">

Suppresses the command line confirmation prompt

</td>
</tr>
</table>



## Example

```
neo delete-db-ase -a mysubaccount -h hana.ondemand.com -u mymail@example.com -i mydb
```

**Related Information**  


[create-db-ase](create-db-ase-01a2177.md "This command creates an ASE database with the specified ID and settings on an ASE database system.")

