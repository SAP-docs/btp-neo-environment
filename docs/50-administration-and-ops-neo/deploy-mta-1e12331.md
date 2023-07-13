<!-- loio1e12331df5e144c7b2cfa9f5db85d065 -->

# deploy-mta

This command deploys Multitarget Application \(MTA\) archives. One or more than one MTA archives can be deployed to your subaccount in one go.



> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**



```
neo deploy-mta --host <host> --account <subaccount_technical_name>  --source <file(1)_location>,<file(2)_location>,...,<file(n)_location> --user <e-mail_or_user>			
```



<a name="loio1e12331df5e144c7b2cfa9f5db85d065__section_N10015_N10012_N10001"/>

## Parameters



To list all parameters available for this command, execute `neo help deploy-mta` in the command line.


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

The name of the subaccount for which you provide a user and a password.



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

Your user password. We recommend that you enter it only when prompted, and not explicitly as a parameter in a properties file or the command line.



</td>
</tr>
<tr>
<td valign="top">

 `-u`, `--user` 



</td>
<td valign="top">

Your user e-mail or SAP ID \(SCN\) user name.



</td>
</tr>
<tr>
<td valign="top">

 `-s`, `--source` 



</td>
<td valign="top">

A comma-separated list of file locations, pointing to the MTA archive files, or the folders containing them.



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
<td valign="top" colspan="2">

**Command-specific parameters**



</td>
</tr>
<tr>
<td valign="top">

 `-y`, `--synchronous` 



</td>
<td valign="top">

Triggers the deployment and waits until the deployment operation finishes. The command without the `--synchronous` parameter triggers deployment and exits immediately without waiting for the operation to finish. Takes no value.



</td>
</tr>
<tr>
<td valign="top">

 `-e`, `--extensions` 



</td>
<td valign="top">

Defines one or more extensions to the deployment descriptor. A comma-separated list of file locations, pointing to the extension descriptor files, or the folders containing them. For more information, see [Defining MTA Extension Descriptors](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/50df803465324d36851c79fd07e8972c.html "") :arrow_upper_right:.



</td>
</tr>
<tr>
<td valign="top">

 `--mode` 



</td>
<td valign="top">

Defines whether the deployment method is a standard deployment, or provider deployment. The available values are `import` \(default value\), or `providerImport`.



</td>
</tr>
</table>



<a name="loio1e12331df5e144c7b2cfa9f5db85d065__section_N1014A_N10012_N10001"/>

## Example

You can deploy an MTA archive on a host different from the default one by specifying the host parameter. For example, to use the region \(host\) located in the United States, execute:

```
neo deploy-mta --host us1.hana.ondemand.com --account mysubaccount --source /usr/test/deploy_mta/example.mtar --user mymail@example.com
```

**Related Information**  


[list-mta-operations](list-mta-operations-8029e1a.md "This command shows the MTA operation status with a given ID.")



