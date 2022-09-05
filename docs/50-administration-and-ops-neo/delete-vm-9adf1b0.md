<!-- loio9adf1b0d48d84c32893196003a695cc3 -->

# delete-vm

Stops and deletes a virtual machine by name or by ID.



> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**



```
neo delete-vm --account <subaccount_technical_name> --user <e-mail_or_user> --host <host> --name <vm_name>
```

> ### Note:  
> By default, deleting a virtual machine doesn't delete its volume and volume snapshots. This gives you the option to create a new virtual machine from the remaining volume and volume snapshots, and allows you to not lose any data that was installed on the file system. For more information, see [Manage Volumes](https://help.sap.com/viewer/c746ff81651e4b8fb6efc11146091016/Cloud/en-US/a533e9cd946f4cc4b4d5973c326a685b.html "A volume is the persistent storage that is created automatically when a virtual machine is created.") :arrow_upper_right: and [Manage Volume Snapshots](https://help.sap.com/viewer/c746ff81651e4b8fb6efc11146091016/Cloud/en-US/93dd4760f72f42f6a668c903030272a4.html "You can take a snapshot of an existing virtual machine volume in your subaccount and use it to create a new virtual machine with the same file system thus saving any manual installation.") :arrow_upper_right:.

However, if you want to delete the virtual machine along with its volume and volume snapshots, you can use the `--delete-volume` and `--delete-volume-snapshots` parameters.



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

 `-i`, `--id` 



</td>
<td valign="top">

ID of the virtual machine

`Type`: string

`Condition`: Use either `--id` or `--name`



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

 `-n`, `--name` 



</td>
<td valign="top">

Name of the virtual machine

`Type`: string

`Condition`: Use either `--id` or `--name`



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
</table>


<table>
<tr>
<th valign="top" colspan="2">

Optional



</th>
</tr>
<tr>
<td valign="top">

 `-v`, `--delete-volume` 



</td>
<td valign="top">

Deletes the volume referenced by the virtual machine.



</td>
</tr>
<tr>
<td valign="top">

 `-s`, `--delete-volume-snapshots` 



</td>
<td valign="top">

Deletes all volume snapshots referenced by the virtual machine.



</td>
</tr>
<tr>
<td valign="top">

 `-f`, `--force` 



</td>
<td valign="top">

You won't be asked to confirm the deletion of the virtual machine.



</td>
</tr>
<tr>
<td valign="top">

 `-y`, `--synchronous` 



</td>
<td valign="top">

Waits until the deletion is complete.

`Type:` switch; takes no value

`Default`: off



</td>
</tr>
</table>



## Example

```
neo delete-vm --account mysubaccount --user mymail@example.com --host hana.ondemand.com --name myvm --synchronous
```

