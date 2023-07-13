<!-- loio96c6d247f64c4fbb849bb80640a146d9 -->

# remove-platform-domain

Removes a platform domain \(under hana.ondemand.com\) as an access point for an application.



> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**



```
neo remove-platform-domain --account <subaccount_technical_name> --application <application_name> --user <e-mail_or_user> --host <host> --platform-domain <platform_domain> 
```



## Parameters



To list all parameters available for this command, execute `neo help remove-platform-domain` in the command line.


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
<tr>
<td valign="top">

`-m`, `platform-domain`



</td>
<td valign="top">

Platform domain under hana.ondemand.com

`Type`: URL



</td>
</tr>
</table>



## Example

```
neo remove-platform-domain --account mysubaccount --application myapp --user myuser --host hana.ondemand.com --platform-domain svc.hana.ondemand.com
```

**Related Information**  


[add-platform-domain](add-platform-domain-7afd450.md "Adds a platform domain (under hana.ondemand.com) on which the application will be accessed.")

[Using Platform Domains](using-platform-domains-a32d4cd.md#loioa32d4cd65be344439d9ed752f182e609 "Using platform domains, you can configure the application network availability or authentication policy. You can achieve that by configuring the appropriate platform domain which will change the URL on which your application will be accessible.")

