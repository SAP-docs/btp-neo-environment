<!-- loio53aa1f37750a4b5ab5b6728b8e5c05af -->

# change-domain-certificate

Changes a certificate of an SSL host. The certificate must already be uploaded.



> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**



```
neo change-domain-certificate --account <subaccount_technical_name> --user <e-mail_or_user> --host <host> --ssl-host <ssl_hostname> --certificate <certificate_name>
```



<a name="loio53aa1f37750a4b5ab5b6728b8e5c05af__section_qtv_lnp_mz"/>

## Parameters



To list all parameters available for this command, execute `neo help change-domain-certificate` in the command line.


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

Use your email, SAP ID, or user name.

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

SSL host as defined with the `--name` parameter when created, or 'default' if not specified.



</td>
</tr>
</table>



<a name="loio53aa1f37750a4b5ab5b6728b8e5c05af__section_f5v_lnp_mz"/>

## Example

```
neo change-domain-certificate --account mysubaccount --user mymail@example.com --host hana.ondemand.com --ssl-host mysslhostname --certificate myfirstcert

```

The `change-domain-certificate` command lets you change the domain certificate of a custom domain in one step instead of executing both the `unbind-domain-certificate` and `bind-domain-certificate` commands.

If your current version of the SDK for SAP BTP, Neo environment does not support this command, update your SDK or use the `unbind-domain-certificate` and `bind-domain-certificate` commands instead.

> ### Note:  
> The first version of the SDK for SAP BTP, Neo environment to support the `change-domain-certificate` command are:
> 
> -   Java Web SDK \(version 1.126.11\)
> 
> -   Java EE 6 Web Profile SDK \(version 2.108.10\)
> 
> -   Java Web Tomcat 7 SDK \(version 2.73.15\)
> 
> -   Java Web Tomcat 8 SDK \(version 3.27.14\)
> 
> 
> For more information, see [Update the SAP BTP SDK for Neo Environment](../30-development-neo/update-the-sap-btp-sdk-for-neo-environment-7614378.md).

**Related Information**  


[Update an Expired Certificate](update-an-expired-certificate-11da7c3.md#loio11da7c3a91f24206a68f70b5d6cb3d88 "When the certificate for the custom domain expires or it's about to expire, you can either upload and bind a new certificate based on a new CSR, or upload and bind a new certificate based on an already existing CSR.")

[unbind-domain-certificate](unbind-domain-certificate-f8d24b6.md "Unbinds a certificate from an SSL host. The certificate will not be deleted from SAP BTP storage.")

[bind-domain-certificate](bind-domain-certificate-8722bcb.md "Binds a certificate to an SSL host. The certificate must already be uploaded.")

[set-ssl-host](set-ssl-host-2956975.md "Configures and updates an SSL host. Allows you to replace an SSL certificate with a different one, manage TLS protocol versions, and configure a bundle of trusted CAs.")

[Update the SAP BTP SDK for Neo Environment](../30-development-neo/update-the-sap-btp-sdk-for-neo-environment-7614378.md)

