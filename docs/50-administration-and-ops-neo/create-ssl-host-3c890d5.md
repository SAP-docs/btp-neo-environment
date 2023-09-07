<!-- loio3c890d5a4dfc44dab970d9a29b443ca7 -->

# create-ssl-host

Creates an SSL host for configuration of custom domains. This SSL host will be serving your custom domain.



> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**



```
neo create-ssl-host --account <subaccount_technical_name> --user <e-mail_or_user> --host <host> --name <ssl_host_name>
```



## Parameters



To list all parameters available for this command, execute `neo help create-ssl-host` in the command line.


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

`Type`: URL. For acceptable values see [Regions](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/350356d1dc314d3199dca15bd2ab9b0e.html "You can deploy applications in different regions. Each region represents a geographical location (for example, Europe, US East) where applications, data, or services are hosted.") :arrow_upper_right:



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

Use your email, SAP ID, or username.

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

`-n`, `--name`



</td>
<td valign="top">

Unique identifier of the SSL host. If not specified, 'default' value is set.

`Type`: string

When creating a new SSL host, the SSL host name must start with a letter and can only contain lowercase letters \(a-z\), uppercase letters \(A-Z\), numbers \(0-9\), underscores \( \_ \), and hyphens \(-\).



</td>
</tr>
</table>



## Example

```
neo create-ssl-host --account mysubaccount --user mymail@example.com --host hana.ondemand.com --name mysslhostname
 
```

> ### Note:  
> In the command output, you get the SSL host. For example, `"A new SSL host [mysslhostname] was created and is now accessible on host [123456.ssl.ondemand.com]"`. Write down the `123456.ssl.ondemand.com` host as you will later need it for the DNS configuration.

**Related Information**  


[Create an SSL Host](configuring-custom-domains-77cf0e6.md#loio70f4d19d3dbd434aa9aa165d53e2896c "You have to create an SSL host that will serve your custom domain. This host holds the mapping between your chosen custom domain and the application on SAP BTP as well as the SSL configuration for secure communication through this custom domain.")

[Configuring Custom Domains](configuring-custom-domains-77cf0e6.md#loio77cf0e6cd32e496c9cc8eeac4bedde94 "To make sure that your domain is trusted and all application data is protected, you need to first set up secure SSL communication. The next step will then be to make your application accessible via the custom domain and route traffic to it.")

