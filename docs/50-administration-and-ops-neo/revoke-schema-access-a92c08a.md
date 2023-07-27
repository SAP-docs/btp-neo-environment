<!-- loioa92c08adc7b54370a309c140fa174d54 -->

# revoke-schema-access

This command revokes the schema access granted to an application in another account.



> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://launchpad.support.sap.com/#/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**



```
neo revoke-schema-access --host <SAP HANA Cloud host> --account <subaccount technical name> --user <e-mail or user name> --access-token <access token> 

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

`--access-token`



</td>
<td valign="top">

Access token that identifies the grant. Grants can only be revoked by the granting subaccount.



</td>
</tr>
</table>



## Example

```
neo revoke-schema-access --host hanatrial.ondemand.com --account mysubaccount --user mymail@example.com --access-token vm6431dhjcr2e3dbt0fk6jpzm2w7oo3q48yumf1c6uu8b9pt9z
```

**Related Information**  


[grant-schema-access](grant-schema-access-830e9ec.md "This command gives an application in another subaccount access to a schema based on a one-time access token. The access token is used to bind the schema to the application.")

[list-schema-access-grants](list-schema-access-grants-371711d.md "This command lists all current schema access grants for a specified subaccount.")

[Managing Access to Databases for Other Subaccounts](https://help.sap.com/viewer/3fa880aa54b74110ae99ad01503fcd60/Cloud/en-US/65d582dc5f0f4c5092acc2bedc9f636d.html "As a subaccount member with the administrator role, you can manage access to databases for other subaccounts in the Neo environment.") :arrow_upper_right:

[Sharing Databases with Other Subaccounts](https://help.sap.com/viewer/3fa880aa54b74110ae99ad01503fcd60/Cloud/en-US/322080db84734e9b8812ede13703b83c.html "You can share a SAP ASE database that is owned by a subaccount with other subaccounts in the Neo environment.") :arrow_upper_right:

[Grant Access to Schemas](https://help.sap.com/viewer/d4790b2de2f4429db6f3dff54e4d7b3a/Cloud/en-US/a3142222d2cb40b0b473f53855f571b0.html "As a subaccount member who is assigned the Administrator or Developer role, you can grant applications in other subaccounts access to any of your subaccount’s schemas in the Neo environment.") :arrow_upper_right:

