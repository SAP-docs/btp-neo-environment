<!-- loio9e3f90f2ead74229ac5c8848ed5bf292 -->

# open-db-tunnel

This command opens a database tunnel to the database system associated with the specified schema or database.



> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**



> ### Note:  
> Make sure that you have installed the required tools correctly.
> 
> If you face trouble using this command, please check that your installation is correct.
> 
> For more information, see [Set Up the Console Client](../30-development-neo/set-up-the-console-client-7613dee.md) and [Using the Console Client](using-the-console-client-8900b22.md).



The command has two modes:

-   Default mode: The tunnel remains open until you explicitly close it by pressing [ENTER\] in the command line. It is closed automatically after 24 hours or if the command window is closed.

    ```
    neo open-db-tunnel -a <subaccount_technical_name> -h <host> -u <user> -i <ID_or_alias>
    ```

-   Background mode: The database tunnel is opened in a separate process. Use the `close-db-tunnel` command to close the tunnel once you are done, or it is closed automatically after one hour.

    ```
    neo open-db-tunnel -a <subaccount_technical_name> -h <host> -u <user> -i <ID_or_alias> --background
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

`Type`: URL. For acceptable values see [Regions](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/350356d1dc314d3199dca15bd2ab9b0e.html "You can deploy applications in different regions. Each region represents a geographical location (for example, Europe, US East) where applications, data, or services are hosted.") :arrow_upper_right:.



</td>
</tr>
<tr>
<td valign="top">

`-i`, `--id`



</td>
<td valign="top">

-   SAP ASE database system \(***ASE***\): Specify the database ID of an SAP ASE user database.

-   SAP HANA tenant database system \(***HANAMDC***\): Specify the database ID of an SAP HANA tenant database.

-   SAP HANA single-container database system \(***HANAXS***\): Specify the alias of the database system.

-   Shared SAP HANA database: Specify the schema ID of a schema.


`Type`: string



</td>
</tr>
<tr>
<td valign="top">

`--access-token`



</td>
<td valign="top">

Identifies a database access permission. The access token and database ID parameters are mutually exclusive.



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

`--background`



</td>
<td valign="top">

Opens the tunnel session in a background process

`Type`: switch, takes no value



</td>
</tr>
<tr>
<td valign="top">

`--output`



</td>
<td valign="top">

Prints information about the tunnel in a special output format.

`Acceptable values`: 'json'

`Type`: string



</td>
</tr>
</table>



## Example

```
neo open-db-tunnel -a mysubaccount -h us2.hana.ondemand.com -u mymail@example.com -i mydatabase
```

**Related Information**  


[Accessing Databases Remotely](https://help.sap.com/viewer/3fa880aa54b74110ae99ad01503fcd60/Cloud/en-US/2a795b95e44c42d08c446893a07921db.html "Access remote database instances through a database tunnel in the Neo environment, which provides a secure connection from your local machine and bypasses any firewalls.") :arrow_upper_right:

[Open Database Tunnels](https://help.sap.com/viewer/3fa880aa54b74110ae99ad01503fcd60/Cloud/en-US/6930850a8f9a40489c01ed1aa381946d.html "Use the open-db-tunnel command to open a tunnel and to get the connection details required for the remote database instance. The database tunnel allows you to connect to a remote database instance through a secure connection.") :arrow_upper_right:

[Connect to SAP HANA Databases via the Eclipse IDE](https://help.sap.com/viewer/d4790b2de2f4429db6f3dff54e4d7b3a/Cloud/en-US/4efc124a0ccc42b3b502ad3a3908d23d.html "Connect to an SAP HANA single-container (XS) or tenant database system (MDC) using SAP HANA tools via the Eclipse IDE.") :arrow_upper_right:

[Connect to SAP HANA Schemas via the Eclipse IDE (Neon)](https://help.sap.com/viewer/d4790b2de2f4429db6f3dff54e4d7b3a/Cloud/en-US/c597f8231b4e463da0dcc3095ea139b7.html "Establish a direct connection to a shared SAP HANA schema via the Eclipse IDE (Neon) using SAP HANA tools.") :arrow_upper_right:

[close-db-tunnel](close-db-tunnel-c7c36e6.md "This command closes one or all database tunnel sessions that have been opened in a background process using the open-db-tunnel --background command.")

[Connect to the Remote SAP ASE Database](https://help.sap.com/viewer/3fa880aa54b74110ae99ad01503fcd60/Cloud/en-US/107ffdb907334d97be99fdcb7aad8961.html "Use the Eclipse Data Tools Platform (DTP) to connect to the SAP ASE database in the cloud. You'll need the connection details you obtained when you opened the database tunnel.") :arrow_upper_right:

[Automating the Use of Database Tunnels](https://help.sap.com/viewer/3fa880aa54b74110ae99ad01503fcd60/Cloud/en-US/49626c9474584bbfa4a936975b851326.html "For continuous delivery and automated tests, the open-db-tunnel command supports a background mode, which allows a database tunnel to be opened by automated scripts or as part of a Maven build.") :arrow_upper_right:

[Machine-Readable Command Output](machine-readable-command-output-b35e1e9.md "")

[Connect DB Tools to SAP HANA via Service Channels](https://help.sap.com/viewer/b865ed651e414196b39f8922db2122c7/Cloud/en-US/64d6a510e98941d28dbff2fc8179f175.html "") :arrow_upper_right:

