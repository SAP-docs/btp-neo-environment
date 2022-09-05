<!-- loio6b5dea07d9fe42b5b8e355f33a208bb0 -->

# restart-hana

Restarts an SAP HANA system or an SAP HANA database service.



> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**



> ### Note:  
> To use this command, log on with a user with administrative rights for the subaccount.

> ### Note:  
> The `restart-hana` operation will be executed asynchronously. Temporary downtime is expected for SAP HANA database system or SAP HANA XS Engine, including inability to work with SAP HANA studio, SAP HANA Web-based Development Workbench and Cockpit UIs dependent on SAP HANA XS.

This command has two alternative uses:

-   For restarting the entire SAP HANA database system \(including all tenant databases when working with SAP HANA tenant database systems\):

    ```
    neo restart-hana --host <host> --account <subaccount_technical_name> --user <e-mail_or_user> --id <SAP HANA system identifier> --system
    ```

-   For restarting an SAP HANA database service \(`indexserver`, `xsengine`\)

    ```
    neo restart-hana --host <host> --account <subaccount_technical_name> --user <e-mail_or_user> --id <SAP HANA system identifier> --service-name <service_name>
    ```


After you trigger the command, you can monitor the command execution in SAP HANA Studio, using *Configuration and Monitoring* \> *Open Administration*.



## Parameters



To list all parameters available for this command, execute ***neo help restart-hana*** in the command line.


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

The ID of a productive SAP HANA database system

> ### Note:  
> You can find the SAP HANA database system ID using the [list-dbms](list-dbms-1ea1771.md) command or in the *Databases & Schemas* section in the cockpit by navigating to *SAP HANA / SAP ASE* \> *Databases & Schemas*.

It must start with a letter and can contain uppercase and lowercase letters \('a' - 'z', 'A' - 'Z'\), numbers \('0' - '9'\), and the special characters '.' and '-'.

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

`-u`, `--user`



</td>
<td valign="top">

Your e-mail, SAP ID, or SCN user name

`Type`: string



</td>
</tr>
<tr>
<td valign="top">

`--service-name`



</td>
<td valign="top">

The SAP HANA database service to be restarted. You can choose between the following values:

-   *xsengine* - for restarting the SAP HANA XS service
-   *indexserver* - for restarting the SAP HANA index server



</td>
</tr>
<tr>
<td valign="top">

`--system`



</td>
<td valign="top">

If available, the entire SAP HANA database system will be restarted.



</td>
</tr>
</table>



## Example

To restart the SAP HANA database system with ID `myhanaid` running on the productive host, execute:

```
neo restart-hana --system --id myhanaid --account mysubaccount --host hana.ondemand.com --user mymail@example.com
```

To restart the SAP XS Engine service on SAP HANA database system with ID `myhanaid`, execute:

```
neo restart-hana --service-name xsengine --id myhanaid --account mysubaccount --host hana.ondemand.com --user mymail@example.com
```

**Related Information**  


[Restart Database Systems](https://help.sap.com/viewer/3fa880aa54b74110ae99ad01503fcd60/Cloud/en-US/10a8b11bdd9c4a84a26e00ec98b54e97.html "Restart your database systems in the Neo environment using the SAP BTP cockpit.") :arrow_upper_right:

[SAP HANA Administration Guide](https://help.sap.com/viewer/6b94445c94ae495c83a19646e7c3fd56/1.0.12/en-US)

[SAP BTP Release Notes](http://scn.sap.com/docs/DOC-28833)

