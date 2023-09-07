<!-- loioacb8f74fc20d478a98de550a1e314b38 -->

# copy-db-hana-certificates

This command copies certificates from the file-based certificate store 'sapsrv.pse' to the SAML and X509 certificate collections of the in-database certificate store of an SAP HANA tenant database.



> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**



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

Password of the SAP HANA tenant database user \(optional, queried at the command prompt if omitted\)



</td>
</tr>
</table>



<a name="loioacb8f74fc20d478a98de550a1e314b38__section_zh3_xn4_3qb"/>

## Example

```
neo copy-db-hana-certificates -a mysubaccount -h hana.ondemand.com -u mymail@example.com -i mydb --db-user mydbuser --db-password SECRET
```

**Related Information**  


[Copying Certificates to In-Database Certificate Store](https://help.sap.com/viewer/d4790b2de2f4429db6f3dff54e4d7b3a/Cloud/en-US/d004ca23d1464a86867e209e269d6a55.html "Copy your trust and own certificates from the file-based certificate store &apos;sapsrv.pse&apos; to the SAML and X509 certificate collections of the in-database certificate store of an SAP HANA tenant database.") :arrow_upper_right:

