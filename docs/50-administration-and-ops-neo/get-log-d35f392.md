<!-- loiod35f392ff9504c8793df5feee18054ca -->

# get-log

This command downloads a particular log file.



> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://launchpad.support.sap.com/#/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**



```
neo get-log --account <subaccount_technical_name> --application <application_name> --user <e-mail_or_user>  --host <host> --directory <local_folder_location_of_the_file> --file <file_name>
```



## Parameters



To list all parameters available for this command, execute `neo help get-log` in the command line.


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

`-d`, `--directory` 



</td>
<td valign="top">

Local folder location under which the file will be downloaded. If the directory you have specified does not exist, it will be created.

`Type`: string



</td>
</tr>
<tr>
<td valign="top">

`-f`, `--file` 



</td>
<td valign="top">

The log file name including its extension.

`Type`: string

> ### Note:  
> To find out the name of the log file to download, use the `list-logs` command to see the available log files of your application. For more information, see [list-logs](list-logs-1f6a77c.md).



</td>
</tr>
<tr>
<td valign="top">

`-h`, `--host` 



</td>
<td valign="top">

Enter a region host.

`Type`: URL, for acceptable values see [Regions](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/350356d1dc314d3199dca15bd2ab9b0e.html "You can deploy applications in different regions. Each region represents a geographical location (for example, Europe, US East) where applications, data, or services are hosted.") :arrow_upper_right:



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


<table>
<tr>
<th valign="top" colspan="2">

Optional



</th>
</tr>
<tr>
<td valign="top">

`-w`, `--overwrite` 



</td>
<td valign="top">

Overwrites a file with the same name if such already exists. If you do not explicitly include the `--overwrite` argument, you will be notified and asked if you want to overwrite the file.

`Default`: true

`Type`: boolean



</td>
</tr>
<tr>
<td valign="top">

`-t`, `--apptype` 



</td>
<td valign="top">

Application type. Use this parameter to differentiate applications with the same name from different technologies \(Java and HTML5\).

The following values are allowed for the application type:

-   `java` - for Java applications

-   `html5` - for HTML5 applications


`Default`: `java`

`Type`: string



</td>
</tr>
</table>



## Example

```
neo get-log --account mysubaccount --application demo --apptype html5 --user p1234567890 --host hana.ondemand.com --directory C:\MyDemoApps\log --file ljs_trace_2016-08-25.log
```

**Related Information**  


[Using Logs in the Console Client](https://help.sap.com/viewer/ee8e8a203e024bbb8c8c2d03fce527dc/Cloud/en-US/e4fd83c5bb5710149b1e94f127f108e4.html)

[Exit Codes](exit-codes-7886796.md "")

