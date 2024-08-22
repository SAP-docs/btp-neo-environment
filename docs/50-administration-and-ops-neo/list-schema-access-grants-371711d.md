<!-- loio371711d0c46347429a6aa69147e892fc -->

# list-schema-access-grants

This command lists all current schema access grants for a specified subaccount.



> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of the following technology portfolios: application development; process automation; integration; data, analytics, and enterprise planning; artificial intelligence. The platform offers users the ability to turn data into business value, compose end-to-end business processes, connect entire IT landscapes, and personalize, build and extend SAP applications. This reduces the overall total cost of ownership maintaining SAP landscapes and third-party software across end-to-end business processes.") :arrow_upper_right:.**



```
neo list-schema-access-grants --host <host> --account <subaccount_technical_name> --user <e-mail_or_user> 

```

Note that the list does not include grants that have been revoked.



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
</table>


<table>
<tr>
<th valign="top" colspan="2">

Optional

</th>
</tr>
<tr>
<td valign="top">

`-i`, `--id`

</td>
<td valign="top">

Schema ID

Lists only the grants for the specified schema

`Type`: string

</td>
</tr>
</table>



## Example

```
neo list-schema-access-grants --host hanatrial.ondemand.com --account mysubaccount --user mymail@example.com --id myschema
```

**Related Information**  


[Grant Access to Schemas](https://help.sap.com/viewer/d4790b2de2f4429db6f3dff54e4d7b3a/Cloud/en-US/a3142222d2cb40b0b473f53855f571b0.html "As a subaccount member who is assigned the Administrator or Developer role, you can grant applications in other subaccounts access to any of your subaccount’s schemas in the Neo environment.") :arrow_upper_right:

[grant-schema-access](grant-schema-access-830e9ec.md "This command gives an application in another subaccount access to a schema based on a one-time access token. The access token is used to bind the schema to the application.")

[revoke-schema-access](revoke-schema-access-a92c08a.md "This command revokes the schema access granted to an application in another account.")

