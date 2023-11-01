<!-- loioc76fc39276dd47dc8d9c6d8bbfc6834a -->

# stop-db-hana

This command stops the specified SAP HANA tenant database on an SAP HANA tenant database \(`MDC`\) system.



```
neo stop-db-hana -a <subaccount_technical_name> -h <host> -u <e-mail_or_user> -i <database_ID>

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

SAP HANA tenant database ID

`Type`: string

</td>
</tr>
</table>



## Example

```
neo stop-db-hana -a mysubaccount -h hana.ondemand.com -u mymail@example.com -i mydb
```

**Related Information**  


[start-db-hana](start-db-hana-bf6020d.md "This command starts the specified SAP HANA tenant database on an SAP HANA tenant database (MDC ) system.")

[restart-hana](restart-hana-6b5dea0.md "Restarts an SAP HANA system or an SAP HANA database service.")

