<!-- loioe8fc50cc0c0f410a8d8ec54f391d01dc -->

# list-ssl-hosts

Lists SSL hosts for a given subaccount.



> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of the following technology portfolios: application development; process automation; integration; data, analytics, and enterprise planning; artificial intelligence. The platform offers users the ability to turn data into business value, compose end-to-end business processes, connect entire IT landscapes, and personalize, build and extend SAP applications. This reduces the overall total cost of ownership maintaining SAP landscapes and third-party software across end-to-end business processes.") :arrow_upper_right:.**



```
neo list-ssl-hosts --account <subaccount_technical_name> --user <e-mail_or_user> --host <host> 
```

If you have several subaccounts in your global account, the `list-ssl-hosts` command returns all SSL hosts in these subaccounts.



## Parameters



To list all parameters available for this command, execute `neo help list-ssl-hosts` in the command line.


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

`Type`: URL. For acceptable values see [Regions](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/350356d1dc314d3199dca15bd2ab9b0e.html "You can deploy applications in different regions. Each region represents a geographical location (for example, Europe, US East) where applications, data, or services are hosted.") :arrow_upper_right:.

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
</table>



## Example

```
neo list-ssl-hosts --account mysubaccount --user mymail@example.com --host hana.ondemand.com 

```

**Related Information**  


[create-ssl-host](create-ssl-host-3c890d5.md "Creates an SSL host for configuration of custom domains. This SSL host will be serving your custom domain.")

[Create an SSL Host](configuring-custom-domains-77cf0e6.md#loio70f4d19d3dbd434aa9aa165d53e2896c "You have to create an SSL host that will serve your custom domain. This host holds the mapping between your chosen custom domain and the application on SAP BTP as well as the SSL configuration for secure communication through this custom domain.")

