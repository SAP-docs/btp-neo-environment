<!-- loioc102abb0801d45f487042ff0415d4760 -->

# add-ca

Uploads a trusted CA certificate and adds it to a certificate authority \(CA\) bundle. If you don't have a CA bundle yet, it will be created automatically.



> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://launchpad.support.sap.com/#/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**



```
neo add-ca --account <subaccount_technical_name> --host <host> --user <e-mail_or_user> --bundle <bundle_name> --location ./certificate_name.crt
```

To configure a CA bundle, run `set-ssl-host` using the `--ca-bundle` parameter. For more information, see [set-ssl-host](set-ssl-host-2956975.md).




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

Use your e-mail, SAP ID, or user name.

`Type`: string



</td>
</tr>
<tr>
<td valign="top">

`--bundle` 



</td>
<td valign="top">

Name of a new or existing bundle in which CAs will be added. You can have several CA bundles, but you can assign only one bundle to one SSL host. One bundle can hold up to 150 certificates.

`Type`: string

When creating a new bundle, the bundle name must start with a letter and can only contain lowercase letters \(a-z\), uppercase letters \(A-Z\), numbers \(0-9\), underscores \( \_ \), and hyphens \(-\).



</td>
</tr>
<tr>
<td valign="top">

`-l`, `--location` 



</td>
<td valign="top">

Path to a file that contains one or more certificates of trusted CAs in PEM format.



</td>
</tr>
</table>



<a name="loioc102abb0801d45f487042ff0415d4760__section_jbj_n3x_d2b"/>

## Example

```
neo add-ca --account mysubaccount --host hana.ondemand.com --user mymail@example.com --bundle mybundle --location ./mycert.crt
```

**Related Information**  


[list-cas](list-cas-99d2659.md "Lists trusted CA certificates in a bundle or bundles that are assigned to an SSL host or hosts.")

[remove-ca](remove-ca-55b61e4.md "Removes trusted CAs from a bundle or deletes a whole bundle and all certificates in it.")

[set-ssl-host](set-ssl-host-2956975.md "Configures and updates an SSL host. Allows you to replace an SSL certificate with a different one, manage TLS protocol versions, and configure a bundle of trusted CAs.")

[Managing Client Certificate Authentication for Custom Domains](managing-client-certificate-authentication-for-custom-domains-286aa51.md "If you want your customers to use client certificates when they access your application on SAP BTP via a custom domain.")

