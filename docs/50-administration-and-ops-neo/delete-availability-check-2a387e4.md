<!-- loio2a387e4e5faa4e35939ba472b33cb74a -->

# delete-availability-check

Deletes an availability check.



> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of the following technology portfolios: application development; process automation; integration; data, analytics, and enterprise planning; artificial intelligence. The platform offers users the ability to turn data into business value, compose end-to-end business processes, connect entire IT landscapes, and personalize, build and extend SAP applications. This reduces the overall total cost of ownership maintaining SAP landscapes and third-party software across end-to-end business processes.") :arrow_upper_right:.**



```
neo delete-availability-check -a <subaccount_technical_name> -u <e-mail_or_user> -h <host>
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
</table>



<a name="loio2a387e4e5faa4e35939ba472b33cb74a__section_ulr_m15_5fb"/>

## Example

```
neo delete-availability-check -a mysubaccount -b demo -u p1234567 --host hana.ondemand.com
```

**Related Information**  


[Monitoring Java Applications](https://help.sap.com/viewer/64f7d2b06c6b40a9b3097860c5930641/Cloud/en-US/cf4b2953c2534c0a9b491abf5a4847d7.html "") :arrow_upper_right:

[Monitoring Database Systems](https://help.sap.com/viewer/64f7d2b06c6b40a9b3097860c5930641/Cloud/en-US/d5c5c6a37c944ce78fcccf2b84243d8a.html "You can monitor your database system by viewing its metrics in the SAP BTP cockpit, by retrieving them with the Metrics REST API, or by receiving alerts for them. Furthermore, when you use an SAP HANA database system, you can also configure monitoring for its SAP HANA XS applications.") :arrow_upper_right:

