<!-- loio576c038be58646b6af46cb052e282a97 -->

# set-custom-domain-trial-token

Sets a third-party cookie deprecation \(TPCD\) trial token for a custom domain. Set this token to continue using restricted third-party cookies in your browser.



> ### Note:  
> This is a temporary token. You should consider migrating to a sustainable solution.

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of the following technology portfolios: application development; process automation; integration; data, analytics, and enterprise planning; artificial intelligence. The platform offers users the ability to turn data into business value, compose end-to-end business processes, connect entire IT landscapes, and personalize, build and extend SAP applications. This reduces the overall total cost of ownership maintaining SAP landscapes and third-party software across end-to-end business processes.") :arrow_upper_right:.**



```
neo set-custom-domain-trial-token --account <subaccount_technical_name> --user <e-mail_or_user> --host <host> --custom-domain <custom_domain> --token <TPCD_trial_token>
```



## Parameters



To list all parameters available for this command, execute `neo help set-custom-domain-trial-token` in the command line.


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
<tr>
<td valign="top">

`--token`

</td>
<td valign="top">

The TPCD trial token to set to a custom domain

</td>
</tr>
</table>



## Example

```
neo set-custom-domain-trial-token --account mysubaccount --user mymail@example.com --host hana.ondemand.com --custom-domain www.example.com --token Bgh2kx3ak4p
```

**Related Information**  


[SAP Note 3409306 - Removal of Third-Party Cookies in Google Chrome and Microsoft Edge Browser](https://me.sap.com/notes/3409306)

[display-custom-domain-trial-token](display-custom-domain-trial-token-1595b69.md "Displays the third-party cookie deprecation (TPCD) trial token for a custom domain. This token allows you to continue using restricted third-party cookies in your browser.")

[remove-custom-domain-trial-token](remove-custom-domain-trial-token-6e63a36.md "Removes a third-party cookie deprecation (TPCD) trial token from a custom domain.")

