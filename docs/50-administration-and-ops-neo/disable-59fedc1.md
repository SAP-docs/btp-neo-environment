<!-- loio59fedc12d81b4801aa24c3b12414e382 -->

# disable

This command stops the creation of new connections to an application or application process, but keeps the already running sessions alive. You can check if an application or application process has been disabled by executing the status command.



> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of the following technology portfolios: application development; process automation; integration; data, analytics, and enterprise planning; artificial intelligence. The platform offers users the ability to turn data into business value, compose end-to-end business processes, connect entire IT landscapes, and personalize, build and extend SAP applications. This reduces the overall total cost of ownership maintaining SAP landscapes and third-party software across end-to-end business processes.") :arrow_upper_right:.**



```
neo disable --host <host> --account <subaccount_technical_name> --application <application_name> --user <e-mail_or_user>
```



## Parameters



To list all parameters available for this command, execute `neo help disable` in the command line.


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

`Type`: URL. For acceptable values see [Regions](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/350356d1dc314d3199dca15bd2ab9b0e.html "You can deploy applications in different regions. Each region represents a geographical location (for example, Europe, US East) where applications, data, or services are hosted.") :arrow_upper_right:

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

Unique ID of a single application process. Use it to disable a particular application process instead of the whole application. As the process ID is unique, you do not need to specify subaccount and application parameters. You can list the application process ID by using the *<status\>* command.

`Default`: none

`Type`: string \(hexadecimal sequence of 2 to 40 characters\)

</td>
</tr>
</table>



## Example

To disable the whole application, execute:

```
neo disable --host hana.ondemand.com --account mysubaccount --application myapp --user mymail@example.com
```

To disable a single applcation process, first identify the application process you want to disable by executing `neo status`:

```
neo status --host hana.ondemand.com --account mysubaccount --application myapp --user mymail@example.com
```

From the generated list of application process IDs, copy the ID you need and execute `neo disable` for it:

```
neo disable --application-process-id e8df21d  --host hana.ondemand.com --user mymail@example.com 
```

**Related Information**  


[Perform Soft Shutdown](perform-soft-shutdown-17e8e96.md "Soft shutdown enables an operator to stop an application or application process in a way that no data is lost. Using soft shutdown gives sufficient time to finish serving end user requests or background jobs.")

[start](start-cc417d7.md "Starts a deployed application in order to make it available for customers. In case the application is already started, the command starts an additional application process if the quota for maximum allowed number of application processes is not exceeded.")

[status](status-d4f6592.md "You can check the current status of an application or application process. The command lists all application processes with their IDs, state, last change date sorted chronologically, and runtime information.")

[Exit Codes](exit-codes-7886796.md "")

