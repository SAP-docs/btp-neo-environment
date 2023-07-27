<!-- loio8722bcb71cda48498330957cc96e72de -->

# bind-domain-certificate

Binds a certificate to an SSL host. The certificate must already be uploaded.



> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://launchpad.support.sap.com/#/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**



```
neo bind-domain-certificate --account <subaccount_technical_name> --user <e-mail_or_user> --host <host> --ssl-host <ssl_hostname> --certificate <certificate_name>
```



## Parameters



To list all parameters available for this command, execute `neo help bind-domain-certificate` in the command line.


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

Enter a region host.

`Type`: URL. For acceptable values see [Regions and Hosts Available for the Neo Environment](../10-concepts-neo/regions-and-hosts-available-for-the-neo-environment-d722f7c.md)



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

Use your email, SAP ID, or username.

`Type`: string



</td>
</tr>
<tr>
<td valign="top">

`--certificate`



</td>
<td valign="top">

Name of the certificate that you set to the SSL host

The certificate must already be uploaded.



</td>
</tr>
<tr>
<td valign="top">

`-l`, `--ssl-host`



</td>
<td valign="top">

SSL host as defined with the`--name` parameter when created, or 'default' if not specified.



</td>
</tr>
</table>



## Example

```
neo bind-domain-certificate --account mysubaccount --user mymail@example.com --host hana.ondemand.com --ssl-host mysslhostname --certificate myfirstcert

```

**Related Information**  


[Bind the Certificate to the SSL Host](configuring-custom-domains-77cf0e6.md#loio1d4248f3582a40cdb6f4a2439a55fb65 "You need to bind the uploaded certificate to the created SSL host so that it can be used as SSL certificate for requests to this SSL host.")

[Configuring Custom Domains](configuring-custom-domains-77cf0e6.md#loio77cf0e6cd32e496c9cc8eeac4bedde94 "To make sure that your domain is trusted and all application data is protected, you need to first set up secure SSL communication. The next step will then be to make your application accessible via the custom domain and route traffic to it.")

[set-ssl-host](set-ssl-host-2956975.md "Configures and updates an SSL host. Allows you to replace an SSL certificate with a different one, manage TLS protocol versions, and configure a bundle of trusted CAs.")

