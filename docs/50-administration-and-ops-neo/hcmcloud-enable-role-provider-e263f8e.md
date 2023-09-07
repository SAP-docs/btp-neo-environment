<!-- loioe263f8ec85ad4c6e869c094b44c0084c -->

# hcmcloud-enable-role-provider

This command enables the SAP SuccessFactors role provider for the specified Java application.



> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**



<a name="loioe263f8ec85ad4c6e869c094b44c0084c__section_sxq_x4j_ndb"/>

## Prerequisites

To be able to use this command, you need the following platform scopes to be specified for your custom platform role:

-   readExtensionConfigurations

-   manageExtensionConfigurations

-   readDestinations


For more information, see [Platform Scopes](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/f2260746ed8e446fafdeaaa8ab43e307.html) and [Manage Custom Platform Roles in the Neo Environment](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/ede5f721e78e4d678c87c8a200c564ca.html).



```
neo  hcmcloud-enable-role-provider --application <extension_application> --account <subaccount_technical_name> --user <e_mail or user> --host <host>
```



## Parameters



To list all parameters available for this command, execute `neo help hcmcloud-enable-role-provider` in the command line.


<table>
<tr>
<th valign="top" colspan="2">

Required



</th>
</tr>
<tr>
<td valign="top">

`-b`, `--application`



</td>
<td valign="top">

The name of the extension application for which you are creating the connection. Cases:

-   Use <code>--application <i class="varname">&lt;my_extension_application&gt;</i></code> if the application is running in your subaccount

-   Use <code>--application <i class="varname">&lt;provider_subaccount&gt;</i>:<i class="varname">&lt;extension_application&gt;</i></code> if the application is running in another subaccount and your extension subaccount is subscribed to the application


`Type`: string \(up to 30 characters; lowercase letters and numbers, starting with a letter\)



</td>
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

Enter a region host

`Type`: URL. For acceptable values, see [Regions and Hosts](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/350356d1dc314d3199dca15bd2ab9b0e.html).



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


<table>
<tr>
<th valign="top" colspan="2">

Optional



</th>
</tr>
<tr>
<td valign="top">

`--connection-name`



</td>
<td valign="top">

The name of the destination for connecting to the SAP SuccessFactors system OData API.

`Default`: *<sap\_hcmcloud\_core\_odata\>*

`Condition`: If you do not specify a value for the `--connection-name` parameter, the default value will be used.

`Type`: string \(up to 200 characters; uppercase and lowercase letters, numbers, and the special characters en dash \(**\-**\) and underscore \(**\_**\).



</td>
</tr>
</table>



## Example

To enable the SAP SuccessFactors role provider for your Java application in an extension subaccount located in the United States \(US East\) region, execute:

```
neo hcmcloud-enable-role-provider --application <my_application> --account <my_extension_subaccount> --user <my_email@example.com> --host us1.hana.ondemand.com
```

