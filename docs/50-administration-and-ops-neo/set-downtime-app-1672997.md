<!-- loio1672997f41f74cd79761291ff7ece0b5 -->

# set-downtime-app

This command configures a custom downtime page \(downtime application\) for an application. The downtime page is shown to the user in the event of unplanned downtime of the original application.



> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**



```
neo set-downtime-app --account <subaccount_technical_name> --application <application_name> --host <host> 
--user <e-mail_or_user> --downtime-application <downtime_application_name> 
```



<a name="loio1672997f41f74cd79761291ff7ece0b5__section_N1001E_N10012_N10001"/>

## Parameters

To list all parameters available for this command, execute `neo help set-downtime-app` in the command line.


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
<tr>
<td valign="top">

`--downtime-application`



</td>
<td valign="top">

Downtime application name

The downtime page application is provided by the customer and hosted in the same subaccount as the application itself.

`Type`: string \(up to 30 characters; lowercase letters and numbers, starting with a letter\)



</td>
</tr>
</table>



## Example

```
neo set-downtime-app --account mysubaccount --application myapp --user mymail@example.com --downtime-application downtimeapp
```

**Related Information**  


[clear-downtime-app](clear-downtime-app-c9ae25a.md "The command deregisters a previously configured downtime page for an application. After you execute the command, the default HTTP error will be shown to the user in the event of unplanned downtime.")

[Handle Unplanned Downtime](handle-unplanned-downtime-dbd314a.md "In the event of unplanned downtime when there is no application process able to serve HTTP requests, a default error is shown to users. To prevent this, an operator can configure a custom downtime page using a downtime application, which takes over the HTTP traffic if an unplanned downtime occurs.")

