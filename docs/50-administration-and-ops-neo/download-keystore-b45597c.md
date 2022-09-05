<!-- loiob45597c856244a55addd232386c7201b -->

# download-keystore

This command is used to download a keystore by downloading the keystore file. You can download keystores on subaccount, application, and subscription levels.



> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**



<a name="loiob45597c856244a55addd232386c7201b__section_N10019_N10016_N10001"/>

## Parameters

To list all parameters available for this command, execute ***neo help download-keystore*** in the command line.


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

Consumer subaccount technical name

The subaccount for which you provide username and password.

`Type`: string \(up to 30 characters; lowercase letters and numbers, starting with a letter\)



</td>
</tr>
<tr>
<td valign="top">

`-h`, `--host`



</td>
<td valign="top">

Enter a region host.

`Type`: URL, for acceptable values see [Regions](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/350356d1dc314d3199dca15bd2ab9b0e.html "You can deploy applications in different regions. Each region represents a geographical location (for example, Europe, US East) where applications, data, or services are hosted.") :arrow_upper_right:



</td>
</tr>
<tr>
<td valign="top">

`-n`,`--name`



</td>
<td valign="top">

Name of the keystore to be downloaded

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


<table>
<tr>
<th valign="top" colspan="2">

Optional



</th>
</tr>
<tr>
<td valign="top">

`-b`, `--application` 



</td>
<td valign="top">

Application name

-   Use `--application <consumer_application_name>` if the application is running in your subaccount.
-   Use `--application <provider_subaccount_technical_name>:<provider_application_name>` if the application is running in another subaccount.

 `Type`: string \(up to 30 characters; lowercase letters and numbers, starting with a letter\)



</td>
</tr>
<tr>
<td valign="top">

`-l`,`--location`



</td>
<td valign="top">

Local directory where the keystore will be saved. If it is not specified, the current directory is used.

`Type`: string



</td>
</tr>
<tr>
<td valign="top">

`-w`, `--overwrite` 



</td>
<td valign="top">

Overwrites a file with the same name if such already exists. If you do not explicitly include the `--overwrite` argument, you will be notified and asked if you want to overwrite the file.



</td>
</tr>
</table>



## Example

On Subscription Level

```
neo download-keystore --account <consumer_subaccount_technical_name> --application <provider_subaccount_technical_name>:<provider_application_name>
--user <e-mail_or_user> --location c:\temp --name KeyStore1 --host hana.ondemand.com
```

On Application Level

```
neo download-keystore --account <consumer_subaccount_technical_name> --application <consumer_application_name>
--user <user_ID> --location c:\temp --name KeyStore1 --host hana.ondemand.com
```

On Subaccount Level

```
neo download-keystore --account <consumer_subaccount_technical_name> --user <e-mail_or_user> 
--location c:\temp --name KeyStore1 --host hana.ondemand.com
```

**Related Information**  


[Keystore Console Commands](../60-security-neo/keystore-console-commands-20b6fbd.md)

[Keys and Certificates](../60-security-neo/keys-and-certificates-3735938.md)

[Using the Keystore Service for Client Side HTTPS Connections](../60-security-neo/using-the-keystore-service-for-client-side-https-connections-38144cd.md)

