<!-- loioc6fedee0a1394991a913ec94fb654826 -->

# list-jmx-checks

Lists JMX checks.



> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**



```
neo list-jmx-checks -a <subaccount_technical_name> -u <e-mail_or_user> -h <host>
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

`-h`, `--host`

</td>
<td valign="top">

Enter a region host.

`Type`: URL. For acceptable values see [Regions](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/350356d1dc314d3199dca15bd2ab9b0e.html "You can deploy applications in different regions. Each region represents a geographical location (for example, Europe, US East) where applications, data, or services are hosted.") :arrow_upper_right:.

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

Application name

`Type`: string \(up to 30 characters; lowercase letters and numbers, starting with a letter\)

> ### Note:  
> If this parameter is used, only the application level checks are listed \(the subaccount level checks are not listed\).



</td>
</tr>
<tr>
<td valign="top">

`-R`, `--recursively`

</td>
<td valign="top">

Lists JMX checks recursively, starting from the specified level. For example, if only 'subaccount' is passed as an argument, it starts from the subaccount level and then lists all checks configured on application level.

`Default`: false

`Type`: boolean

</td>
</tr>
</table>

> ### Note:  
> If the optional parameters are not used, only the JMX checks on subaccount level are listed.



<a name="loioc6fedee0a1394991a913ec94fb654826__section_rvn_ndz_5fb"/>

## Example

Listing all the JMX checks on subaccount and application levels:

```
neo list-jmx-checks -a mysubaccount -u p1234567 -R -h hana.ondemand.com
```

Sample output:

```
 
Neo Console Client


Password for your user:


Running list-jmx-check with the following parameters:

	account    : mysubaccount
	host       : https://hana.ondemand.com
	recursively: true
	user       : p1234567


Subaccount-level JMX checks

    account         : mysubaccount
    check-name      : JVM Heap Memory Used
    object-name     : java.lang:type=Memory
    critical        : 60
    attribute       : HeapMemoryUsage
    attribute key   : used
    warning         : 700000000
    critical        : 900000000 
    unit            : B


Application JMX checks
			
      application       : demo
      check-name        : JVM Heap Memory Used
      object-name       : java.lang:type=Memory
      attribute         : HeapMemoryUsage
      attribute key     : used
      warning           : 600000000
      critical          : 850000000
      unit              : B


```

**Related Information**  


[JMX Checks](https://help.sap.com/viewer/64f7d2b06c6b40a9b3097860c5930641/Cloud/en-US/ef5c05a713154945b347f87b54446c2b.html "Registering JMX checks for SAP Monitoring service allows alerting on any metric that is based on JMX MBean attribute.") :arrow_upper_right:

[Monitoring Java Applications](https://help.sap.com/viewer/64f7d2b06c6b40a9b3097860c5930641/Cloud/en-US/cf4b2953c2534c0a9b491abf5a4847d7.html "") :arrow_upper_right:

