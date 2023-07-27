<!-- loio04b5e0273c9645dbb59a4554bde5251b -->

# create-volume-snapshot

Takes a snapshot of the file system of the specified virtual machine volume. The operation is asynchronous.



> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://launchpad.support.sap.com/#/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**



```
neo create-volume-snapshot --volume-id <volume_id> --name <name_of_the_snapshot> --account <subaccount_technical_name> --user <e-mail_or_user> --host <host>
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

`-n`, `--name`



</td>
<td valign="top">

Name of the snapshot

`Type`: string. It can contain only alphanumeric characters \(0-9, a-z, A-Z\), underscore \(\_\), and hyphen \(-\). The allowed name length is between 1 and 128 characters.



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

`-v`, `--volume-id`



</td>
<td valign="top">

Unique identifier of the volume from which the snapshot will be taken

`Type`: string



</td>
</tr>
</table>



## Example

```
neo create-volume-snapshot --volume-id myvolumeid --name myvolumesnapshot --account mysubaccount --host hana.ondemand.com --user myemail@example.com
```

**Related Information**  


[Manage Volume Snapshots](https://help.sap.com/viewer/c746ff81651e4b8fb6efc11146091016/Cloud/en-US/93dd4760f72f42f6a668c903030272a4.html "You can take a snapshot of an existing virtual machine volume in your subaccount and use it to create a new virtual machine with the same file system thus saving any manual installation.") :arrow_upper_right:

[delete-volume-snapshot](delete-volume-snapshot-8536a22.md "Deletes a specified virtual machine volume snapshot.")

[display-volume-snapshot](display-volume-snapshot-a96f269.md "Shows details about the specified virtual machine volume snapshot.")

[list-volume-snapshots](list-volume-snapshots-b076212.md "Lists all volume snapshots in the specified subaccount. Use display-volume-snapshot to get information about a specific volume snapshot.")

