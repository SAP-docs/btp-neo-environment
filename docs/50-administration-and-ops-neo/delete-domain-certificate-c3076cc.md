<!-- loioc3076ccbad214c129b056778c33bcd3e -->

# delete-domain-certificate

Deletes a certificate.



> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of the following technology portfolios: application development; process automation; integration; data, analytics, and enterprise planning; artificial intelligence. The platform offers users the ability to turn data into business value, compose end-to-end business processes, connect entire IT landscapes, and personalize, build and extend SAP applications. This reduces the overall total cost of ownership maintaining SAP landscapes and third-party software across end-to-end business processes.") :arrow_upper_right:.**



> ### Note:  
> Cannot be undone. If the certificate is mapped to an SSL host, the certificate will be removed from the SSL host too.

```
neo delete-domain-certificate --account <subaccount_technical_name> --user <e-mail_or_user> --host <host> --name <certificate_name>
```



## Parameters



To list all parameters available for this command, execute `neo help delete-domain-certificate` in the command line.


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

`Type`: URL. For acceptable values see [Regions](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/350356d1dc314d3199dca15bd2ab9b0e.html "You can deploy applications in different regions. Each region represents a geographical location (for example, Europe, US East) where applications, data, or services are hosted.") :arrow_upper_right:

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

`-n`, `--name`

</td>
<td valign="top">

Name of the certificate that you set to the SSL host

The certificate must already be uploaded.

</td>
</tr>
</table>



## Example

```
neo delete-domain-certificate --account mysubaccount --user mymail@example.com --host hana.ondemand.com --name myfirstcert

```

**Related Information**  


[Bind the Certificate to the SSL Host](configuring-custom-domains-77cf0e6.md#loio1d4248f3582a40cdb6f4a2439a55fb65 "You need to bind the uploaded certificate to the created SSL host so that it can be used as SSL certificate for requests to this SSL host.")

[bind-domain-certificate](bind-domain-certificate-8722bcb.md "Binds a certificate to an SSL host. The certificate must already be uploaded.")

