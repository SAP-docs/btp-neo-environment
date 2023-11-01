<!-- loio8bd95529c8ae4ccf883095c5f43e38e1 -->

# delete-account

Deletes a particular subaccount. Only the user who has created the subaccount is allowed to delete it.



> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**



> ### Note:  
> You cannot delete a subaccount if it still has associated services, subscriptions, non-shared database systems, database schemas, deployed applications, HTML5 applications, or document service repositories. You need to disable services and delete the other subaccount entities before you proceed with the subaccount deletion. For information on how to disable services and delete subaccount entities, see Related Information. Make sure also that there are no running virtual machines in the subaccount.



```
neo delete-account --account <subaccount_technical_name> --user <e-mail_or_user> --host <host>
```



## Parameters

To list all parameters available for this command, execute `neo help delete-account` in the command line.


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

`-u`, `--user`

</td>
<td valign="top">

Use your email, SAP ID or user name

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
<tr>
<td valign="top">

`-h`, `--host`

</td>
<td valign="top">

Enter a region host.

`Type`: URL. For acceptable values, see [Regions](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/350356d1dc314d3199dca15bd2ab9b0e.html "You can deploy applications in different regions. Each region represents a geographical location (for example, Europe, US East) where applications, data, or services are hosted.") :arrow_upper_right:.

</td>
</tr>
</table>



## Example

```
neo delete-account --account mysubaccount --user myuser --host hana.ondemand.com
```

**Related Information**  


[Disable Services in the Neo Environment](../30-development-neo/using-services-in-the-neo-environment-a32d3d5.md#loiobb93d85070b14ac280f57fbee6044a73 "In the Neo environment, you might need to disable services so that they are not available to subaccount members.")

[Deleting Subscriptions](unsubscribe-862d00e.md "Removes the subscription to a provider Java application from a consumer subaccount.")

[Deleting Databases](https://help.sap.com/viewer/d4790b2de2f4429db6f3dff54e4d7b3a/Cloud/en-US/6cc1db5f30214321833fc8ca77e4ee8f.html "An overview of the different tasks you can perform to administer databases in the Neo environment.") :arrow_upper_right:

[Deleting Database Schemas](delete-schema-82a9911.md "This command deletes the specified schema, including all data it contains. A schema cannot be deleted if it is still bound to an application. To enforce the deletion, use the force parameter but bear in mind that this will also delete all bindings that still exist.")

[Undeploying Applications](undeploy-7e09b85.md "Undeploying an application removes it from SAP BTP. To undeploy an application, you have to stop it first.")

