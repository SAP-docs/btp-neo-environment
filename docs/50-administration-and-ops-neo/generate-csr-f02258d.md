<!-- loiof02258d98b0246cc84a9dfdfe3642b83 -->

# generate-csr

Generates and returns a certificate signing request \(CSR\).



> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**



```
neo generate-csr --account <subaccount_technical_name> --user <e-mail_or_user> --host <host> --name <certificate_name> 
--certificate-distinguished-name <type0=value0,type1=value1,type2>
```



## Parameters



To list all parameters available for this command, execute `neo help generate-csr` in the command line.


<table>
<tr>
<th valign="top" colspan="2">

Required



</th>
</tr>
<tr>
<th valign="top" colspan="2">

Optional



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

Unique identifier of the certificate

`Type`: string

When generating a CSR, the certificate name must start with a letter and can only contain lowercase letters \(a-z\), uppercase letters \(A-Z\), numbers \(0-9\), underscores \( \_ \), and hyphens \(-\).



</td>
</tr>
<tr>
<td valign="top">

`-d`,`--certificate-distinguished-name`



</td>
<td valign="top">

Attributes of the CSR

`Type`: string \(formatted as type0=value0,type1=value1,type2=..., characters may be escaped by \\ \(backslash\), no spaces are skipped\)

`Allowed attributes`:

-   Country \(C\) – two-digit code - for example, ‘GB’
-   State \(ST\) – state or province name - for example, ‘Hampshire’
-   Locality \(L\) – city full name - for example, ‘Portsmouth’
-   Organization \(O\) – company name
-   Organizational Unit \(OU\) – for example, ‘IT Department’
-   Common Name \(CN\) – the domain name for which you are requesting the certificate - ‘`www.example.com`’
-   Email Address \(E\) – to validate the certificate request, some certificate authorities \(CA\) require the email address of the domain owner



</td>
</tr>
<tr>
<td valign="top">

`-s`, `--subject-alternative-name`



</td>
<td valign="top">

A comma-separated list of all domain names to be protected with this certificate, used as value for the Subject Alternative Name field of the generated certificate.

`Type`: string



</td>
</tr>
<tr>
<td valign="top">

`-g`, `--signature-algorithm` 



</td>
<td valign="top">

Signature algorithm

`Default`: SHA256withRSA

`Supported algorithms`: SHA256withRSA, SHA384withRSA, SHA512withRSA



</td>
</tr>
<tr>
<td valign="top">

`-k`, `--key-size` 



</td>
<td valign="top">

The size \(length\) of a generated key pair

`Supported sizes`: 2048, 4096



</td>
</tr>
</table>



## Example

```
neo generate-csr --account mysubaccount --user mymail@example.com --host hana.ondemand.com --name myfirstcert 
--certificate-distinguished-name "C=BG,O=MyCompany,CN=www.mycompany.bg,E=admin@mycompany.bg" --subject-alternative-name “www.mycompany.com,www.mycompany.net”
```

**Related Information**  


[Configuring Custom Domains](configuring-custom-domains-77cf0e6.md#loio77cf0e6cd32e496c9cc8eeac4bedde94 "To make sure that your domain is trusted and all application data is protected, you need to first set up secure SSL communication. The next step will then be to make your application accessible via the custom domain and route traffic to it.")

[list-domain-certificates](list-domain-certificates-dfb8438.md "Use this command to list certificates available for a custom domain.")

[delete-domain-certificate](delete-domain-certificate-c3076cc.md "Deletes a certificate.")

