<!-- loioa1c73b15d03d4e2fa05d43f0080ec316 -->

# set-db-properties-hana

This command changes the properties for a SAP HANA database enabled for multitenant database container support.



> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://launchpad.support.sap.com/#/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**



```
neo set-db-properties-hana -a <subaccount_technical_name> -h <host> -u <e-mail_or_user> -i <database_ID>

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

`Type`: URL, for acceptable values see [Regions](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/350356d1dc314d3199dca15bd2ab9b0e.html "You can deploy applications in different regions. Each region represents a geographical location (for example, Europe, US East) where applications, data, or services are hosted.") :arrow_upper_right:.



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

HANA database ID

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

`--web-access` 



</td>
<td valign="top">

Enables or disables access to the HANA database from the Internet: 'enabled' \(default\), 'disabled'



</td>
</tr>
<tr>
<td valign="top">

`--dp-server`



</td>
<td valign="top">

Enables or disables the data processing server of the SAP HANA database: 'enabled', 'disabled'.



</td>
</tr>
<tr>
<td valign="top">

`--script-server`



</td>
<td valign="top">

Enables or disables the script server of the SAP HANA database: 'enabled', 'disabled'.



</td>
</tr>
<tr>
<td valign="top">

`--xsengine-mode`



</td>
<td valign="top">

Specifies how the XS engine should run: 'embedded', 'standalone'.



</td>
</tr>
<tr>
<td valign="top">

`--docstore`



</td>
<td valign="top">

Enables or disables the DocStore server of SAP HANA database: 'enabled', 'disabled'.



</td>
</tr>
</table>



## Example

```
neo set-db-properties-hana -a mysubaccount -h hana.ondemand.com -u mymail@example.com -i mydb
```

