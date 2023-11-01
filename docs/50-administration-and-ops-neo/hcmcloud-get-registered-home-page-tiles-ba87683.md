<!-- loioba8768339dad4260b0641e4f36d26394 -->

# hcmcloud-get-registered-home-page-tiles

This command lists the SAP SuccessFactors Employee Central \(EC\) home page tiles registered in the SAP SuccessFactorss company instance associated with the extension subaccount.



> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**



<a name="loioba8768339dad4260b0641e4f36d26394__section_vgh_nnj_ndb"/>

## Prerequisites

To be able to use this command, you need the following platform scopes to be specified for your custom platform role:

-   readExtensionConfigurations

-   readHTML5Applications


For more information, see [Platform Scopes](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/f2260746ed8e446fafdeaaa8ab43e307.html) and [Manage Custom Platform Roles in the Neo Environment](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/ede5f721e78e4d678c87c8a200c564ca.html).



```
neo hcmcloud-get-registered-home-page-tiles --application <extension_application> --account <subaccount_technical_name> --user <e-mail_or_user> --host <host> --application-type <extension_application_type>
```



## Parameters



To list all parameters available for this command, execute `neo help hcmcloud-get-registered-home-page-tiles` in the command line.


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

The name of the extension application for which you are listing the home page tiles. Cases:

-   Use <code>--application <i class="varname">&lt;my_extension_application&gt;</i></code> if the application is running in your subaccount

-   Use <code>--application <i class="varname">&lt;provider_subaccount&gt;</i>:<i class="varname">&lt;extension_application&gt;</i></code> if the application is running in another subaccount and your extension subaccount is subscribed to the application


`Type`: string \(up to 30 characters; lowercase letters and numbers, starting with a letter\)

> ### Note:  
> If you do not specify the `application` parameter, the command lists all tiles registered in the Successfactors company instance associated with the specified extension subaccount.



</td>
</tr>
<tr>
<td valign="top">

`-a`, `--account`

</td>
<td valign="top">

Name of the extension subaccount

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


<table>
<tr>
<th valign="top" colspan="2">

Optional

</th>
</tr>
<tr>
<td valign="top">

`--application-type`

</td>
<td valign="top">

The type of the extension application for which you are listing the home page tiles

`Accepted values`: `java`, `html5`

`Type`: string \(up to 30 characters; lowercase letters and numbers, starting with a letter\)

</td>
</tr>
</table>



## Example

To list the home page tiles registered for a Java extension application running in your subaccount in the US East region, execute:

```
neo  hcmcloud-get-registered-home-page-tiles --application <my_application> --account <my_extension_subaccount>  --user <my_email@example.com> --host us1.hana.ondemand.com --application-type <java>
```

There is no lifecycle dependency between the tiles and the application, so the application may not be started or may not be deployed anymore.

