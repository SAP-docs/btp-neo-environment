<!-- loio64ecd69a56e2429b86286bc0e96fb9f2 -->

# list-security-rules

This console client command lists the security group rules configured for a virtual machine.



> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of the following technology portfolios: application development; process automation; integration; data, analytics, and enterprise planning; artificial intelligence. The platform offers users the ability to turn data into business value, compose end-to-end business processes, connect entire IT landscapes, and personalize, build and extend SAP applications. This reduces the overall total cost of ownership maintaining SAP landscapes and third-party software across end-to-end business processes.") :arrow_upper_right:.**



```
neo list-security-rules --account <subaccount_technical_name> --user <e-mail_or_user> --host <host> --name <vm_name>
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

Your subaccount technical name.

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

Type the name of the virtual machine.

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



## Example

```
neo list-security-rules --account mysubaccount --user mymail@example.com --host hana.ondemand.com --name myvm
```

As an output of the `list-security-rules` command, you may receive the HANA or JAVA source types previously created with the `create-security-rule` command, or an internally managed security group rule of type CIDR for a registered access point. The security group rule of type CIDR allows communication between the load balancer of the platform and the virtual machine.

**Related Information**  


[Manage Network Communication for SAP Virtual Machine Service](https://help.sap.com/viewer/c746ff81651e4b8fb6efc11146091016/Cloud/en-US/41c987c040f04c7cb6157dcc824a7762.html "You can allow communication with a virtual machine from other systems by managing security group rules in the cockpit or using console client commands. Communication between virtual machines within the same subaccount is available by default.") :arrow_upper_right:

[create-security-rule](create-security-rule-b140be7.md "This console client command creates a security group rule for a virtual machine.")

