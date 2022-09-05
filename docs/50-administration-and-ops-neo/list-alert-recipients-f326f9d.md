<!-- loiof326f9df2f5246bbb1878b01cfdbc0ba -->

# list-alert-recipients

Lists alert recipients.



> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**



<a name="loiof326f9df2f5246bbb1878b01cfdbc0ba__section_an3_mgj_flb"/>

## Prerequisites

-   You've set up the console client.

    For more information, see [Set Up the Console Client](../30-development-neo/set-up-the-console-client-7613dee.md).

-   The *readMonitoringConfiguration* scope is assigned to the used platform role for the subaccount. For more information, see [Platform Scopes](platform-scopes-f226074.md).




```
neo list-alert-recipients -a <subaccount_technical_name> -u <e-mail_or_user> -h <host>
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

Use your email, SAP ID, or user name

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

`-b`, `--application` 



</td>
<td valign="top">

Application name for Java or HTML5 applications, or productive SAP HANA instance database name and application name in the format *<instance name\>*:*<application name\>* for SAP HANA XS applications

 `Type`: string \(up to 30 characters; lowercase letters and numbers, starting with a letter\)



</td>
</tr>
<tr>
<td valign="top">

`-R`, `--recursively`



</td>
<td valign="top">

Lists alerts recipients recursively starting from the specified level. For example, if only 'subaccount' is passed as an argument, it starts from the subaccount level and then lists all recipients configured on application level.

`Default`: false

`Type`: boolean



</td>
</tr>
</table>



```
neo list-alert-recipients -a mysubaccount -b demo -u p1234567 -R --host hana.ondemand.com
```

Sample output:

```

Neo Console Client


Password for your user:


Running list-alert-recipients with the following parameters:

    account     : mysubaccount
    host        : https://hana.ondemand.com
    recursively : true
    user        : p1234567


Subaccount-level alert recipients
Recipients not set on subaccount level for subaccount mysubaccount
	

       application : demo1
       alert_recipients@example.com
       application : demo2
       alert_recipients@example.org, alert_recipients@example.net
		 
  
```

**Related Information**  


[Monitoring Java Applications](https://help.sap.com/viewer/64f7d2b06c6b40a9b3097860c5930641/Cloud/en-US/cf4b2953c2534c0a9b491abf5a4847d7.html "") :arrow_upper_right:

[Monitoring Database Systems](https://help.sap.com/viewer/64f7d2b06c6b40a9b3097860c5930641/Cloud/en-US/d5c5c6a37c944ce78fcccf2b84243d8a.html "") :arrow_upper_right:

[set-alert-recipients](set-alert-recipients-6dae74f.md "Sets alert recipients.")

[clear-alert-recipients](clear-alert-recipients-0f2b2cd.md "Clears alert recipients.")

