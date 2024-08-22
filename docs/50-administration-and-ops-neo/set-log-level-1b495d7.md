<!-- loio1b495d7580c7404db42c9da996b50a93 -->

# set-log-level

This command sets a log level for one or multiple loggers.



> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of the following technology portfolios: application development; process automation; integration; data, analytics, and enterprise planning; artificial intelligence. The platform offers users the ability to turn data into business value, compose end-to-end business processes, connect entire IT landscapes, and personalize, build and extend SAP applications. This reduces the overall total cost of ownership maintaining SAP landscapes and third-party software across end-to-end business processes.") :arrow_upper_right:.**



```
neo set-log-level  --account <subaccount_technical_name> --application <application_name> --user <e-mail_or_user> --host <host> --loggers <logger_name1>,<logger_name2>,... --level <log_level>
```



<a name="loio1b495d7580c7404db42c9da996b50a93__section_N100AF_N10013_N10001"/>

## Log Level Mapping

Simple Logging Facade for Java \(SLF4J\) uses the following log levels:


<table>
<tr>
<th valign="top">

Level

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

ALL

</td>
<td valign="top">

This level has the lowest possible rank and is intended to turn on all logging.

</td>
</tr>
<tr>
<td valign="top">

TRACE

</td>
<td valign="top">

This level designates finer-grained informational events than DEBUG.

</td>
</tr>
<tr>
<td valign="top">

DEBUG

</td>
<td valign="top">

This level designates fine-grained informational events that are most useful to debug an application.

</td>
</tr>
<tr>
<td valign="top">

INFO

</td>
<td valign="top">

This level designates informational messages that highlight the progress of the application at coarse-grained level.

</td>
</tr>
<tr>
<td valign="top">

WARN

</td>
<td valign="top">

This level designates potentially harmful situations.

</td>
</tr>
<tr>
<td valign="top">

ERROR

</td>
<td valign="top">

This level designates error events that might still allow the application to continue running.

</td>
</tr>
<tr>
<td valign="top">

OFF

</td>
<td valign="top">

This level has the highest possible rank and is intended to turn off logging.

</td>
</tr>
</table>

> ### Caution:  
> HTTP headers are logged in plain text once the log level is set to `DEBUG` or `ALL`. Thus, in case they contain any sensitive information, such as passwords kept in an HTTP **Authorization** header, it’s disclosed in the logs.



## Parameters



To list all parameters available for this command, execute `neo help set-log-level` in the command line.


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

`-g`, `--loggers` 

</td>
<td valign="top">

Single or multiple comma-separated logger names

`Type`: string

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

`-l`, `--level` 

</td>
<td valign="top">

The log level you want to set for the logger\(s\)

`Type`: string

</td>
</tr>
<tr>
<td valign="top">

`-p`, `--password` 

</td>
<td valign="top">

Password for the specified user. To protect your password, enter it only when prompted by the console client and not explicitly as a parameter in the properties file or the command line.

`Type`: string

</td>
</tr>
<tr>
<td valign="top">

`-u`, `--user` 

</td>
<td valign="top">

Your email, SAP ID or user name

`Type`: string

</td>
</tr>
</table>



## Example

```
neo set-log-level --account mysubaccount --application demo --user p1234567890 --host hana.ondemand.com --loggers com.acme.foo,com.acme.bar --level ERROR
```

**Related Information**  


[Using Logs in the Console Client](https://help.sap.com/viewer/f88a032109f0429caea276fc6e3a95f9/Cloud/en-US/e4fd83c5bb5710149b1e94f127f108e4.html "") :arrow_upper_right:

[Exit Codes](exit-codes-7886796.md "")

