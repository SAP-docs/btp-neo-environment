<!-- loiof42be92739bf483fa930a9caa7efaf13 -->

# start-maintenance

This command starts the planned downtime of an application, during which it no longer receives requests and a custom maintenance page for that application is shown to the user. All active connections will still be handled until the application is stopped.



> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://launchpad.support.sap.com/#/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**



```
neo start-maintenance --account <subaccount_technical_name> --application <application_name> --host <host> 
--user <e-mail_or_user> --maintenance-application <maintenance_application_name> 
```



<a name="loiof42be92739bf483fa930a9caa7efaf13__section_N1001E_N10012_N10001"/>

## Parameters

To list all parameters available for this command, execute `neo help start-maintenance` in the command line.


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

Use your email, SAP ID, or user name.

`Type`: string



</td>
</tr>
<tr>
<td valign="top">

`--maintenance-application`



</td>
<td valign="top">

Maintenance page application name

The maintenance page application is provided by the customer and hosted in the same subaccount as the application itself.

`Type`: string \(up to 30 characters; lowercase letters and numbers, starting with a letter\)



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

`--direct-access-code`



</td>
<td valign="top">

While setting your application in maintenance mode, you can generate an access code, which you can use later during the maintenance period. While your application is in maintenance mode, you can use this access code in the *Direct-Access-Code* HTTP header so that you can have access to your application for testing and administration purposes. In the meantime, users will continue to have access to the maintenance application.

`Type`: string \(alphanumeric; up to 100 characters\)



</td>
</tr>
</table>

If an application is already in planed downtime, executing the status command for it will show the maintenance application, to which the traffic is being redirected.



## Example

```
neo start-maintenance --account mysubaccount --application myapp --user <mymail@example.com --host hana.ondemand.com --maintenance-application maintapp
```

**Related Information**  


[Enable Maintenance Mode for Planned Downtimes](enable-maintenance-mode-for-planned-downtimes-aa04f29.md "An operator can start and stop planned application downtime, during which a customized maintenance page for that application is shown to end users.")

[stop-maintenance](stop-maintenance-3fbd6fe.md "This command stops the planned downtime of an application, starts traffic to it and deregisters the maintenance application page.")

[status](status-d4f6592.md "You can check the current status of an application or application process. The command lists all application processes with their IDs, state, last change date sorted chronologically, and runtime information.")

