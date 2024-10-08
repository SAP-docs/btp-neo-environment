<!-- loio962ccbbd5f634f918bbea9c1bf4273c3 -->

# list-vms

Lists all virtual machines in the specified subaccount. You can get information for a concrete virtual machine by name. The command output lists information about the virtual machine, such as size; status; SSH key; floating IP \(if assigned\); volume IDs.



> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of the following technology portfolios: application development; process automation; integration; data, analytics, and enterprise planning; artificial intelligence. The platform offers users the ability to turn data into business value, compose end-to-end business processes, connect entire IT landscapes, and personalize, build and extend SAP applications. This reduces the overall total cost of ownership maintaining SAP landscapes and third-party software across end-to-end business processes.") :arrow_upper_right:.**



```
neo list-vms --account <subaccount_technical_name> --user <e-mail_or_user> --host <host> --name <vm_name>
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
</table>


<table>
<tr>
<th valign="top" colspan="2">

Optional

</th>
</tr>
<tr>
<td valign="top">

`-n`, `--name` 

</td>
<td valign="top">

Name of the virtual machine

`Type`: string

</td>
</tr>
</table>



## Example

```
neo list-vms --account mysubaccount --user mymail@example.com --host hana.ondemand.com --name myvm
```

**Related Information**  


[Manage Virtual Machines](https://help.sap.com/viewer/c746ff81651e4b8fb6efc11146091016/Cloud/en-US/c0d2dd37428944d3b673ffdd74f3a975.html "You can create and start a virtual machine using either the SAP BTP cockpit or the console client. Then, you establish a secure communication channel to it over Secure Shell (SSH) protocol. You open an SSH tunnel and get all the communication details needed for you to log in to the virtual machine and install and maintain your software.") :arrow_upper_right:

