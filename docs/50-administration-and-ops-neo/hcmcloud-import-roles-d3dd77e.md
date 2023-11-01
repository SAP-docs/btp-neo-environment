<!-- loiod3dd77e6d8454bd2a9cbeb6c747c8135 -->

# hcmcloud-import-roles

This command imports SAP SuccessFactors HXM suite roles into the SAP SuccessFactors customer instance linked to an extension subaccount.



> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**



<a name="loiod3dd77e6d8454bd2a9cbeb6c747c8135__section_sxq_x4j_ndb"/>

## Prerequisites

To be able to use this command, you need the following platform scopes to be specified for your custom platform role:

-   readExtensionConfigurations

-   manageExtensionConfigurations


For more information, see [Platform Scopes](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/f2260746ed8e446fafdeaaa8ab43e307.html) and [Manage Custom Platform Roles in the Neo Environment](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/ede5f721e78e4d678c87c8a200c564ca.html).



```
neo hcmcloud-import-roles --account <subaccount_technical_name> --user <e-mail_or_user> --host <host> --location <path_to_the_file_with_role_definitions>
```



## Parameters



To list all parameters available for this command, execute `neo help hcmcloud-import-roles` in the command line.


<table>
<tr>
<th valign="top" colspan="2">

Required

</th>
</tr>
<tr>
<td valign="top">

`-l`, `--location`

</td>
<td valign="top">

Path to the file containing in which the SAP SuccessFactors HXM Suite roles are defined

`Type`: string

> ### Note:  
> The file size must not exceed 500 KB.



</td>
</tr>
<tr>
<td valign="top">

`-a`, `--account`

</td>
<td valign="top">

The extension subaccount in SAP BTP which is linked to the target SAP SuccessFactors system

`Type`: string \(up to 30 characters; lowercase letters and numbers, starting with a letter\)

</td>
</tr>
<tr>
<td valign="top">

`-h`, `--host`

</td>
<td valign="top">

Enter a region host

`Type`: URL. For acceptable values see [Regions and Hosts](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/350356d1dc314d3199dca15bd2ab9b0e.html).

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

Use your email, SAP ID or user name

`Type`: string

</td>
</tr>
</table>



## Example

To import the role definitions for an extension application from the system repository for your extension subaccount into the SAP SuccessFactors customer instance connected to this subaccount, execute:

```
neo hcmcloud-import-roles --account myextensionsubacc --user mymail@example.com --host hana.ondemand.com --location pathtorolefile
```

If any of the roles that you are importing already exists in the target system, the commands fails to execute.

**Related Information**  


[Create the Resource File with Role Definitions](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/93d5ce5346424596ac8dbe43b98a49ec.html)

