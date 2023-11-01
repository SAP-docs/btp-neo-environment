<!-- loiocc417d7ac1284f9e903fd89613b08b27 -->

# start

Starts a deployed application in order to make it available for customers. In case the application is already started, the command starts an additional application process if the quota for maximum allowed number of application processes is not exceeded.



> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**



```
neo start --account <subaccount_technical_name> --application <application_name> --user <e-mail_or_user> 
--host <host>
```



<a name="loiocc417d7ac1284f9e903fd89613b08b27__section_N1001F_N10012_N10001"/>

## Parameters

To list all parameters available for this command, execute `neo help start` in the command line.


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

`-b`, `--application` 

</td>
<td valign="top">

Application name

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

`--disabled` 

</td>
<td valign="top">

Starts an application process in disabled state, so that it is not available for new connections.

`Default`: off

`Type`: switch, takes no value

</td>
</tr>
<tr>
<td valign="top">

`-y`, `--synchronous` 

</td>
<td valign="top">

Triggers the starting process and waits until the application is started. The command without the `--synchronous` parameter triggers the starting process and exits immediately without waiting for the application to start.

`Default`: off

`Type`: switch, takes no value

</td>
</tr>
</table>



## Example

To start the application and wait for the operation to finish, execute:

```
neo start --host hana.ondemand.com --account mysubaccount --application myapp --user mymail@example.com --synchronous 
```

**Related Information**  


[Console Client for the Neo Environment](console-client-for-the-neo-environment-7613230.md)

[status](status-d4f6592.md "You can check the current status of an application or application process. The command lists all application processes with their IDs, state, last change date sorted chronologically, and runtime information.")

[Scale Applications](scale-applications-745781b.md "Each application is started on a dedicated SAP BTP Runtime. One application can be started on one or many application processes, according to the compute unit quota that you have.")

