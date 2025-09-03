<!-- loio9fbd1393b9934c93984c893c5f39be3a -->

# list-proxy-host-mappings

Lists the proxy hosts mapped to an application hostname.



> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/docs/btp/sap-business-technology-platform/sap-business-technology-platform?version=Cloud) .**



```
neo list-proxy-host-mappings --account <subaccount_technical_name> --app-host <application_host> --proxy <proxy_host:port> -h <host> -u <e-mail_or_user> -p <password>
```



<a name="loio9fbd1393b9934c93984c893c5f39be3a__section_xqt_3ck_fz"/>

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

`-h`, `--host`

</td>
<td valign="top">

Region host on which you execute the command.

`Type`: URL. For acceptable values see [Regions](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/350356d1dc314d3199dca15bd2ab9b0e.html "You can deploy applications in different regions. Each region represents a geographical location (for example, Europe, US East) where applications, data, or services are hosted.") :arrow_upper_right:.

</td>
</tr>
<tr>
<td valign="top">

`-u`, `--user`

</td>
<td valign="top">

Your email, SAP ID, or username.

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
</table>


<table>
<tr>
<th valign="top" colspan="2">

Optional

</th>
</tr>
<tr>
<td valign="top">

`--app-host`

</td>
<td valign="top">

Your application hostname.

For example: `myapp.hana.ondemand.com`

</td>
</tr>
<tr>
<td valign="top">

`--proxy`

</td>
<td valign="top">

On-premise reverse proxy hostname and port.

Separate proxy hostname and port with a colon \(':'\). For example:`loc.corp:123`

</td>
</tr>
</table>



<a name="loio9fbd1393b9934c93984c893c5f39be3a__section_xdr_5ck_fz"/>

## Example

```
neo list-proxy-host-mappings --account mysubaccount --app-host app.hana.ondemand.com --proxy loc.corp:123 -h hana.ondemand.com -u username -p ******
```

An application with hostname `app.hana.ondemand.com` is mapped to proxy host `loc.corp:123`.

**Related Information**  


[Configuring Application Access via On-Premise Reverse Proxy](configuring-application-access-via-on-premise-reverse-proxy-79773d1.md "Using an on-premise reverse proxy allows you to combine on-premise and cloud-based web applications in the same browser window.")

[map-proxy-host](map-proxy-host-12b5cc4.md "Maps an application host to an on-premise reverse proxy host and port.")

[unmap-proxy-host](unmap-proxy-host-10ddad9.md "Deletes the mapping between an application host and an on-premise reverse proxy host and port.")

