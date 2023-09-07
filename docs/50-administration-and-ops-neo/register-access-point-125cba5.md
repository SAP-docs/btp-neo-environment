<!-- loio125cba59e7c14ecbac3d43c118cf570e -->

# register-access-point

Registers an access point URL for a virtual machine specified by name or ID.



> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**



```
neo register-access-point --account <subaccount_technical_name> --user <e-mail_or_user> --host <host> --name <vm_name>
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



## Example

```
neo register-access-point --account mysubaccount --user mymail@example.com --host hana.ondemand.com --name myvm
```

The `register-access-point` command creates an internally managed security rule of type CIDR, which allows communication between the load balancer of the platform and the virtual machine.

**Related Information**  


[Enable Internet Access](https://help.sap.com/viewer/c746ff81651e4b8fb6efc11146091016/Cloud/en-US/acf74847c5f846d0b4512cba64c18353.html "You can make your software running on a virtual machine accessible from the Internet if your scenario requires it.") :arrow_upper_right:

[unregister-access-point](unregister-access-point-462a3d2.md "Unregisters the access point URL registered for a virtual machine specified by name or ID.")

