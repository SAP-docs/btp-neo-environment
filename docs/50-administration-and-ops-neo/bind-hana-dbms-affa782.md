<!-- loioaffa7822cef0400698c05d4f12f2e71f -->

# bind-hana-dbms

This command binds a Java application to an SAP HANA single-container database system \(XS\) via a data source.



> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://launchpad.support.sap.com/#/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**



You can only bind an application to an SAP HANA single-container database system \(XS\) if the application is deployed.

The following commands are available:

-   Database in the same subaccount:

    ```
    neo bind-hana-dbms -a <subaccount_technical_name> -b <application_name> -h <host> -u <e-mail_or_user> -i <productive_HANA_database> --db-user <database_user> --db-password <database_user_password>
    ```

-   Database in another subaccount:

    ```
    neo bind-hana-dbms -a <subaccount_technical_name> -b <application_name> -h <host> -u <e-mail_or_user> --access-token 120579jy40i15v1dqv3n3fsw40ug52m6re9fzqxg46l3fah0w0 --db-user <database_user> --db-password <database_user_password>
    ```

    > ### Note:  
    > To bind your application to a database that is owned by another subaccount of your global account, see [bind-db](bind-db-2a4e62e.md).




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

`Type`: URL, for acceptable values see [Regions and Hosts Available for the Neo Environment](../10-concepts-neo/regions-and-hosts-available-for-the-neo-environment-d722f7c.md)

> ### Note:  
> You cannot use this command in trial accounts.



</td>
</tr>
<tr>
<td valign="top">

`-i`, `--id`



</td>
<td valign="top">

ID of the SAP HANA single-container database system \(XS\)

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
<tr>
<td valign="top">

`--db-password`



</td>
<td valign="top">

Password of the database user used to access the SAP HANA single-container database system \(XS\)



</td>
</tr>
<tr>
<td valign="top">

`--db-user`



</td>
<td valign="top">

Name of the database user used to access the SAP HANA single-container database system \(XS\)



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

Type: string \(uppercase and lowercase letters, numbers, and the following special characters: \`/\`, \`\_\`, \`-\`, \`@\`. Do not use special characters as first or last charachters of the data source name.\)



</td>
</tr>
</table>



## Example

-   Database in the same subaccount:

    ```
    neo bind-hana-dbms -a mysubaccount -b myapp -h hana.ondemand.com -u mymail@example.com -i myhanaxs --db-user MYPRODHANA --db-password SECRET
    ```

-   Database in another subaccount:

    ```
    neo bind-hana-dbms -a mysubaccount -b myapp -h hana.ondemand.com -u mymail@example.com --db-user MYPRODHANA --db-password SECRET --access-token 120579jy40i15v1dqv3n3fsw40ug52m6re9fzqxg46l3fah0w0
    ```


**Related Information**  


[unbind-hana-dbms](unbind-hana-dbms-de4022e.md "This command unbinds a productive SAP HANA database system from a Java application for a particular data source.")

[Binding SAP HANA Databases to Java Applications](https://help.sap.com/viewer/d4790b2de2f4429db6f3dff54e4d7b3a/Cloud/en-US/1742986c3cfa47099442aee0cf8df5e9.html "Establish a data source binding between your applications and the SAP HANA database in the Neo environment using the SAP BTP cockpit or the console client.") :arrow_upper_right:

[Bind Applications to Databases in the Same Global Account](https://help.sap.com/viewer/3fa880aa54b74110ae99ad01503fcd60/Cloud/en-US/907b1707dec64bd9bfcc85333ab4b65d.html "You use the cockpit or the console client in the Neo environment to bind a Java application that you deployed in one subaccount to an SAP ASE database that is owned by another subaccount.") :arrow_upper_right:

[Bind Applications to Databases in Other Subaccounts](https://help.sap.com/viewer/3fa880aa54b74110ae99ad01503fcd60/Cloud/en-US/667d7a43e38843988516e46923129b32.html "To bind applications to productive SAP ASE databases in other subaccounts, you use a remote access token that indicates that access to the database has been permitted.") :arrow_upper_right:

