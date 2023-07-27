<!-- loiob4f86d5166594f1bba5d6be97dd7affc -->

# update-db-binding

This command updates the credentials in an existing database binding.



> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://launchpad.support.sap.com/#/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**



You can set a new pair of database user and password, change the keystore, or switch from password- to certificate-based authentication or from certificate- to password-based authentication.



## Parameters


<table>
<tr>
<th valign="top" colspan="2">

Required



</th>
</tr>
<tr>
<td valign="top">

`--db-password`



</td>
<td valign="top">

Password of the database user used to access the database

\(Optional, needed only, when `--db-user` is specified\)

To protect your password, enter it only when prompted by the console client and not explicitly as a parameter in the properties file or the command line



</td>
</tr>
<tr>
<td valign="top">

`--db-user`



</td>
<td valign="top">

Name of the database user used to access the database. Use it to set password-based authentication and for bindings to productive HANA instances and databases. If omitted, you must specify `--keystore-name`



</td>
</tr>
<tr>
<td valign="top">

`--keystore-name`



</td>
<td valign="top">

Name of the keystore used to access the database. Use it to set authentication with an X.509 client certificate and for bindings to HANA databases on HANA 2 MDC systems \(only for HANA MDC databases with version 2.00.056 or higher\). If omitted, you must specify `--db-user`.



</td>
</tr>
<tr>
<td valign="top">

`--keystore-password`



</td>
<td valign="top">

Password of the keystore used to access the HANA database

\(Optional, needed only when --keystore-name is specified.\)

To protect your password, enter it only when prompted by the console client and not explicitly as a parameter in the properties file or the command line.



</td>
</tr>
<tr>
<td valign="top">

`-s`, `--data-source`



</td>
<td valign="top">

Name of the data source \(optional\)

Default: <DEFAULT\>

The application will be able to access this database via the specified data source.



</td>
</tr>
<tr>
<td valign="top">

`-a`, `--account`



</td>
<td valign="top">

Subaccount technical name



</td>
</tr>
<tr>
<td valign="top">

`-b`, `--application` 



</td>
<td valign="top">

Application name



</td>
</tr>
<tr>
<td valign="top">

`-h`, `--host`



</td>
<td valign="top">

Enter a region host.

`Type:` URL, for acceptable values see [Regions and Hosts Available for the Neo Environment](https://help.sap.com/viewer/ea72206b834e4ace9cd834feed6c0e09/Cloud/en-US/d722f7cea9ec408b85db4c3dcba07b52.html)



</td>
</tr>
<tr>
<td valign="top">

`-p`, `--password`



</td>
<td valign="top">

To protect your password, enter it only when prompted by the console client and not explicitly as a parameter in the properties file or the command line

`Type:` string



</td>
</tr>
<tr>
<td valign="top">

`-u`, `--user`



</td>
<td valign="top">

Use your e-mail, SAP ID, or user name

`Type:` string



</td>
</tr>
</table>

**Related Information**  


[unbind-db](unbind-db-46e24bb.md "This command unbinds a database from a Java application for a particular data source.")

[bind-db](bind-db-2a4e62e.md "This command binds an SAP HANA tenant database or SAP ASE user database to a Java application using a data source.")

[Binding SAP ASE Databases to Java Applications](https://help.sap.com/viewer/3fa880aa54b74110ae99ad01503fcd60/Cloud/en-US/9fe085ea6a50486e9c350cb20e451cdf.html "Use the SAP BTP cockpit or the console client to establish a data source binding between the application and the database in the Neo environment.") :arrow_upper_right:

[Binding SAP HANA Databases to Java Applications](https://help.sap.com/viewer/d4790b2de2f4429db6f3dff54e4d7b3a/Cloud/en-US/1742986c3cfa47099442aee0cf8df5e9.html "Establish a data source binding between your applications and the SAP HANA database in the Neo environment using the SAP BTP cockpit or the console client.") :arrow_upper_right:

[Bind Applications to Databases in the Same Global Account](https://help.sap.com/viewer/3fa880aa54b74110ae99ad01503fcd60/Cloud/en-US/907b1707dec64bd9bfcc85333ab4b65d.html "You use the cockpit or the console client in the Neo environment to bind a Java application that you deployed in one subaccount to an SAP ASE database that is owned by another subaccount.") :arrow_upper_right:

[Bind Applications to Databases in Other Subaccounts](https://help.sap.com/viewer/3fa880aa54b74110ae99ad01503fcd60/Cloud/en-US/667d7a43e38843988516e46923129b32.html "To bind applications to productive SAP ASE databases in other subaccounts, you use a remote access token that indicates that access to the database has been permitted.") :arrow_upper_right:

