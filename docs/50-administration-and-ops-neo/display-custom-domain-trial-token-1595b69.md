<!-- loio1595b69ea5ec4ddc8fc7c04ac3d0f10e -->

# display-custom-domain-trial-token

Displays the third-party cookie deprecation \(TPCD\) trial token for a custom domain. This token allows you to continue using restricted third-party cookies in your browser.



> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/docs/btp/sap-business-technology-platform/sap-business-technology-platform?version=Cloud) .**



```
neo display-custom-domain-trial-token --account <subaccount_technical_name> --user <e-mail_or_user> --host <host> --custom-domain <custom_domain>
```



## Parameters



To list all parameters available for this command, execute `neo help display-custom-domain-trial-token` in the command line.


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

Use your email, SAP ID, or user name.

`Type`: string

</td>
</tr>
<tr>
<td valign="top">

`-e`, `--custom-domain`

</td>
<td valign="top">

Custom domain for accessing the application

`Type`: string \(hostname such as mydomain.com or shop.mydomain.com corresponding to the CN/SAN of the certificate\)

</td>
</tr>
</table>



## Example

```
neo display-custom-domain-trial-token --account mysubaccount --user mymail@example.com --host hana.ondemand.com --custom-domain www.example.com
```

**Related Information**  


[SAP Note 3409306 - Removal of Third-Party Cookies in Google Chrome and Microsoft Edge Browser](https://me.sap.com/notes/3409306)

[remove-custom-domain-trial-token](remove-custom-domain-trial-token-6e63a36.md "Removes a third-party cookie deprecation (TPCD) trial token from a custom domain.")

[set-custom-domain-trial-token](set-custom-domain-trial-token-576c038.md "Sets a third-party cookie deprecation (TPCD) trial token for a custom domain. Set this token to continue using restricted third-party cookies in your browser.")

