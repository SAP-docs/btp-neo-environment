<!-- loiof8d24b6a1c4e4cec841b3ee1118189bb -->

# unbind-domain-certificate

Unbinds a certificate from an SSL host. The certificate will not be deleted from SAP BTP storage.



> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/docs/btp/sap-business-technology-platform/sap-business-technology-platform?version=Cloud) .**



```
neo unbind-domain-certificate --account <subaccount_technical_name> --user <e-mail_or_user> --host <host> --ssl-host <ssl_hostname>
```



## Parameters



To list all parameters available for this command, execute `neo help unbind-domain-certificate` in the command line.


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

`Type`: URL, for acceptable values see [Regions](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/350356d1dc314d3199dca15bd2ab9b0e.html "You can deploy applications in different regions. Each region represents a geographical location (for example, Europe, US East) where applications, data, or services are hosted.") :arrow_upper_right:.

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

`-l`, `--ssl-host`

</td>
<td valign="top">

SSL host as defined with the`--name` parameter when created, or 'default' if not specified.

</td>
</tr>
</table>



## Example

```
neo unbind-domain-certificate --account mysubaccount --user mymail@example.com --host hana.ondemand.com --ssl-host mysslhostname 

```

**Related Information**  


[Bind the Certificate to the SSL Host](configuring-custom-domains-77cf0e6.md#loio1d4248f3582a40cdb6f4a2439a55fb65 "You need to bind the uploaded certificate to the created SSL host so that it can be used as SSL certificate for requests to this SSL host.")

[Update an Expired Certificate](update-an-expired-certificate-11da7c3.md#loio11da7c3a91f24206a68f70b5d6cb3d88 "When the certificate for the custom domain expires or it's about to expire, you can either upload and bind a new certificate based on a new CSR, or upload and bind a new certificate based on an already existing CSR.")

