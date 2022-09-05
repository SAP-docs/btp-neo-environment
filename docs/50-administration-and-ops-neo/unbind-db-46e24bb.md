<!-- loio46e24bb9d5ef4c2cb5cfdde8ed751e28 -->

# unbind-db

This command unbinds a database from a Java application for a particular data source.



> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**



The application retains access to the database until the next application restart. After the restart, the application will no longer be able to access it.

```
neo unbind-db -a <subaccount_technical_name> -b <application_name> -h <host> -u <e-mail_or_user>
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

`Type`: string \(up to 30 characters; lowercase letters and numbers, starting with a letter\)



</td>
</tr>
<tr>
<td valign="top">

`-b`, `--application`



</td>
<td valign="top">

Application name

 `Type`: string \(up to 30 characters; lowercase letters and numbers, starting with a letter\)



</td>
</tr>
<tr>
<td valign="top">

`-h`, `--host`



</td>
<td valign="top">

Enter a region host.

`Type`: URL, for acceptable values see [Regions](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/350356d1dc314d3199dca15bd2ab9b0e.html "You can deploy applications in different regions. Each region represents a geographical location (for example, Europe, US East) where applications, data, or services are hosted.") :arrow_upper_right:.



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

Use your e-mail, SAP ID, or user name

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

`-s`, `--data-source`



</td>
<td valign="top">

Data source name

Default: <DEFAULT\>



</td>
</tr>
</table>



## Example

```
neo unbind-db -a mysubaccount -b myapp -h hana.ondemand.com -u mymail@example.com
```

**Related Information**  


[bind-db](bind-db-2a4e62e.md "This command binds an SAP HANA tenant database or SAP ASE user database to a Java application using a data source.")

[update-db-binding](update-db-binding-b4f86d5.md "This command updates the credentials in an existing database binding.")

[Binding SAP HANA Databases to Java Applications](https://help.sap.com/viewer/d4790b2de2f4429db6f3dff54e4d7b3a/Cloud/en-US/1742986c3cfa47099442aee0cf8df5e9.html "Establish a data source binding between your applications and the SAP HANA database in the Neo environment using the SAP BTP cockpit or the console client.") :arrow_upper_right:

[Binding SAP ASE Databases to Java Applications](https://help.sap.com/viewer/3fa880aa54b74110ae99ad01503fcd60/Cloud/en-US/9fe085ea6a50486e9c350cb20e451cdf.html "Use the SAP BTP cockpit or the console client to establish a data source binding between the application and the database in the Neo environment.") :arrow_upper_right:

[Bind Applications to Databases in the Same Global Account](https://help.sap.com/viewer/3fa880aa54b74110ae99ad01503fcd60/Cloud/en-US/907b1707dec64bd9bfcc85333ab4b65d.html "You use the cockpit or the console client in the Neo environment to bind a Java application that you deployed in one subaccount to an SAP ASE database that is owned by another subaccount.") :arrow_upper_right:

[Bind Applications to Databases in Other Subaccounts](https://help.sap.com/viewer/3fa880aa54b74110ae99ad01503fcd60/Cloud/en-US/667d7a43e38843988516e46923129b32.html "To bind applications to productive SAP ASE databases in other subaccounts, you use a remote access token that indicates that access to the database has been permitted.") :arrow_upper_right:

