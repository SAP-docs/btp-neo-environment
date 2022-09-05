<!-- loio8b08f499fbe648b39d384b4a80a7b374 -->

# add-ecm-tenant

Adds a new tenant to a repository.



> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**



```
neo add-ecm-tenant --account <subaccount_technical_name>  --host <host> --user <e-mail_or_user> --name <repository_name> --key <repository_key> --tenant <tenant_name> --virus-scan <true/false> 
```



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

Specify an existing subaccount of which you are already a member.

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

Name of the repository

`Type`: string



</td>
</tr>
<tr>
<td valign="top">

`-t`, `--tenant`



</td>
<td valign="top">

Tenant alias

`Type`: string



</td>
</tr>
<tr>
<td valign="top">

`-k`, `--key`



</td>
<td valign="top">

Key of the repository

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

`-v`, `--virus-scan`



</td>
<td valign="top">

Can be used to activate the virus scanner and check all incoming documents for viruses.

`Default`: `true`

`Type`: boolean

> ### Recommendation:  
> For repositories that are used by untrusted users and or for unknown content, we recommend that you enable the virus scanner by setting this parameter to `true`. Enabling the virus scanner could impair the upload performance.

If a virus is detected, the upload process for the document fails with a virus scanner exception.



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
</table>



## Example

```
neo add-ecm-tenant --account sap --host hana.ondemand.com --user <myemail@example.com> --name DemoRepository --key ecm_012345689  --tenant sap2 --virus-scan true
```

This example adds the *sap2* tenant to the *DemoRepository* repository.

