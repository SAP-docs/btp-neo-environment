<!-- loiofb098118e1f14622852aabcb8d0f1915 -->

# delete-ecm-repository

This command deletes a repository including the data of any tenants in the repository, unless you restrict the command to a specific tenant.



> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**



> ### Caution:  
> Be very careful when using this command. Deleting a repository permanently deletes all data. This data cannot be recovered.



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

`-t`, `--tenant`



</td>
<td valign="top">

Tenant alias

Deletes the repository for the given tenant only instead of for all tenants. If no tenant name is provided, the repositories for all tenants are deleted.

`Type`: string



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

neo delete-ecm-repository --account sap --host hana.ondemand.com --user <myemail@example.com> --name DemoRepository --key ecm_012345689

SAP BTP Console Client


Are you sure you want to permanently delete all data? This operation cannot be reverted. (yes/no) 
yes

Delete command executed successfully.

```

