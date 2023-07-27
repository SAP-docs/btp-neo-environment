<!-- loio29569757974e4ebd9806eaf099d517a0 -->

# set-ssl-host

Configures and updates an SSL host. Allows you to replace an SSL certificate with a different one, manage TLS protocol versions, and configure a bundle of trusted CAs.



> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://launchpad.support.sap.com/#/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**



```
neo set-ssl-host --account <subaccount_technical_name> --user <e-mail_or_user> --host <host> --name <ssl_hostname>
```



<a name="loio29569757974e4ebd9806eaf099d517a0__section_dth_dtx_rcb"/>

## Parameters



To list all parameters available for this command, execute `neo help set-ssl-host` in the command line.


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

`Type`: URL. For acceptable values, see [Regions](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/350356d1dc314d3199dca15bd2ab9b0e.html "You can deploy applications in different regions. Each region represents a geographical location (for example, Europe, US East) where applications, data, or services are hosted.") :arrow_upper_right:.



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

`-n`, `--name`



</td>
<td valign="top">

Name of the SSL host that will be configured and updated.



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

`-c`, `--certificate`



</td>
<td valign="top">

Name of the certificate that you bind to the SSL host. The certificate must already be uploaded.

> ### Caution:  
> This will replace the previously bound certificate, if there is already one.

`Type`: string \(It can contain alphanumerics, '.', '-', and '\_'\)



</td>
</tr>
<tr>
<td valign="top">

`--ca-bundle` 



</td>
<td valign="top">

Use a switch to specify if client certificate authentication is mandatory for the respective CA bundle. For more information, see [Managing Client Certificate Authentication for Custom Domains](managing-client-certificate-authentication-for-custom-domains-286aa51.md).

`Type`: string

`Format`: <bundle\_name\>:<switch\>

`Acceptable switch values`:

-   `request` - client certificate authentication is not mandatory

-   `require` - client certificate authentication is mandatory

-   `none` - removes the client certificate configuration for the specified bundle and unassigns that bundle from the SSL host


`Default switch value`: request



</td>
</tr>
<tr>
<td valign="top">

`-t`, `--supported-protocols`



</td>
<td valign="top">

Specify the TLS protocols that you want to enable for the SSL host. The remaining TLS protocols are disabled. This parameter requires a certificate to be bound to the SSL host.

`Type`: string

`Supported TLS protocols`: TLSV1\_2

Newer TLS versions will be added to the list of supported TLS protocols, if necessary.

`Delimiter`: comma \(,\)

> ### Note:  
> Enabling TLS 1.2 with `--supported-protocols TLSV1_2` disables all ciphers considered weak by the platform and listed in the --supported-ciphers section. You can enable these ciphers again using the`--supported-ciphers` parameter.

To check the currently enabled TLS version, run the `set-ssl-host` command without using any optional parameters.



</td>
</tr>
<tr>
<td valign="top">

`-s`, `--supported-ciphers`



</td>
<td valign="top">

It allows you to enable additional ciphers for the SSL host.

> ### Note:  
> This parameter does not work on its own. It is always accompanied by the `--supported-protocols` parameter with value `TLSV1_2`.

`Type`: string

`Acceptable values`:

-   AES128\_SHA256

-   AES256\_SHA256

-   AES128\_SHA

-   AES256\_SHA

-   ECDHE\_RSA\_AES128\_CBC\_SHA

-   ECDHE\_RSA\_AES128\_SHA256

-   ECDHE\_RSA\_AES256\_CBC\_SHA

-   ECDHE\_RSA\_AES256\_SHA384


`Delimiter`: comma \(,\)

> ### Caution:  
> For security reasons, it is recommended to use the default TLS 1.2 ciphers without using the `--supported-ciphers` parameter.



</td>
</tr>
</table>

> ### Note:  
> If you change either the supported protocols, ciphers, or both, you will set a custom SSL profile for which any further TLS versions will not be updated automatically.
> 
> If you want to learn which TLS version and cipher your application is using to communicate with the Neo environment, see [Transport Layer Security \(TLS\) Connectivity Support](https://help.sap.com/viewer/ea72206b834e4ace9cd834feed6c0e09/Cloud/en-US/3438252775d84bdfa211e79147561c99.html).



<a name="loio29569757974e4ebd9806eaf099d517a0__section_clt_xtx_rcb"/>

## Examples

-   ```
neo set-ssl-host -a mysubaccount -u mymail@example.com -h hana.ondemand.com -n mysslhostname
```

    If the optional parameters are not used, the `set-ssl-host` command returns the current properties of the SSL host.

-   ```
neo set-ssl-host -a mysubaccount -u mymail@example.com -h hana.ondemand.com -n mysslhostname -c mycert --supported-protocols "TLSV1_2"
```

    Here, TLS 1.2 is enabled and all ciphers considered weak by the platform are disabled.

    > ### Note:  
    > Enabling TLS 1.2 this way will disable the following ciphers: \[ECDHE-RSA-AES128-CBC-SHA, ECDHE-RSA-AES128-SHA256, ECDHE-RSA-AES256-CBC-SHA, ECDHE-RSA-AES256-SHA384, AES128-SHA256, AES256-SHA256, AES128-SHA, AES256-SHA\]. You can enable these ciphers again using the`--supported-ciphers` parameter.

-   ```
neo set-ssl-host -a mysubaccount -u mymail@example.com -h hana.ondemand.com -n mysslhostname -c mycert --supported-protocols "TLSV1_2" --supported-ciphers "AES128-SHA,AES256-SHA"
```

    In this example, AES128-SHA and AES256-SHA are the only ciphers enabled for TLS 1.2.


**Related Information**  


[create-ssl-host](create-ssl-host-3c890d5.md "Creates an SSL host for configuration of custom domains. This SSL host will be serving your custom domain.")

[upload-domain-certificate](upload-domain-certificate-bb54abf.md "Uploads a signed custom domain certificate to SAP BTP. You can upload either a certificate based on a previously generated CSR via the generate-csr command, or another valid certificate with its corresponding private key.")

[bind-domain-certificate](bind-domain-certificate-8722bcb.md "Binds a certificate to an SSL host. The certificate must already be uploaded.")

[change-domain-certificate](change-domain-certificate-53aa1f3.md "Changes a certificate of an SSL host. The certificate must already be uploaded.")

[Bind the Certificate to the SSL Host](configuring-custom-domains-77cf0e6.md#loio1d4248f3582a40cdb6f4a2439a55fb65 "You need to bind the uploaded certificate to the created SSL host so that it can be used as SSL certificate for requests to this SSL host.")

[add-ca](add-ca-c102abb.md "Uploads a trusted CA certificate and adds it to a certificate authority (CA) bundle. If you don't have a CA bundle yet, it will be created automatically.")

[list-cas](list-cas-99d2659.md "Lists trusted CA certificates in a bundle or bundles that are assigned to an SSL host or hosts.")

[remove-ca](remove-ca-55b61e4.md "Removes trusted CAs from a bundle or deletes a whole bundle and all certificates in it.")

