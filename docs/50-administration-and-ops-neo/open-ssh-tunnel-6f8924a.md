<!-- loio6f8924a89b06426ea4aeac2042cd9acc -->

# open-ssh-tunnel

Opens a secure tunnel to a specific virtual machine.



> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/docs/btp/sap-business-technology-platform/sap-business-technology-platform?version=Cloud) .**



```
neo open-ssh-tunnel --account <subaccount_technical_name> --user <e-mail_or_user> --host <host> --vm-id <vm_id>
```

or

```
neo open-ssh-tunnel --account <subaccount_technical_name> --user <e-mail_or_user> --host <host> --vm-name <vm_name>
```

> ### Note:  
> The tunnel is closed automatically after 24 hours or if the command window is closed.



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

`-n`, `--vm-name` 

</td>
<td valign="top">

Name of the virtual machine

`Type`: string

`Condition`: Use either `--vm-id` or `--vm-name`

</td>
</tr>
<tr>
<td valign="top">

`-i`,`--vm-id` 

</td>
<td valign="top">

ID of the virtual machine

`Type`: string

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

`-r`, `--port`

</td>
<td valign="top">

Port on which you want to open the SSH tunnel

If not specified, the command opens the tunnel on a random port.

</td>
</tr>
</table>



## Example

```
neo open-ssh-tunnel --account mysubaccount --user mymail@example.com --host hana.ondemand.com --vm-id myvmid
```

or

```
neo open-ssh-tunnel --account mysubaccount --user mymail@example.com --host hana.ondemand.com --vm-name myvmname
```

**Related Information**  


[list-ssh-tunnels](list-ssh-tunnels-da73699.md "Lists the currently opened SSH tunnels on the user's machine.")

[close-ssh-tunnel](close-ssh-tunnel-c505268.md "Closes the ssh-tunnel to the specified virtual machine. If no virtual machine ID is specified, closes all tunnels.")

