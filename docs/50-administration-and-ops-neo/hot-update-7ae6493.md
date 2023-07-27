<!-- loio7ae6493455844b4ab993c1a1b69595fa -->

# hot-update

The hot-update command enables a developer to redeploy and update the binaries of an application started on one process faster than the normal deploy and restart. Use it to apply and activate your changes during development and not for updating productive applications.



> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://launchpad.support.sap.com/#/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**



There are three options for hot-update specified with the *\--strategy* parameter:

-   replace-binaries - redeploys and updates the application binaries

-   restart-runtime - redeploys and updates the application binaries and restarts the application process

-   reprovision-runtime - cleans up the file system, reprovisions the runtime and redeploys and updates the application binaries


```
neo hot-update --host <host> --account <subaccount_technical_name> --application <application_name> --source <file_location> --user <e-mail_or_user> --strategy <update_strategy>
  
```

**Limitations:**

-   It works only if there's a single running process of the application.

-   It doesn’t work if the previous operation was deploy or any other changing the deploy parameters.

-   You can't change deploy parameters and context path of the application.




## Parameters

To list all parameters available for this command, execute `neo help hot-update` in the command line.


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

`Type`: URL. For acceptable values, see [Regions](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/350356d1dc314d3199dca15bd2ab9b0e.html "You can deploy applications in different regions. Each region represents a geographical location (for example, Europe, US East) where applications, data, or services are hosted.") :arrow_upper_right:.



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

Your email, SAP ID or user name.

`Type`: string



</td>
</tr>
<tr>
<td valign="top">

`-s`, `--source`



</td>
<td valign="top">

A comma-separated list of file locations, pointing to WAR files, or folders containing them.

`Type`: file location



</td>
</tr>
<tr>
<td valign="top">

`--strategy`



</td>
<td valign="top">

Defines how the update is performed.

`Acceptable values:`

-   `replace-binaries`
-   `restart-runtime`
-   `reprovision-runtime`



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

`--connections`



</td>
<td valign="top">

Number of connections used to deploy the content.

`Default`: *1*

`Acceptable values`: `1-6`

`Type`: integer



</td>
</tr>
<tr>
<td valign="top">

`--delta` 



</td>
<td valign="top">

Uploads only the changes between the provided source and the deployed content. New content is added; missing content is deleted. Recommended for development use to speed up the deployment.

`Acceptable values`: None



</td>
</tr>
<tr>
<td valign="top">

`-y`, `--synchronous`



</td>
<td valign="top">

Waits for the operation to complete.

`Acceptable values`: None



</td>
</tr>
</table>



## Example

```
neo hot-update --host us1.hana.ondemand.com --account mysubaccount --application myapp --source samples/deploy_war/example.war --user mymail@example.com --strategy replace-binaries
```

