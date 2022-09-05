<!-- loio75a0058e5c304243be91e4d2b7b04611 -->

# delete-jmx-check

Deletes the specified JMX check or all JMX checks.



> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**



```
neo delete-jmx-check -a <subaccount_technical_name> -u <e-mail_or_user> -n <JMX_check_name> -h <host>
```

or

```
neo delete-jmx-check -a <subaccount_technical_name> -u <e-mail_or_user> -A -h <host>
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

`-n`, `--name` or `-A`, all



</td>
<td valign="top">

Name of the JMX check to be deleted or all JMX checks configured for the given subaccount and application are deleted.

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

Application name

 `Type`: string \(up to 30 characters; lowercase letters and numbers, starting with a letter\)



</td>
</tr>
</table>



```
neo delete-jmx-check -a mysubaccount -b demo -u p1234567 -n "JVM Heap Memory Used" -h hana.ondemand.com
```

**Related Information**  


[JMX Checks](https://help.sap.com/viewer/64f7d2b06c6b40a9b3097860c5930641/Cloud/en-US/ef5c05a713154945b347f87b54446c2b.html "Registering JMX checks allows alerting on any metric that is based on JMX MBean attribute.") :arrow_upper_right:

[Monitoring Java Applications](https://help.sap.com/viewer/64f7d2b06c6b40a9b3097860c5930641/Cloud/en-US/cf4b2953c2534c0a9b491abf5a4847d7.html "") :arrow_upper_right:

