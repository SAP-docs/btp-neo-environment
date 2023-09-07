<!-- loio4108f0f0680446a39db27f624c0e8b6a -->

# set-quota

Sets compute unit quotas for a given subaccount.



> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**



> ### Note:  
> The amount you want to set cannot exceed the amount of quota you have purchased. In case you try to set bigger amount of quota, you will receive an error message.



```
neo set-quota --account <subaccount_technical_name> --host <host> --user <e-mail_or_user> --amount <quota_type>:<integer_amount_of_quota>
```



## Parameters

To list all parameters available for this command, execute `neo help set-quota` in the command line.


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

`Type`: URL, for acceptable values see [Regions](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/350356d1dc314d3199dca15bd2ab9b0e.html "You can deploy applications in different regions. Each region represents a geographical location (for example, Europe, US East) where applications, data, or services are hosted.") :arrow_upper_right:.



</td>
</tr>
<tr>
<td valign="top">

`-m`, `--amount`



</td>
<td valign="top">

Compute unit quota type and amount of the quota to be set in the format <type\>:\[amount\].

In this composite parameter, the <type\> part is mandatory and must have one of the following values: lite, pro, prem, prem-plus. The amount part is optional and must be an integer value. If omitted, a default value 1 is assigned. Do not insert spaces between the two parts and their delimiter ":", and use lower case for the <type\> part.

`Type`: string



</td>
</tr>
</table>



## Example

```
neo set-quota --account mysubaccount --user myuser --host hana.ondemand.com --amount lite:2
```

