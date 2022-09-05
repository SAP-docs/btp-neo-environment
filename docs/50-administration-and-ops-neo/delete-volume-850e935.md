<!-- loio850e9350422848ce86b3e080dafb7bf3 -->

# delete-volume

Deletes a specified virtual machine volume.



> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**



```
neo delete-volume --id <id_of_the_volume> --account <subaccount_technical_name> --user <e-mail_or_user> --host <host>
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

`Type`: URL. For acceptable values, see [Regions](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/350356d1dc314d3199dca15bd2ab9b0e.html "You can deploy applications in different regions. Each region represents a geographical location (for example, Europe, US East) where applications, data, or services are hosted.") :arrow_upper_right:.



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

Use your email, SAP ID, or user name.

`Type`: string



</td>
</tr>
<tr>
<td valign="top">

`-v`, `--id`



</td>
<td valign="top">

Unique identifier of the volume that you want to delete

`Type`: string

`Condition`: Use either `--id` or `--name`



</td>
</tr>
<tr>
<td valign="top">

 `-n`, `--name` 



</td>
<td valign="top">

Name of the volume

`Type`: string

`Condition`: Use either `--id` or `--name`



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

 `-s`, `--delete-volume-snapshots` 



</td>
<td valign="top">

Deletes all volume snapshots referenced by the volume.



</td>
</tr>
<tr>
<td valign="top">

 `-f`, `--force` 



</td>
<td valign="top">

You won't be asked to confirm the deletion of the virtual machine volume.



</td>
</tr>
</table>



## Example

```
neo delete-volume --id myvolumeid --account mysubaccount --host hana.ondemand.com --user myemail@example.com
```

