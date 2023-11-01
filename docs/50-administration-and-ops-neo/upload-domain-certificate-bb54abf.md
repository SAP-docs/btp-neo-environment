<!-- loiobb54abf8453b437c848ece7269cbe28f -->

# upload-domain-certificate

Uploads a signed custom domain certificate to SAP BTP. You can upload either a certificate based on a previously generated CSR via the `generate-csr` command, or another valid certificate with its corresponding private key.



> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**



```
neo upload-domain-certificate --account <subaccount_technical_name> --user <e-mail_or_user> --host <host> --name <certificate_name> --location <file_location>
```



## Parameters



To list all parameters available for this command, execute `neo help upload-domain-certificate` in the command line.


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

Name of the certificate previously used in the CSR generation via the `generate-csr` command.

If you upload a certificate not based on a CSR generated via `generate-csr`, you use this parameter to name the certificate.

`Type`: string

The certificate name must start with a letter and can only contain lowercase letters \(a-z\), uppercase letters \(A-Z\), numbers \(0-9\), underscores \( \_ \), and hyphens \(-\).

</td>
</tr>
<tr>
<td valign="top">

`-l`, `--location`

</td>
<td valign="top">

Location of a file containing certificate data

> ### Note:  
> Some CAs issue chained root certificates that contain one or more intermediate certificates. In such cases, put all certificates in the file for upload starting with the signed SSL certificate.

> ### Caution:  
> Once uploaded, the certificate cannot be downloaded for security reasons. This also includes intermediate certificates.

`Type`: file location

`Maximum file size`: 20 KB

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

`-f`, `--force`

</td>
<td valign="top">

Overwrites an existing SSL certificate. For example, this parameter lets you update an expired certificate based on an already existing CSR. For more information, see [Using the CSR of the Bound Certificate](update-an-expired-certificate-11da7c3.md#loiof16731619a134670ac99915b2049d8d5).

The `--force` option is also useful if you had to and you did not upload an intermediate certificate for some reason. Note that the intermediate certificate must be added to the file that contains the SSL certificate.

</td>
</tr>
<tr>
<td valign="top">

`-k`, `--key-location`

</td>
<td valign="top">

Location of the file containing the private key of the certificate specified in `--name`

If you want to upload a signed certificate that is not based on a CSR generated via the `generate-csr` command, you must use this parameter to remotely upload this certificate to SAP BTP along with its private key.

> ### Caution:  
> Uploading a private key from a remote location poses a security risk. Also, there is no way to download the uploaded private key. SAP recommends that you use only certificates that are based on CSRs previously generated via the `generate-csr` command.

`Type`: file location

`Maximum file size`: 4 KB

</td>
</tr>
</table>



## Examples

```
neo upload-domain-certificate --account mysubaccount --user mymail@example.com --host hana.ondemand.com --name myfirstcert --location ./certificate.pub
```

The `.pub` file \(for example, certificate.pub\) should contain either:

-   An SSL certificate.

    > ### Example:  
    > ```
    > -----BEGIN CERTIFICATE-----
    > Enter your SSL certificate.
    > The certificate must be in Privacy-enhanced Electronic Mail (PEM) format (128 or 256 bits).
    > -----END CERTIFICATE----- 
    > 
    > ```

-   An SSL certificate followed by an intermediate certificate.

    > ### Example:  
    > ```
    > -----BEGIN CERTIFICATE-----
    > Enter your SSL certificate. 
    > The certificate must be in Privacy-enhanced Electronic Mail (PEM) format (128 or 256 bits).
    > -----END CERTIFICATE----- 
    > -----BEGIN CERTIFICATE-----
    > Enter your intermediate certificate.
    > The certificate must be in Privacy-enhanced Electronic Mail (PEM) format (128 or 256 bits).
    > -----END CERTIFICATE----- 
    > ```


```
neo upload-domain-certificate --account mysubaccount --user mymail@example.com --host hana.ondemand.com --name mycert --location ./certificate.pub --key-location ./certificate.key
```

It is not recommended, but if you decide to upload a private key \(for example, certificate.key\), it should follow one of these formats:

> ### Example:  
> ```
> -----BEGIN PRIVATE KEY-----
> Enter your private key.
> It must be without password, in Privacy-enhanced Electronic Mail (PEM) format (2048-4096 bits).
> -----END PRIVATE KEY-----
> ```

> ### Example:  
> ```
> -----BEGIN RSA PRIVATE KEY-----
> Enter your RSA private key.
> It must be without password, in Privacy-enhanced Electronic Mail (PEM) format (2048-4096 bits).
> -----END RSA PRIVATE KEY-----
> ```

**Related Information**  


[generate-csr](generate-csr-f02258d.md "Generates and returns a certificate signing request (CSR).")

[Configuring Custom Domains](configuring-custom-domains-77cf0e6.md#loio77cf0e6cd32e496c9cc8eeac4bedde94 "To make sure that your domain is trusted and all application data is protected, you need to first set up secure SSL communication. The next step will then be to make your application accessible via the custom domain and route traffic to it.")

