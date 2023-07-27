<!-- loio99d2659da99a40218da107a5017f9fbf -->

# list-cas

Lists trusted CA certificates in a bundle or bundles that are assigned to an SSL host or hosts.



> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://launchpad.support.sap.com/#/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**



```
neo list-cas --account <subaccount_technical_name> --host <host> --user <e-mail_or_user>
```

If you have several subaccounts in your global account and you don't list a concrete bundle, the command returns all bundles in these subaccounts.



<a name="loio99d2659da99a40218da107a5017f9fbf__section_dbj_1gx_d2b"/>

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

Use your e-mail, SAP ID, or user name.

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

`--bundle` 



</td>
<td valign="top">

Name of the CA bundle that you want to view.

`Type`: string

You use this parameter instead of `--all`.



</td>
</tr>
<tr>
<td valign="top">

`--all` 



</td>
<td valign="top">

Lists the names of all bundles in the subaccount. Takes no value.

You use this parameter instead of `--bundle`.



</td>
</tr>
<tr>
<td valign="top">

`-f`, `--file-name` 



</td>
<td valign="top">

Path to the file where the CA bundle is downloaded.

`Type`: string

`Default`: The CA certificates are saved in the current folder in a file named after the CA bundle.

> ### Note:  
> If a file with the same name already exists in the specified directory, you will be asked if you want to overwrite the file.



</td>
</tr>
</table>



<a name="loio99d2659da99a40218da107a5017f9fbf__section_ncg_rsx_d2b"/>

## Example

If you want to list a specific bundle in a subaccount, execute:

```
neo list-cas --account mysubaccount --host hana.ondemand.com --user mymail@example.com --bundle mybundle
```

If you want to list all bundles in a subaccount, execute:

```
neo list-cas --account mysubaccount --host hana.ondemand.com --user mymail@example.com --all
```

**Related Information**  


[add-ca](add-ca-c102abb.md "Uploads a trusted CA certificate and adds it to a certificate authority (CA) bundle. If you don't have a CA bundle yet, it will be created automatically.")

[remove-ca](remove-ca-55b61e4.md "Removes trusted CAs from a bundle or deletes a whole bundle and all certificates in it.")

[set-ssl-host](set-ssl-host-2956975.md "Configures and updates an SSL host. Allows you to replace an SSL certificate with a different one, manage TLS protocol versions, and configure a bundle of trusted CAs.")

[Managing Client Certificate Authentication for Custom Domains](managing-client-certificate-authentication-for-custom-domains-286aa51.md "If you want your customers to use client certificates when they access your application on SAP BTP via a custom domain.")

