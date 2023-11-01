<!-- loiob35e1e92ceb647daac49098b828dac92 -->

# Machine-Readable Command Output

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**



## Context

The console commands can return structured, machine-readable output. When you use the optional `--output` parameter in a command, the command returns values and objects in a format that a machine can easily parse. The currently supported output format is JSON.

Syntax: `--output <format>` 

Accepted format value: `json`



## Cases

-   If a command supports structured output, it returns machine-readable result values.
-   If a command does not \(yet\) support structured output,it returns basic information including the standard OUT/ERR output.
-   If the command is invoked without the `--output` parameter, it works as before.



## JSON Output Format

When `--output json` is specified, the console client prints out a single JSON object containing information about the command execution and the result, if available.

The JSON object contains the following properties:


<table>
<tr>
<th valign="top">

Property Name

</th>
<th valign="top">

Type

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

`command`

</td>
<td valign="top">

String

</td>
<td valign="top">

The name of the invoked `neo` command

</td>
</tr>
<tr>
<td valign="top">

`argLine`

</td>
<td valign="top">

String

</td>
<td valign="top">

The exact arguments line as specified by the calling script

</td>
</tr>
<tr>
<td valign="top">

`pid`

</td>
<td valign="top">

Name

</td>
<td valign="top">

The process ID of the invoked command

</td>
</tr>
<tr>
<td valign="top">

`exitCode`

</td>
<td valign="top">

Name

</td>
<td valign="top">

The process exit code of the invoked command \( `0` = successful, everything else = failure\)

</td>
</tr>
<tr>
<td valign="top">

`errorMsg`

</td>
<td valign="top">

String

</td>
<td valign="top">

The message provided when the command implementation throws instance of `com.sap.jpaas.infrastructure.console.exception.CommandException`

</td>
</tr>
<tr>
<td valign="top">

`commandOutput`

</td>
<td valign="top">

String

</td>
<td valign="top">

The command output written to`system.out` and captured by the console client framework

</td>
</tr>
<tr>
<td valign="top">

`commandErrorOutput`

</td>
<td valign="top">

String

</td>
<td valign="top">

The command output written to `system.err` and captured by the console client framework

</td>
</tr>
<tr>
<td valign="top">

`result`

</td>
<td valign="top">

Object

</td>
<td valign="top">

The result object returned by the command following the new contract for structured, machine-readable output

</td>
</tr>
</table>



## Example

Here is a full example of a command \( `neo start` \) that supports structured output and displays result values:

```
{
    "command": "start",
    "argLine": "-a myaccount -b myapplication -h hana.ondemand.com -u myuser -p ******* -y",
    "pid": 6523,
    "exitCode": 0,
    "errorMsg": null,
    "commandOutput": "Requesting start for:
   application           : myapplication
   account               : myaccount
   host                  : https://hana.ondemand.com
   synchronous           : true
   SDK version           : 1.48.99
   user                  : myuser
 
 
[Tue Feb 25 18:07:19 CET 2014] Start request performed successfully.
 
Triggered start of application process.
Status: STARTING
 
[Tue Feb 25 18:07:19 CET 2014] Waiting for STARTED status..............
[Tue Feb 25 18:07:25 CET 2014] Status STARTING reached for 6161 ms
[Tue Feb 25 18:07:19 CET 2014] Waiting for STARTED status..................................
[Tue Feb 25 18:08:47 CET 2014] Status STARTED reached for 87838 ms
 
web: STARTED
 
URL: https://myapplicationmyaccount.hana.ondemand.com
 
Access points:
  https://myapplicationmyaccount.hana.ondemand.com
 
Runtime: 1.47 (valid until 20-May-2015)
 
Application processes
ID          State       Last Change              Runtime
  fc735dc     STARTED     25-Feb-2014 18:07:48     1.47.10.2
",
    "commandErrorOutput": "",
    "result": {
        "status": "STARTED",
        "url": "https://myapplicationmyaccount.hana.ondemand.com",
        "accessPoints": [
            "https://myapplicationmyaccount.hana.ondemand.com",
            "https://myapplicationmyaccount.hana.ondemand.com/app2"
        ],
        "applicationProcesses": [
            {
                "id": "fc735dc",
                "state": "STARTED",
                "lastChange": "2014-02-25T18:07:48Z",
                "runtime": "1.47.10.2"
            }
        ]
    }
}
```

> ### Note:  
> The shown command result is only an example and may look different in the real or future implementation. The output is similar for commands that do not support structured result values but the result property is then null.

**Related Information**  


[Exit Codes](https://help.sap.com/viewer/ea72206b834e4ace9cd834feed6c0e09/Cloud/en-US/7886796eb9b9419fa6cecf1d215c38d8.html)

[Default Trace File](https://help.sap.com/viewer/ea72206b834e4ace9cd834feed6c0e09/Cloud/en-US/1b651b3aa5f54538a8f452f6fda0f5c3.html)

