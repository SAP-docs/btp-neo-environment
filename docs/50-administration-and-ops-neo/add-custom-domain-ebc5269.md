<!-- loioebc5269d0df34330b9a68fe1b8adc3ef -->

# add-custom-domain

Use this command to add a custom domain to an application URL. This will route the traffic for the custom domain to your application on SAP BTP.



> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**



```
neo add-custom-domain --account <subaccount_technical_name> --user <e-mail_or_user> --host <host> --custom-domain <custom_domain> 
--application-url <app_url> --ssl-host <ssl_hostname>
```



## Parameters



To list all parameters available for this command, execute `neo help add-custom-domain` in the command line.


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

`-i`, `--application-url`



</td>
<td valign="top">

The access point of the application on SAP BTP default domains \(hana.ondemand.com, etc.\)

`Type`: string \(hostname such as myapp.hana.ondemand.com or shop-mytenant.hana.ondemand.com\)

Query strings are not supported in the `--application-url` parameter and are ignored. For example, if you specify “mysubaccountmyapp.hana.ondemand.com/sites?idp=example”, the “?idp=example” part will be ignored.

> ### Note:  
> For SAP Cloud Integration applications, the application URL is formed differently. For more information, see [Configuring Custom Domains for SAP Cloud Integration](https://help.sap.com/viewer/368c481cd6954bdfa5d0435479fd4eaf/Cloud/en-US/7230b9ff41914cc0969223e6a020104b.html).



</td>
</tr>
<tr>
<td valign="top">

`-l`, `--ssl-host`



</td>
<td valign="top">

SSL host as defined with the `--name` parameter when created, or 'default' if not specified.



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

`--disable-application-url`



</td>
<td valign="top">

Allows you to disable the access to the platform URL, for example `hana.ondemand.com`, for subscribed applications with a URL of type `https://<application_name><provider_subaccount>-<consumer_subaccount>.<domain>`. The *<domain\>* is the respective region host. For example, `us1.hana.ondemand.com`.

> ### Note:  
> It may take up to one hour for this change to take effect.

`Type`: takes no value

If you do not explicitly use this parameter, your subscribed application will continue to be accessible via the default URL `hana.ondemand.com`.



</td>
</tr>
</table>



## Example

```
neo add-custom-domain --account mysubaccount --user mymail@example.com --host hana.ondemand.com --custom-domain www.example.com 
--application-url mysubaccountmyapp-subscription.hana.ondemand.com --ssl-host mysslhostname
```

**Related Information**  


[Add the Custom Domain](configuring-custom-domains-77cf0e6.md#loiobf395cf25683491eabefadb4383ed7ff "To make your application on the platform accessible via the custom domain, you need to map the custom domain to the application URL.")

[list-custom-domain-mappings](list-custom-domain-mappings-7dfeeb2.md "Lists custom domains configured as access points for applications in a subaccount.")

[remove-custom-domain](remove-custom-domain-de15ca8.md "Removes a custom domain as an access point of an application. Use this command if you no longer want an application to be accessible on the configured custom domain.")

[Configuring Custom Domains](configuring-custom-domains-77cf0e6.md#loio77cf0e6cd32e496c9cc8eeac4bedde94 "To make sure that your domain is trusted and all application data is protected, you need to first set up secure SSL communication. The next step will then be to make your application accessible via the custom domain and route traffic to it.")

[Configuring Custom Domains for SAP Cloud Integration](https://help.sap.com/viewer/368c481cd6954bdfa5d0435479fd4eaf/Cloud/en-US/7230b9ff41914cc0969223e6a020104b.html)

