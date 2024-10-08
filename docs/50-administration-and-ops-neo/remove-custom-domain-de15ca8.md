<!-- loiode15ca85ffab4301986c89e7ed239ece -->

# remove-custom-domain

Removes a custom domain as an access point of an application. Use this command if you no longer want an application to be accessible on the configured custom domain.



> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of the following technology portfolios: application development; process automation; integration; data, analytics, and enterprise planning; artificial intelligence. The platform offers users the ability to turn data into business value, compose end-to-end business processes, connect entire IT landscapes, and personalize, build and extend SAP applications. This reduces the overall total cost of ownership maintaining SAP landscapes and third-party software across end-to-end business processes.") :arrow_upper_right:.**



```
neo remove-custom-domain --account <subaccount_technical_name> --user <e-mail_or_user> --host <host> --custom-domain <custom_domain> --ssl-host <ssl_host>
```



## Parameters



To list all parameters available for this command, execute `neo help remove-custom-domain` in the command line.


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
<tr>
<td valign="top">

`-e`, `--custom-domain`

</td>
<td valign="top">

Custom domain for accessing the application

`Type`: string \(Fully qualified domain name - FQDN\)

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
neo remove-custom-domain --account mysubaccount --user mymail@example.com --host hana.ondemand.com --custom-domain www.example.com --ssl-host mysslhostname
```

**Related Information**  


[add-custom-domain](add-custom-domain-ebc5269.md "Use this command to add a custom domain to an application URL. This will route the traffic for the custom domain to your application on SAP BTP.")

[Add the Custom Domain](configuring-custom-domains-77cf0e6.md#loiobf395cf25683491eabefadb4383ed7ff "To make your application on the platform accessible via the custom domain, you need to map the custom domain to the application URL.")

[Configuring Custom Domains](configuring-custom-domains-77cf0e6.md#loio77cf0e6cd32e496c9cc8eeac4bedde94 "To make sure that your domain is trusted and all application data is protected, you need to first set up secure SSL communication. The next step will then be to make your application accessible via the custom domain and route traffic to it.")

