<!-- loioacf1b72fd1b646ef90f23983690d52df -->

# create-ecm-repository

Creates a new repository in the specified subaccount.



> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**



```
neo create-ecm-repository --account <subaccount_technical_name>  --host <host> --user <e-mail_or_user> --name <repository_name> --key <repository_key> --display <display_name_of_repository> --description <description_of_repository> --virus-scan <true/false> 
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

Specify an existing subaccount of which you are already a member.

`Type`: string \(up to 30 characters; lowercase letters and numbers, starting with a letter\)



</td>
</tr>
<tr>
<td valign="top">

`-h`, `--host`



</td>
<td valign="top">

Enter a region host.

`Type`: URL. For acceptable values see [Regions](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/350356d1dc314d3199dca15bd2ab9b0e.html "You can deploy applications in different regions. Each region represents a geographical location (for example, Europe, US East) where applications, data, or services are hosted.") :arrow_upper_right:



</td>
</tr>
<tr>
<td valign="top">

`-u`, `--user`



</td>
<td valign="top">

Use your email, SAP ID, or user name.

`Type`: string



</td>
</tr>
<tr>
<td valign="top">

`-n`, `--name`



</td>
<td valign="top">

Name of the repository

`Type`: string



</td>
</tr>
<tr>
<td valign="top">

`-k`, `--key`



</td>
<td valign="top">

Key of the repository

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

`-d`, `--display-name`



</td>
<td valign="top">

Can be used to provide a more readable name of the repository. Equals the --name value if left blank. You cannot change the display later on.

`Type`: string \(up to 30 characters; lowercase letters and numbers, starting with a letter\)



</td>
</tr>
<tr>
<td valign="top">

`-e`, `--description`



</td>
<td valign="top">

Description of the repository. You cannot change the description later on.

`Type`: string



</td>
</tr>
<tr>
<td valign="top">

`-v`, `--virus-scan`



</td>
<td valign="top">

Can be used to activate the virus scanner and check all incoming documents for viruses.

`Default`: `true`

`Type`: boolean

> ### Recommendation:  
> For repositories that are used by untrusted users and or for unknown content, we recommend that you enable the virus scanner by setting this parameter to `true`. Enabling the virus scanner could impair the upload performance.

If a virus is detected, the upload process for the document fails with a virus scanner exception.



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
</table>



## Example

```
neo create-ecm-repository --account sap --host hana.ondemand.com --user <myemail@example.com> --name DemoRepository --key ecm_012345689  --display-name DemoRep --description "Demo Repository" --virus-scan true

SAP BTP Console Client

Repository DemoRepository created successfully.

```

