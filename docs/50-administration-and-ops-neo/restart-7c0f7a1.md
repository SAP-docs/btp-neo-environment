<!-- loio7c0f7a18a4564e0e8b6f997d230285ff -->

# restart

Use this command to restart your application or a single application process. The effect of the restart command is the same as executing the stop command first and when the application is stopped, starting it with the start command.



> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of the following technology portfolios: application development; process automation; integration; data, analytics, and enterprise planning; artificial intelligence. The platform offers users the ability to turn data into business value, compose end-to-end business processes, connect entire IT landscapes, and personalize, build and extend SAP applications. This reduces the overall total cost of ownership maintaining SAP landscapes and third-party software across end-to-end business processes.") :arrow_upper_right:.**



```
neo restart --account <subaccount_technical_name> --application <application_name> --host <host> --user <e-mail_or_user>
```

```
neo restart --application-process-id <ID> --user <e-mail_or_user> --host <host>
```

> ### Recommendation:  
> We recommend that you restart your Java applications by following the steps in [Restart Applications with Zero Downtime](restart-applications-with-zero-downtime-deadcc4.md).
> 
> If you are not able to start an application process, please do not try to stop any of the currently running processes. First, please make sure that you can start a new application process before stopping any of the running processes.
> 
> Here are the benefits of restarting a Java application this way:
> 
> -   It allows your application to remain operable all the time.
> 
> -   It protects you against unexpected issues with the application or the platform.



<a name="loio7c0f7a18a4564e0e8b6f997d230285ff__section_N10019_N10012_N10001"/>

## Parameters

To list all parameters available for this command, execute the `neo help restart` command.


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

`Type`: URL. For acceptable values see [Regions](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/350356d1dc314d3199dca15bd2ab9b0e.html "You can deploy applications in different regions. Each region represents a geographical location (for example, Europe, US East) where applications, data, or services are hosted.") :arrow_upper_right:.

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

Triggers the process and waits until the application is restarted. The command without the `--synchronous` parameter triggers the restarting process and exits immediately without waiting for the application to start.

`Default`: off

`Type`: switch, takes no value

</td>
</tr>
<tr>
<td valign="top">

`-i`, `--application-process-id`

</td>
<td valign="top">

Unique ID of a single application process. Use it to restart a particular application process instead of the whole application. As the process ID is unique, you do not need to specify subaccount and application parameters. You can list the application process ID by using the *<status\>* command.

`Default`: none

`Type`: string \(hexadecimal sequence of 2 to 40 characters\)

</td>
</tr>
</table>



## Example

To restart the whole application and wait for the operation to finish, execute:

```
 neo restart --account mysubaccount --application myapp --user mymail@example.com --host hana.ondemand.com --synchronous
```

**Related Information**  


[stop](stop-b5bfcbf.md "Use this command to stop your deployed and started application or application process.")

[status](status-d4f6592.md "You can check the current status of an application or application process. The command lists all application processes with their IDs, state, last change date sorted chronologically, and runtime information.")

[Exit Codes](exit-codes-7886796.md "")

