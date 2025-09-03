<!-- loio8fdc143303d2456a84cd660eb7277a6a -->

# deploy-local

This command deploys WAR files on a local server instance.



> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/docs/btp/sap-business-technology-platform/sap-business-technology-platform?version=Cloud) .**



```
neo deploy-local --source <file_location>
```



## Parameters


<table>
<tr>
<th valign="top" colspan="2">

Required

</th>
</tr>
<tr>
<td valign="top">

`-s`, `--source`

</td>
<td valign="top">

Source for deployment \(comma separated list of WAR files or folders containing one or more WAR files\)

`Type`: file location

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

`-l`, `--location`

</td>
<td valign="top">

Local server installation directory

</td>
</tr>
</table>



## Example

```
neo deploy-local --source samples/deploy_war/example.war
```

**Related Information**  


[Deploy Locally with the Console Client](../30-development-neo/deploy-locally-with-the-console-client-937c833.md "The console client allows you to install a server runtime in a local folder and use it to deploy your application.")

