<!-- loio8029e1a15ad948d2a2387266fb31c9ba -->

# list-mta-operations

This command shows the MTA operation status with a given ID.



> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**



```
neo list-mta-operations --host <host> --account <subaccount_technical_name> --operation-id < operation-id > --user <e-mail_or_user>			
```



<a name="loio8029e1a15ad948d2a2387266fb31c9ba__section_N10015_N10012_N10001"/>

## Parameters



To list all parameters available for this command, execute `neo help list-mta-operations` in the command line.


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

The name of the subaccount for which you provide a user and a password.

</td>
</tr>
<tr>
<td valign="top">

`-h`, `--host`

</td>
<td valign="top">

The host on which you execute the command.

</td>
</tr>
<tr>
<td valign="top">

`-p`, `--password`

</td>
<td valign="top">

Your user password. We recommend that you enter it only when prompted, and not explicitly as a parameter in a properties file or the command line.

</td>
</tr>
<tr>
<td valign="top">

`-u`, `--user`

</td>
<td valign="top">

Your user e-mail or SAP ID \(SCN\) user name.

</td>
</tr>
<tr>
<td valign="top">

`--operation-id`

</td>
<td valign="top">

The ID of the operation.

> ### Note:  
> This parameter is optional. If you do not use this parameter, all operations that have not been cleaned up within the last 24 hours will be listed.



</td>
</tr>
</table>



<a name="loio8029e1a15ad948d2a2387266fb31c9ba__section_N1014A_N10012_N10001"/>

## Example

To check the deployment status of an MTA with ID "i2", execute:

```
neo list-mta-operations –host hana.ondemand.com --account mysubaccount –-operation-id i2 --user mymail@example.com 
```

**Related Information**  


[deploy-mta](deploy-mta-1e12331.md "This command deploys Multitarget Application (MTA) archives. One or more than one MTA archives can be deployed to your subaccount in one go.")

 <?sap-ot O2O class="- topic/link " href="c4f0d850b6ba46089a76d53ab805c9e6.xml" text="" desc="" xtrc="link:2" xtrf="file:/home/builder/src/dita-all/jjq1673438782153/loio9fe952ba277c471bbad80cd40548bb84_en-US/src/content/localization/en-us/8029e1a15ad948d2a2387266fb31c9ba.xml" ?> 

