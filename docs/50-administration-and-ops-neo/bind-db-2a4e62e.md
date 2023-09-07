<!-- loio2a4e62e1c1f24090bda5679936a32429 -->

# bind-db

This command binds an SAP HANA tenant database or SAP ASE user database to a Java application using a data source.



> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**



You can only bind an application to an SAP HANA tenant database or SAP ASE user database if the application is deployed.

You can use the following types of authentication against the database:

-   Password-based authentication using a combination of database user and database password

-   For SAP HANA tenant database only: X.509 client certificate authentication using a combination of keystore name and keystore password

    -   Supported only for HANA MDC databases with version 2.00.056 or higher

    -   The application must be deployed on one of these application runtimes:

        -   Java Web Tomcat 8 \(minimum version 3.145\)

        -   Java Web Tomcat 9 \(minimum version 4.19\)

        -   Java EE 7 Web Profile TomEE 7 \(minimum version 1.114\)






You can use the following examples for both authentication types, password-based or X.509 client certificate authentication:

-   Database in the same subaccount:

    ```
    neo bind-db -a <subaccount_technical_name> -b <application_name> -h <host> -u <e-mail_or_user> -i <database_ID> --db-user <database_user> --db-password <database_user_password>
    ```

-   Database in another accout \(same global account\):

    > ### Note:  
    > To bind your application to a database that is owned by another subaccount of your global account, you need permission to use it. See [Sharing Databases in the Same Global Account](https://help.sap.com/viewer/3fa880aa54b74110ae99ad01503fcd60/Cloud/en-US/1cc5e1efb7f640329f419b53f21c0906.html "You can share SAP ASE databases that have been provisioned in a subaccount with other subaccounts of your global account in the Neo environment.") :arrow_upper_right:.

    ```
    neo bind-db -a <subaccount_technical_name> -b <application_name> -h <host> -u <e-mail_or_user> -i <owner_subaccount>:<database_ID> --db-user <database_user> --db-password <database_user_password>
    ```

-   Database in another subaccount:

    ```
    neo bind-db -a <subaccount_technical_name> -b <application_name> -h <host> -u <e-mail_or_user> --access-token vm6431dhjcr2e3dbt0fk6jpzm2w7oo3q48yumf1c6uu8b9pt9z --db-user <database_user> --db-password <database_user_password>
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

`Type`: URL, for acceptable values see [Regions and Hosts Available for the Neo Environment](../10-concepts-neo/regions-and-hosts-available-for-the-neo-environment-d722f7c.md)



</td>
</tr>
<tr>
<td valign="top">

`-i`, `--id`



</td>
<td valign="top">

Database ID

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

`--db-user`



</td>
<td valign="top">

Name of the database user used to access the database

Use it only to set password-based authentication and for bindings to productive HANA instances and databases. If skipped, you must specify `--keystore-name`.



</td>
</tr>
<tr>
<td valign="top">

`--db-password`



</td>
<td valign="top">

Password of the database user used to access the database

\(Optional, needed only when `--db-user` is specified.\)

To protect your password, enter it only when prompted by the console client and not explicitly as a parameter in the properties file or the command line.



</td>
</tr>
<tr>
<td valign="top">

`--keystore-name`



</td>
<td valign="top">

Name of the keystore used to access the HANA database

Use it only to set authentication with an X.509 client certificate and for bindings to HANA databases on HANA 2 MDC systems. If skipped, you must specify `--db-user`. \(Only for HANA MDC databases with version 2.00.056 or higher\).



</td>
</tr>
<tr>
<td valign="top">

`--keystore-password`



</td>
<td valign="top">

Password of the keystore used to access the HANA database

\(Optional, needed only when `--keystore-name` is specified.\)

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

Type: string \(uppercase and lowercase letters, numbers, and the following special characters: \`/\`, \`\_\`, \`-\`, \`@\`. Do not use special characters as first or last charachters of the data source name.\)



</td>
</tr>
</table>



## Example

-   Database in the same subaccount:

    ```
    neo bind-db -a mysubaccount -b myapp -h hana.ondemand.com -u mymail@example.com -i mydb --db-user MYDBUSER --db-password SECRET
    ```

-   Database in another subaccount \(same global account\):

    ```
    neo bind-db -a mysubaccount -b myapp -h hana.ondemand.com -u mymail@example.com -i anothersubaccount:anothersubaccountsdb --db-user MYDBUSER --db-password SECRET
    ```

-   Database in another subaccount:

    ```
    neo bind-db -a mysubaccount -b myapp -h hana.ondemand.com -u mymail@example.com --access-token 120579jy40i15v1dqv3n3fsw40ug52m6re9fzqxg46l3fah0w0 --db-user MYDBUSER --db-password SECRET
    ```


**Related Information**  


[unbind-db](unbind-db-46e24bb.md "This command unbinds a database from a Java application for a particular data source.")

[update-db-binding](update-db-binding-b4f86d5.md "This command updates the credentials in an existing database binding.")

[Binding SAP HANA Databases to Java Applications](https://help.sap.com/viewer/d4790b2de2f4429db6f3dff54e4d7b3a/Cloud/en-US/1742986c3cfa47099442aee0cf8df5e9.html "Establish a data source binding between your applications and the SAP HANA database in the Neo environment using the SAP BTP cockpit or the console client.") :arrow_upper_right:

[Binding SAP ASE Databases to Java Applications](https://help.sap.com/viewer/3fa880aa54b74110ae99ad01503fcd60/Cloud/en-US/9fe085ea6a50486e9c350cb20e451cdf.html "Use the SAP BTP cockpit or the console client to establish a data source binding between the application and the database in the Neo environment.") :arrow_upper_right:

[Bind Applications to Databases in the Same Global Account](https://help.sap.com/viewer/3fa880aa54b74110ae99ad01503fcd60/Cloud/en-US/907b1707dec64bd9bfcc85333ab4b65d.html "You use the cockpit or the console client in the Neo environment to bind a Java application that you deployed in one subaccount to an SAP ASE database that is owned by another subaccount.") :arrow_upper_right:

[Bind Applications to Databases in Other Subaccounts](https://help.sap.com/viewer/3fa880aa54b74110ae99ad01503fcd60/Cloud/en-US/667d7a43e38843988516e46923129b32.html "To bind applications to productive SAP ASE databases in other subaccounts, you use a remote access token that indicates that access to the database has been permitted.") :arrow_upper_right:

