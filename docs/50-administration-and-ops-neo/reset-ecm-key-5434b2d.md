<!-- loio5434b2d2eaa34d0e8e0addc52f39343d -->

# reset-ecm-key

If you have forgotten the repository key, use this command to request a new repository key.



> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of the following technology portfolios: application development; process automation; integration; data, analytics, and enterprise planning; artificial intelligence. The platform offers users the ability to turn data into business value, compose end-to-end business processes, connect entire IT landscapes, and personalize, build and extend SAP applications. This reduces the overall total cost of ownership maintaining SAP landscapes and third-party software across end-to-end business processes.") :arrow_upper_right:.**



This command only creates a new key that replaces the old one. You cannot use the old key any longer. The command does not affect any other repository setting, for example, the virus scan definition. If you just want to change your current repository key, use the `edit-ecm-repository` command.

```
neo reset-ecm-key --name <repository_name> --account <subaccount_technical_name> --host <host> --user <e-mail_or_user>
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
</table>



## Example

```
neo reset-ecm-key --name com.foo.MyRepository --account sap --host hana.ondemand.com --user p1940248318
```

This example resets the repository key for the `com.foo.MyRepository` repository and creates a new repository key, for example `fp0TebRs14rwyqq`.

**Related Information**  


[edit-ecm-repository](edit-ecm-repository-279edd1.md "Changes the name, key, or virus scan settings of a repository. You cannot change the display name or the description.")

