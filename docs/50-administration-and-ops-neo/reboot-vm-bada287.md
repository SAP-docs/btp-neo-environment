<!-- loiobada2872389b44a9a544ed058b67638a -->

# reboot-vm

Reboots a virtual machine by name or by ID. By default, the reboot is soft. You can perform a hard reboot if you use the `--hard` parameter.



> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/docs/btp/sap-business-technology-platform/sap-business-technology-platform?version=Cloud) .**



```
neo reboot-vm --account <subaccount_technical_name> --user <e-mail_or_user> --host <host> --name <vm_name>
```

or

```
neo reboot-vm --account <subaccount_technical_name> --user <e-mail_or_user> --host <host> --id <vm_id>
```



<a name="loiobada2872389b44a9a544ed058b67638a__section_fwp_lnn_q2b"/>

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

`--hard` 

</td>
<td valign="top">

Performs a hard reboot of the specified virtual machine. The hard reboot lets you force a shutdown before restarting the virtual machine.

`Type`: switch; takes no value

`Default`: soft. The soft reboot attempts to shut down gracefully and restart the virtual machine.

</td>
</tr>
</table>



<a name="loiobada2872389b44a9a544ed058b67638a__section_jy2_jpn_q2b"/>

## Examples

-   If you want to perform a soft reboot, execute one of the following two commands:

    ```
    neo reboot-vm --account mysubaccount --user mymail@example.com --host hana.ondemand.com --name myvm
    ```

    ```
    neo reboot-vm --account mysubaccount --user mymail@example.com --host hana.ondemand.com --id myvmid
    ```

-   If you want to perform a hard reboot, execute one of the following two commands:

    ```
    neo reboot-vm --account mysubaccount --user mymail@example.com --host hana.ondemand.com --name myvm --hard
    ```

    ```
    neo reboot-vm --account mysubaccount --user mymail@example.com --host hana.ondemand.com --id myvmid --hard
    ```


**Related Information**  


[Manage Virtual Machines](https://help.sap.com/viewer/c746ff81651e4b8fb6efc11146091016/Cloud/en-US/c0d2dd37428944d3b673ffdd74f3a975.html "You can create and start a virtual machine using either the SAP BTP cockpit or the console client. Then, you establish a secure communication channel to it over Secure Shell (SSH) protocol. You open an SSH tunnel and get all the communication details needed for you to log in to the virtual machine and install and maintain your software.") :arrow_upper_right:

[list-vms](list-vms-962ccbb.md "Lists all virtual machines in the specified subaccount. You can get information for a concrete virtual machine by name. The command output lists information about the virtual machine, such as size; status; SSH key; floating IP (if assigned); volume IDs.")

