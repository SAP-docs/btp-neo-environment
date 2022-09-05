<!-- loiob5bfcbf682684129b142606e1d4ca5cb -->

# stop

Use this command to stop your deployed and started application or application process.



> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**



```
neo stop --account <subaccount_technical_name> --application <application_name> --user <e-mail_or_user> --host <host>
```

```
neo stop --application-process-id <ID> --user <e-mail_or_user> --host <host>
```



<a name="loiob5bfcbf682684129b142606e1d4ca5cb__section_N1001E_N10012_N10001"/>

## Parameters

To list all parameters available for this command, execute ***neo help stop*** in the command line.


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

`Condition`: Not required if using `--application-process-id`



</td>
</tr>
<tr>
<td valign="top">

`-b`, `--application` 



</td>
<td valign="top">

Application name

 `Type`: string \(up to 30 characters; lowercase letters and numbers, starting with a letter\)

`Condition`: Not required if using `--application-process-id`



</td>
</tr>
<tr>
<td valign="top">

`-h`, `--host`



</td>
<td valign="top">

Enter a region host.

`Type`: URL, for acceptable values see [Regions](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/350356d1dc314d3199dca15bd2ab9b0e.html "You can deploy applications in different regions. Each region represents a geographical location (for example, Europe, US East) where applications, data, or services are hosted.") :arrow_upper_right:.



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

Use your email, SAP ID or user name

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

 `-y`, `--synchronous`



</td>
<td valign="top">

Triggers the stopping process and waits until the application is stopped. The command without the `--synchronous` parameter triggers the stopping process and exits immediately without waiting for the application to stop.

`Default`: off

`Type`: switch, takes no value



</td>
</tr>
<tr>
<td valign="top">

`-i`, `--application-process-id`



</td>
<td valign="top">

Unique ID of a single application process. Use it to stop a particular application process instead of the whole application. As the process ID is unique, you do not need to specify subaccount and application parameters. You can list the application process ID by using the *<status\>* command.

`Default`: none

`Type`: string \(hexadecimal sequence of 2 to 40 characters\)



</td>
</tr>
</table>



## Example

To stop the whole application and wait for the operation to finish, execute:

```
neo stop --host hana.ondemand.com --account mysubaccount --application myapp --user mymail@example.com --synchronous 
```

**Related Information**  


[Console Client for the Neo Environment](console-client-for-the-neo-environment-7613230.md)

[status](status-d4f6592.md "You can check the current status of an application or application process. The command lists all application processes with their IDs, state, last change date sorted chronologically, and runtime information.")

[Exit Codes](exit-codes-7886796.md "")

