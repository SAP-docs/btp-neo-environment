<!-- loioc5052684a01c4709b5f945519bc4a9f8 -->

# close-ssh-tunnel

Closes the ssh-tunnel to the specified virtual machine. If no virtual machine ID is specified, closes all tunnels.



> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**



```
neo close-ssh-tunnel --vm-id <vm_id>
```

or

```
neo close-ssh-tunnel --account <subaccount_technical_name> --user <e-mail_or_user> --host <host> --vm-name <vm_name>
```



## Parameters




<table>
<tr>
<th valign="top" colspan="2">

Required



</th>
</tr>
<tr>
<th valign="top" colspan="2">

Optional



</th>
</tr>
<tr>
<td valign="top">

`-a`, `--account`



</td>
<td valign="top">

Subaccount technical name

`Type`: string \(up to 30 characters; lowercase letters and numbers, starting with a letter\)

`Condition`: Required if you use `--vm-name`



</td>
</tr>
<tr>
<td valign="top">

`-h`, `--host`



</td>
<td valign="top">

Enter a region host.

`Type`: URL. For acceptable values, see [Regions and Hosts Available for the Neo Environment](../10-concepts-neo/regions-and-hosts-available-for-the-neo-environment-d722f7c.md).

`Condition`: Required if you use `--vm-name`



</td>
</tr>
<tr>
<td valign="top">

 `-n`, `--vm-name` 



</td>
<td valign="top">

Name of the virtual machine

`Type`: string

`Condition`: Use either `--vm-id` or `--vm-name`

`Condition`: `--vm-name` requires the following parameters:

-   `-h, --host`

-   `-u, --user`

-   `-a, --account`

-   `-p, --password`




</td>
</tr>
<tr>
<td valign="top">

 `-i`,`--vm-id` 



</td>
<td valign="top">

ID of the virtual machine

`Type`: string

If no virtual machine ID is specified, closes all tunnels.

`Condition`: Use either `--vm-id` or `--vm-name`



</td>
</tr>
<tr>
<td valign="top">

`-p`, `--password`



</td>
<td valign="top">

To protect your password, enter it only when prompted by the console client and not explicitly as a parameter in the properties file or the command line.

`Type`: string

`Condition`: Required if you use `--vm-name`



</td>
</tr>
<tr>
<td valign="top">

`-u`, `--user`



</td>
<td valign="top">

Use your email, SAP ID, or user name.

`Type`: string

`Condition`: Required if you use `--vm-name`



</td>
</tr>
<tr>
<td valign="top">

`-r`, `--port`



</td>
<td valign="top">

Port on which you want to close the SSH tunnel



</td>
</tr>
</table>



## Example

```
neo close-ssh-tunnel --vm-id myvmid --port xxxx
```

or

```
neo close-ssh-tunnel --account mysubaccount --user mymail@example.com --host hana.ondemand.com --vm-name myvmname --port xxxx
```

**Related Information**  


[open-ssh-tunnel](open-ssh-tunnel-6f8924a.md "Opens a secure tunnel to a specific virtual machine.")

[list-ssh-tunnels](list-ssh-tunnels-da73699.md "Lists the currently opened SSH tunnels on the user's machine.")

