<!-- loio49bb2011da2b439d87a382ed923f5d8c -->

# list-runtimes

The command displays all available application runtime containers.



> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/docs/btp/sap-business-technology-platform/sap-business-technology-platform?version=Cloud) .**



```
neo list-runtimes --user <e-mail_or_user> --host <host>
```



## Parameters

To list all parameters available for this command, execute `neo help list-runtimes` in the command line.


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

Use your email, SAP ID, or username.

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



## Example

```
neo list-runtimes --user myuser --host hana.ondemand.com
```

**Related Information**  


[list-runtime-versions](list-runtime-versions-20e08d3.md "The command displays the supported application runtime container versions for your SAP BTP SDK for Neo environment. Only recommended versions are shown by default. You can also list supported version for a particular runtime container.")

[Choose Application Runtime Version](choose-application-runtime-version-13afe5c.md "Applications deployed on SAP BTP are always started on the latest version of the application runtime container. This version contains all released fixes, critical patches and enhancements and is respectively the recommended option for applications. In some special cases, you can choose the version of the runtime container your application uses by specifying it with the parameter --runtime-version when deploying your application. To change this version, you need to redeploy the application without specifying this parameter.")

[View Runtime Information](view-runtime-information-343663e.md "View information about the application runtime. SAP BTP provides a set of runtimes. You can choose the application runtime during application deployment.")

