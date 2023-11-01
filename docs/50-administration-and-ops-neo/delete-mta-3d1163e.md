<!-- loio3d1163e7d5124b17af2b839feb2a1701 -->

# delete-mta

This command deletes Multitarget Application \(MTA\) archives that are deployed to your subaccount.



> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**



```
neo delete-mta --host <host> --account <subaccount_technical_name> --user <e-mail_or_user> --id <MTA_ID>
```



<a name="loio3d1163e7d5124b17af2b839feb2a1701__section_N10015_N10012_N10001"/>

## Parameters



To list all parameters available for this command, execute `neo help delete-mta` in the command line.


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

`-i`, `--id`

</td>
<td valign="top">

A comma-separated list of MTA IDs

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

`-y`, `--synchronous`

</td>
<td valign="top">

Instructs the console to wait for the operation to finish. It takes no value.

</td>
</tr>
</table>



<a name="loio3d1163e7d5124b17af2b839feb2a1701__section_N1014A_N10012_N10001"/>

## Example

To delete MTA archives with IDs <MTA\_ID1\> and <MTA\_ID2\> that have been deployed to your subaccount, execute:

```
neo delete-mta --host hana.ondemand.com --account mysubaccount --user mymail@example.com --id <ID1>,<ID2>
```

