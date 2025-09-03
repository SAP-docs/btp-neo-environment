<!-- loioacb8f74fc20d478a98de550a1e314b38 -->

# copy-db-hana-certificates

This command copies certificates from the file-based certificate store of the tenant database to the SAML and X509 certificate collections of the in-database certificate store of a HANA tenant database. After the certificates are copied, all extra certificates are removed from the file-based certificate store. The file-based store is then disabled, and the in-database certificate store is enabled. The command can only be executed once, if the in-database certificate store is already enabled, the command will not execute.



> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/docs/btp/sap-business-technology-platform/sap-business-technology-platform?version=Cloud) .**



```
neo copy-db-hana-certificates -a <subaccount_technical_name> -h <host> -u <e-mail_or_user> -i <database_ID> --db-user <dbuser> --db-password <database_user_password>
```



<a name="loioacb8f74fc20d478a98de550a1e314b38__section_l3m_wn4_3qb"/>

## Parameters


<table>
<tr>
<th valign="top" colspan="2">

Required

</th>
</tr>
<tr>
<td valign="top">

`-i`, `--id`

</td>
<td valign="top">

HANA database ID

`Type`: string

> ### Note:  
> The tenant database must be started.



</td>
</tr>
<tr>
<td valign="top">

, `--db-user`

</td>
<td valign="top">

Name of the SAP HANA tenant database user used for the operation

`Type`: string

> ### Note:  
> The database user must have the following privileges in the HANA tenant database: "USER ADMIN", "CERTIFICATE ADMIN", "TRUST ADMIN".



</td>
</tr>
<tr>
<td valign="top">

`--db-password`

</td>
<td valign="top">

Password of the SAP HANA tenant database user \(optional, queried at the command prompt if omitted\).

To protect your password, enter it only when prompted by the console client and not explicitly as a parameter in the properties file or the command line.

</td>
</tr>
</table>



<a name="loioacb8f74fc20d478a98de550a1e314b38__section_zh3_xn4_3qb"/>

## Example

```
neo copy-db-hana-certificates -a mysubaccount -h hana.ondemand.com -u mymail@example.com -i mydb --db-user mydbuser --db-password SECRET
```

**Related Information**  


[Enabling the In-Database Certificate Store and Moving Certificates](https://help.sap.com/viewer/d4790b2de2f4429db6f3dff54e4d7b3a/Cloud/en-US/d004ca23d1464a86867e209e269d6a55.html "Learn how to enable the in-memory certificate store for an SAP HANA tenant database and how to move any custom certificates (e.g. the ones used for SAML and X509) away from the file-based store to the in-database store.") :arrow_upper_right:

