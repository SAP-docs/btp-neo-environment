<!-- loio83d45827519b413bb98c4e2aaf9b3752 -->

# create-availability-check

Creates an availability check.



> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://launchpad.support.sap.com/#/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**



```
neo create-availability-check -a <subaccount_technical_name> -u <e-mail_or_user> -U <relative_URL> -h <host>
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

`-a`, `--account`



</td>
<td valign="top">

Subaccount technical name

`Type`: string \(up to 30 characters; lowercase letters and numbers, starting with a letter\)



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

`-U`, `--url`



</td>
<td valign="top">

Relative application URL

`Type`: string



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
</table>


<table>
<tr>
<th valign="top" colspan="2">

Optional



</th>
</tr>
<tr>
<td valign="top">

`-b`, `--application` 



</td>
<td valign="top">

Application name for Java or HTML5 applications, or productive SAP HANA instance database name and application name in the format *<instance name\>*:*<application name\>* for SAP HANA XS applications

`Type`: string \(up to 30 characters; lowercase letters and numbers, starting with a letter\)



</td>
</tr>
<tr>
<td valign="top">

`-W`, `--warning`



</td>
<td valign="top">

Threshold value or range of the response time in seconds.

`Default`: 50

`Type`: string



</td>
</tr>
<tr>
<td valign="top">

`-C`, `--critical`



</td>
<td valign="top">

Threshold value or range of the response time in seconds.

`Default`: 60

`Type`: string



</td>
</tr>
<tr>
<td valign="top">

`-w`, `--overwrite`



</td>
<td valign="top">

Should be used only if there is an existing availability check that needs to be updated.

`Default`: false

`Type`: boolean



</td>
</tr>
</table>



<a name="loio83d45827519b413bb98c4e2aaf9b3752__section_jqc_fzt_5fb"/>

## Example

Example for creating an availability check for application *demo*:

```
neo create-availability-check -a mysubaccount -b demo -u p1234567 -U /heartbeat -C 4 -W 6 --host hana.ondemand.com
```

Example for creating an availability check for *myhana* application:

```
neo create-availability-check -a mysubaccount -b myhanainstance:myhana -u p1234567 -U /heartbeat.xsjs -C 4 -W 6 --host hana.ondemand.com
```

**Related Information**  


[Monitoring Java Applications](https://help.sap.com/viewer/64f7d2b06c6b40a9b3097860c5930641/Cloud/en-US/cf4b2953c2534c0a9b491abf5a4847d7.html "") :arrow_upper_right:

[Monitoring Database Systems](https://help.sap.com/viewer/64f7d2b06c6b40a9b3097860c5930641/Cloud/en-US/d5c5c6a37c944ce78fcccf2b84243d8a.html "") :arrow_upper_right:

