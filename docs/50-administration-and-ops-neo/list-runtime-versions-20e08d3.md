<!-- loio20e08d390fcf4d4a97e847c7343ea679 -->

# list-runtime-versions

The command displays the supported application runtime container versions for your SAP BTP SDK for Neo environment. Only recommended versions are shown by default. You can also list supported version for a particular runtime container.



> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**



```
neo list-runtime-versions --user <e-mail_or_user> --host <host>
```



## Parameters

To list all parameters available for this command, execute `neo help list-runtime-versions` in the command line.


<table>
<tr>
<th valign="top" colspan="2">

Required



</th>
</tr>
<tr>
<td valign="top">

`-u`, `--user`



</td>
<td valign="top">

Use your email, SAP ID, or user name.

`Type`: string



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

`-h`, `--host`



</td>
<td valign="top">

Enter a region host.

`Type`: URL. For acceptable values, see [Regions](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/350356d1dc314d3199dca15bd2ab9b0e.html "You can deploy applications in different regions. Each region represents a geographical location (for example, Europe, US East) where applications, data, or services are hosted.") :arrow_upper_right:.



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

`--all`



</td>
<td valign="top">

Lists all supported application runtime container versions. Using a previously released runtime version is not recommended.



</td>
</tr>
<tr>
<td valign="top">

`--runtime`



</td>
<td valign="top">

Lists supported version only for the specified runtime container.

For more information, see [Application Runtime Container](../30-development-neo/application-runtime-container-7613bd2.md).



</td>
</tr>
</table>



## Example

```
neo list-runtime-versions --user myuser --host hana.ondemand.com --runtime neo-java-web
```

**Related Information**  


[Choose Application Runtime Version](choose-application-runtime-version-13afe5c.md "Applications deployed on SAP BTP are always started on the latest version of the application runtime container. This version contains all released fixes, critical patches and enhancements and is respectively the recommended option for applications. In some special cases, you can choose the version of the runtime container your application uses by specifying it with the parameter --runtime-version when deploying your application. To change this version, you need to redeploy the application without specifying this parameter.")

[View Runtime Information](view-runtime-information-343663e.md "View information about the application runtime. SAP BTP provides a set of runtimes. You can choose the application runtime during application deployment.")

[list-runtimes](list-runtimes-49bb201.md "The command displays all available application runtime containers.")

