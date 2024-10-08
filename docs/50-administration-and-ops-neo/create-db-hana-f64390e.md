<!-- loiof64390e250cc4dcf8d9046192957d26a -->

# create-db-hana

This command creates an SAP HANA database with the specified ID and settings, on an SAP HANA tenant database system.



> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of the following technology portfolios: application development; process automation; integration; data, analytics, and enterprise planning; artificial intelligence. The platform offers users the ability to turn data into business value, compose end-to-end business processes, connect entire IT landscapes, and personalize, build and extend SAP applications. This reduces the overall total cost of ownership maintaining SAP landscapes and third-party software across end-to-end business processes.") :arrow_upper_right:.**



```
neo create-db-hana -a <subaccount_technical_name> -h <host> -u <e-mail_or_user> --dbsystem <database_system> -i <database_ID> --db-password <database_user_password>
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

`-h`, `--host`

</td>
<td valign="top">

Enter a region host.

`Type`: URL, for acceptable values see [Regions](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/350356d1dc314d3199dca15bd2ab9b0e.html "You can deploy applications in different regions. Each region represents a geographical location (for example, Europe, US East) where applications, data, or services are hosted.") :arrow_upper_right:

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

`-i`, `--id`

</td>
<td valign="top">

HANA database ID

`Type`: string

</td>
</tr>
<tr>
<td valign="top">

`--dbsystem`

</td>
<td valign="top">

ID of the SAP HANA database system

`Type`: string

</td>
</tr>
<tr>
<td valign="top">

`--db-password`

</td>
<td valign="top">

Password of the SYSTEM user used to access the SAP HANA database \(optional, queried at the command prompt if omitted\).

To protect your password, enter it only when prompted by the console client and not explicitly as a parameter in the properties file or the command line.

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

`--dp-server` 

</td>
<td valign="top">

Enables or disables the data processing server of the SAP HANA database: 'enabled', 'disabled' \(default\).

</td>
</tr>
<tr>
<td valign="top">

`--script-server` 

</td>
<td valign="top">

Enables or disables the script server of the SAP HANA database: 'enabled', 'disabled' \(default\).

</td>
</tr>
<tr>
<td valign="top">

`--web-access` 

</td>
<td valign="top">

Enables or disables access to the SAP HANA database from the Internet: 'enabled' \(default\), 'disabled'

</td>
</tr>
<tr>
<td valign="top">

`--xsengine-mode` 

</td>
<td valign="top">

Specifies how the XS engine should run: 'embedded' \(default\), 'standalone'.

</td>
</tr>
<tr>
<td valign="top">

`--docstore`

</td>
<td valign="top">

Enables or disables the DocStore server of SAP HANA database: 'enabled', 'disabled' \(default\).

</td>
</tr>
</table>

> ### Note:  
> There is a limit to the number of databases you can create, and you'll see an error message when you reach the maximum number of databases. For more information on tenant database limits, see [Creating Databases](https://help.sap.com/docs/sap-hana-service-for-sap-btp-in-sap-and-microsoft-azure-regions/sap-hana-service-for-sap-btp-in-sap-regions/creating-databases?version=Cloud).



## Example

```
neo create-db-hana -a mysubaccount -h hana.ondemand.com -u mymail@example.com --dbsystem mydbsys -i mydb --db-password SECRET
```

**Related Information**  


[Create SAP HANA Tenant Databases](https://help.sap.com/viewer/d4790b2de2f4429db6f3dff54e4d7b3a/Cloud/en-US/533384eda57e428f98a43815e6a11119.html#loio46af2934d19343ca8250ce288d27ea41 "Use the cockpit to create an SAP HANA tenant database on an SAP HANA database management system in your subaccount in the Neo environment.") :arrow_upper_right:

[delete-db-hana](delete-db-hana-628ae80.md "This command deletes the SAP HANA database with the specified ID on a SAP HANA database system enabled for multitenant database container support.")

