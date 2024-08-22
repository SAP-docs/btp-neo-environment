<!-- loiod4f6592584464cc6a5c3c0b6fc88abf9 -->

# status

You can check the current status of an application or application process. The command lists all application processes with their IDs, state, last change date sorted chronologically, and runtime information.



> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of the following technology portfolios: application development; process automation; integration; data, analytics, and enterprise planning; artificial intelligence. The platform offers users the ability to turn data into business value, compose end-to-end business processes, connect entire IT landscapes, and personalize, build and extend SAP applications. This reduces the overall total cost of ownership maintaining SAP landscapes and third-party software across end-to-end business processes.") :arrow_upper_right:.**



The command also lists the availability zones where these application processes are running. However, this is only valid for recently started applications and if you have the latest SAP BTP SDK for Neo environment version installed.

If two or more processes of an application are running in the same availability zone, they're on separate hardware entities. Therefore, if one of these processes is affected by an infrastructure issue, the others continue to run normally ensuring that your application is working as expected.

When an application process is running but can't receive new connection requests, it's marked as disabled in its status description. Additionally, if an application is in planned downtime and a maintenance page has been configured for it, the corresponding application is listed in the command output.

```
neo status --account <subaccount_technical_name> --application <application_name> --host <host> --user <e-mail_or_user>
```

```
neo status --application-process-id <ID> --host <host> --user <e-mail_or_user>
```



<a name="loiod4f6592584464cc6a5c3c0b6fc88abf9__section_N10019_N10016_N10001"/>

## Parameters

To list all parameters available for this command, execute `neo help status` in the command line.


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

Use your email, SAP ID, or user name

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

Unique ID of a single application process. Use it to show the status of a particular application process instead of the whole application. As the process ID is unique, you don't need to specify subaccount and application parameters.

`Default`: none

`Type`: string \(hexadecimal sequence of 2 to 40 characters\)

</td>
</tr>
<tr>
<td valign="top">

`--show-full-process-id`

</td>
<td valign="top">

Shows the full length \(40 characters\) of the unique application process ID. You may need to get the full ID when you try to execute a certain operation on the application process and the process can't be identified uniquely with the short version of the ID. In particular, usage of the full length is recommended for tools and batch processing. If this parameter isn't used, the status command lists only the first 7 characters by default.

`Default`: off

`Type`: switch, takes no value

</td>
</tr>
</table>



<a name="loiod4f6592584464cc6a5c3c0b6fc88abf9__section_N10026_N10016_N10001"/>

## Example

You can list all application processes in your application with their IDs:

```
neo status --host hana.ondemand.com --account mysubaccount --application myapp --user mymail@example.com
```

Then, you can request the status of a particular application process from the list using its ID:

```
neo status --host hana.ondemand.com --application-process-id e8df21d --user mymail@example.com
```

**Related Information**  


[Console Client for the Neo Environment](console-client-for-the-neo-environment-7613230.md)

[start](start-cc417d7.md "Starts a deployed application in order to make it available for customers. In case the application is already started, the command starts an additional application process if the quota for maximum allowed number of application processes is not exceeded.")

[disable](disable-59fedc1.md "This command stops the creation of new connections to an application or application process, but keeps the already running sessions alive. You can check if an application or application process has been disabled by executing the status command.")

[start-maintenance](start-maintenance-f42be92.md "This command starts the planned downtime of an application, during which it no longer receives requests and a custom maintenance page for that application is shown to the user. All active connections will still be handled until the application is stopped.")

