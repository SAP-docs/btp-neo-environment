<!-- loio13a70e053b984202982161d2a551bb0e -->

# enable

This command enables new connection requests to a disabled application or application process. The enable command cannot be used for an application that is in maintenance mode.



> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**



```
neo enable --host <host> --account <subaccount_technical_name> --application <application_name> --user <e-mail_or_user>
```



## Parameters



To list all parameters available for this command, execute `neo help enable` in the command line.


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

`Type`: URL. For acceptable values, see [Regions](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/350356d1dc314d3199dca15bd2ab9b0e.html "You can deploy applications in different regions. Each region represents a geographical location (for example, Europe, US East) where applications, data, or services are hosted.") :arrow_upper_right:



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

`-i`, `--application-process-id`



</td>
<td valign="top">

Unique ID of a single application process. Use it to enable a particular application process instead of the whole application. As the process ID is unique, you do not need to specify subaccount and application parameters. You can list the application process ID by using the *<status\>* command.

`Default`: none

`Type`: string \(hexadecimal sequence of 2 to 40 characters\)



</td>
</tr>
</table>



## Example

To enable the whole application, execute:

```
neo enable --host hana.ondemand.com --account mysubaccount --application myapp --user mymail@example.com
```

To enable a single applcation process, first identify the application process you want to enable by executing `neo status`:

```
neo status --host hana.ondemand.com --account mysubaccount --application myapp --user mymail@example.com
```

From the generated list of application process IDs, copy the ID you need and execute `neo enable` for it:

```
neo enable --application-process-id e8df21d  --host hana.ondemand.com --user mymail@example.com 
```

**Related Information**  


[status](status-d4f6592.md "You can check the current status of an application or application process. The command lists all application processes with their IDs, state, last change date sorted chronologically, and runtime information.")

[disable](disable-59fedc1.md "This command stops the creation of new connections to an application or application process, but keeps the already running sessions alive. You can check if an application or application process has been disabled by executing the status command.")

[start-maintenance](start-maintenance-f42be92.md "This command starts the planned downtime of an application, during which it no longer receives requests and a custom maintenance page for that application is shown to the user. All active connections will still be handled until the application is stopped.")

