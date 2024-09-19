<!-- loio4a44c350f9cd4e26ab21d25a32a8e5a5 -->

# add-domain-certificate

Adds a certificate to the SSL host. The certificate must already be uploaded.



> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of the following technology portfolios: application development; process automation; integration; data, analytics, and enterprise planning; artificial intelligence. The platform offers users the ability to turn data into business value, compose end-to-end business processes, connect entire IT landscapes, and personalize, build and extend SAP applications. This reduces the overall total cost of ownership maintaining SAP landscapes and third-party software across end-to-end business processes.") :arrow_upper_right:.**



```
neo add-domain-certificate --account <subaccount_technical_name> --user <e-mail_or_user> --host <host> --ssl-host <ssl_hostname> --certificate <certificate_name>
```

The `add-domain-certificate` command allows you to add an already uploaded certificate of another type to the SSL host. For example, if you already have an RSA certificate bound to the SSL host, you now also have the option to add an ECC certificate to that SSL host, and vice versa.



## Parameters



To list all parameters available for this command, execute `neo help add-domain-certificate` in the command line.


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

Name of the certificate that you add to the SSL host

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
neo add-domain-certificate --account mysubaccount --user mymail@example.com --host hana.ondemand.com --ssl-host mysslhostname --certificate myfirstcert

```

To check all currently added certificates, run the `set-ssl-host` command. The certificates appear in the command output as ***Certificate 1 : <value1\>\(<type1\>\)*** and ***Certificate 2 : <value2\>\(<type2\>\)***.



### Command output example:

***Certificate 1 : myfirstcert \(RSA\)***

***Certificate 2 : mynewcert \(ECC\)***

If you have two certificates in total, the most recently added certificate will be listed as ***Certificate 2 : <value2\>\(<type2\>\)***. In the provided output example, `mynewcert` is the certificate added with the `add-domain-certificate` command.

**Related Information**  


[Bind the Certificate to the SSL Host](configuring-custom-domains-77cf0e6.md#loio1d4248f3582a40cdb6f4a2439a55fb65 "You need to bind the uploaded certificate to the created SSL host so that it can be used as SSL certificate for requests to this SSL host.")

[Configuring Custom Domains](configuring-custom-domains-77cf0e6.md#loio77cf0e6cd32e496c9cc8eeac4bedde94 "To make sure that your domain is trusted and all application data is protected, you need to first set up secure SSL communication. The next step will then be to make your application accessible via the custom domain and route traffic to it.")

[set-ssl-host](set-ssl-host-2956975.md "Configures and updates an SSL host. Allows you to replace an SSL certificate with a different one, manage TLS protocol versions, and configure a bundle of trusted CAs.")

