<!-- loioba4e8bbf0ec4409fae7064bcbbe07e49 -->

# hcmcloud-create-connection

Use this command to configure the connectivity of an extension application to an SAP SuccessFactors system associated with a specified subaccount in the Neo environment, or to configure the connectivity of a specified subaccount in the Neo environment to an SAP SuccessFactors system associated with this subaccount. The command creates the required HTTP destination and registers an OAuth client for the extension application in SAP SuccessFactors.



> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**



## Prerequisites

To be able to use this command, you need the following platform scopes to be specified for your custom platform role:

-   readExtensionConfigurations

-   manageExtensionConfigurations

-   manageDestinations


For more information, see [Platform Scopes](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/f2260746ed8e446fafdeaaa8ab43e307.html) and [Manage Custom Platform Roles in the Neo Environment](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/ede5f721e78e4d678c87c8a200c564ca.html).



```
neo  hcmcloud-create-connection --application <Java_extension_application> --account <subaccount_technical_name> --user <e_mail or user> --host <host>
```



## Parameters



To list all parameters available for this command, execute ***neo help hcmcloud-create-connection*** in the command line.


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

Use your email, SAP ID or user name.

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

`-w`, `--overwrite`



</td>
<td valign="top">

If a connection with the same name already exists, overwrites it. If you do not explicitly specify the --overwrite parameter, and a connection with the same name already exists, the command fails to execute



</td>
</tr>
<tr>
<td valign="top">

\(Deprecated\) `--technical-user-id`



</td>
<td valign="top">

ID of the technical user for the connection.

`Condition`: Required for connection type OData with technical user

`Type`: string

> ### Caution:  
> This property is deprecated and will be removed soon. We recommend that you work on behalf of specific \(named\) users instead of working with a technical user.
> 
> See [OAuth SAML Bearer Assertion Authentication](https://help.sap.com/viewer/cca91383641e40ffbe03bdc78f00f681/Cloud/en-US/c69ea6aacd714ad2ae8ceb5fc3ceea56.html "Create and configure an OAuth SAML Bearer Assertion destination for an application in the Cloud Foundry environment.") :arrow_upper_right:.



</td>
</tr>
<tr>
<td valign="top">

`-b`, `--application`



</td>
<td valign="top">

The name of the extension application for which you are creating the connection. Cases:

-   Use <code>--application <i class="varname">&lt;my_extension_application&gt;</i></code> if the application is running in your subaccount

-   Use <code>--application <i class="varname">&lt;provider_subaccount&gt;</i>:<i class="varname">&lt;extension_application application&gt;</i></code> if the application is running in another subaccount and your extension subaccount is subscribed to the application.


`Type`: string \(up to 30 characters; lowercase letters and numbers, starting with a letter\)

> ### Note:  
> This parameter is only relevant for Java applications.



</td>
</tr>
<tr>
<td valign="top">

`-n`, `--name`



</td>
<td valign="top">

Name of the connection.

`Default`:

-   For a connection of OData type: *<sap\_hcmcloud\_core\_odata\>*

-   For a connection of OData with a technical user type: *<sap\_hcmcloud\_core\_odata\_technical\_user\>*


`Condition`: If you have not specified the name parameter, the default value *<sap\_hcmcloud\_core\_odata\>* will be assumed for connections without a technical user, the default value *<sap\_hcmcloud\_core\_odata\_technical\_user\>* will be assumed for connections with technical user.

> ### Note:  
> If the connection is on a subaccount level, the name is required and must be different than *<sap\_hcmcloud\_core\_odata\>* and *<sap\_hcmcloud\_core\_odata\_technical\_user\>*.

`Type`: string \(up to 200 characters; uppercase and lowercase letters, numbers, and the special characters en dash \(**\-**\) and underscore \(**\_**\).



</td>
</tr>
</table>



## Example

To configure a connection of type OData with technical user and with a specific name for a Java extension application in a subaccount located in the United States \(US East\) region, execute:

```
neo hcmcloud-create-connection --application <my_Java_application> --account <my_extension_subaccount> --user <my_email@example.com> --host us1.hana.ondemand.com --technical-user-id <technical_user_id> --name <my_connection_name>
```



<a name="loioba4e8bbf0ec4409fae7064bcbbe07e49__section_ymd_t5z_gbb"/>

## Result

After executing this command without specifying a name for the connection, you have one of the following destinations in your subaccount:

-   sap\_hcmcloud\_core\_odata

-   sap\_hcmcloud\_core\_odata\_technical\_user


After executing the command with a specific name for the connection, the required destination is created in your subaccount.

You can consume this destination in your application using one of these APIs:

-   [HttpDestination API and DestinationFactory](https://help.sap.com/viewer/cca91383641e40ffbe03bdc78f00f681/Cloud/en-US/462dbffef4614044b5c727c9de37672e.html)

-   [ConnectivityConfiguration API](https://help.sap.com/viewer/cca91383641e40ffbe03bdc78f00f681/Cloud/en-US/4da3b13c88ce4220bbd56a4361799668.html)

-   [AuthenticationHeaderProvider API](https://help.sap.com/viewer/cca91383641e40ffbe03bdc78f00f681/Cloud/en-US/df6c1ffd39f0451594d737cf7638ce00.html)


