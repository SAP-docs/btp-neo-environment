<!-- loio7afd450f4dec43dd94542f196c32df37 -->

# add-platform-domain

Adds a platform domain \(under hana.ondemand.com\) on which the application will be accessed.



> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of the following technology portfolios: application development; process automation; integration; data, analytics, and enterprise planning; artificial intelligence. The platform offers users the ability to turn data into business value, compose end-to-end business processes, connect entire IT landscapes, and personalize, build and extend SAP applications. This reduces the overall total cost of ownership maintaining SAP landscapes and third-party software across end-to-end business processes.") :arrow_upper_right:.**



```
neo add-platform-domain --account <subaccount_technical_name> --application <application_name> --user <e-mail_or_user> --host <host> --platform-domain <platform_domain> 
```



## Parameters



To list all parameters available for this command, execute `neo help add-platform-domain` in the command line.


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

`Type`: URL. For acceptable values, see [Regions and Hosts Available for the Neo Environment](../10-concepts-neo/regions-and-hosts-available-for-the-neo-environment-d722f7c.md).

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

Use your email, SAP ID or user name

`Type`: string

</td>
</tr>
<tr>
<td valign="top">

`-m`, `--platform-domain`

</td>
<td valign="top">

Platform domain under hana.ondemand.com

The chosen platform domain will be parent domain in the absolute application domain.

`Acceptable values`:

-   svc.\{region host\}
-   cert.\{region host\}

For more information about the available region hosts, see [Regions and Hosts Available for the Neo Environment](../10-concepts-neo/regions-and-hosts-available-for-the-neo-environment-d722f7c.md).

</td>
</tr>
</table>



## Example

```
neo add-platform-domain --account mysubaccount --application myapp --user myuser --host us1.hana.ondemand.com --platform-domain svc.us1.hana.ondemand.com
```

**Related Information**  


[Using Platform Domains](using-platform-domains-a32d4cd.md#loioa32d4cd65be344439d9ed752f182e609 "Using platform domains, you can configure the application network availability or authentication policy. You can achieve that by configuring the appropriate platform domain which will change the URL on which your application will be accessible.")

[remove-platform-domain](remove-platform-domain-96c6d24.md "Removes a platform domain (under hana.ondemand.com) as an access point for an application.")

