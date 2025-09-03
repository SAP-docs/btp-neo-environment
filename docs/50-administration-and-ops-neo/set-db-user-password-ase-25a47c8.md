<!-- loio25a47c87925f40448a305db337ea2470 -->

# set-db-user-password-ase

This command sets a new password for an existing ASE database user and overwrites the existing password.



> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/docs/btp/sap-business-technology-platform/sap-business-technology-platform?version=Cloud) .**



```
neo set-db-user-password-ase -a <subaccount_technical_name> -h <host> -u <e-mail_or_user> -i <database_ID> --db-user <dbuser> --db-password <database_user_password>

```



<a name="loio25a47c87925f40448a305db337ea2470__section_uwl_byy_qpb"/>

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

`--db-user`

</td>
<td valign="top">

Name of the ASE database user

`Type`: string \(up to 30 characters, starting with a letter\)

</td>
</tr>
<tr>
<td valign="top">

`--db-password`

</td>
<td valign="top">

New password of the ASE database user \(optional, queried at the command prompt if omitted\).

To protect your database password, enter it only when prompted by the console client and not explicitly as a parameter in the properties file or the command line.

`Type`: string

</td>
</tr>
</table>



<a name="loio25a47c87925f40448a305db337ea2470__section_tcb_xzy_qpb"/>

## Example

```
neo set-db-user-password-ase -a mysubaccount -h hana.ondemand.com -u mymail@example.com -i mydb --db-user mydbuser --db-password SECRET
```

