<!-- loiob8b51efeb4ef44939c828a435549c357 -->

# list-mtas

This command lists the Multitarget Application \(MTA\) archives that are deployed to your subaccount or provided by another subaccount.



> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of the following technology portfolios: application development; process automation; integration; data, analytics, and enterprise planning; artificial intelligence. The platform offers users the ability to turn data into business value, compose end-to-end business processes, connect entire IT landscapes, and personalize, build and extend SAP applications. This reduces the overall total cost of ownership maintaining SAP landscapes and third-party software across end-to-end business processes.") :arrow_upper_right:.**



```
neo list-mtas --host <host> --account <subaccount_technical_name> --user <e-mail_or_user>
```



<a name="loiob8b51efeb4ef44939c828a435549c357__section_N10015_N10012_N10001"/>

## Parameters



To list all parameters available for this command, execute `neo help list-mtas` in the command line.


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
</table>


<table>
<tr>
<th valign="top" colspan="2">

Optional

</th>
</tr>
<tr>
<td valign="top" colspan="2">

**Command-specific parameters**

</td>
</tr>
<tr>
<td valign="top">

`--available-for-subscription` 

</td>
<td valign="top">

If you use this parameter, the command will list only the MTAs that are available for subscription to the corresponding subaccount. The MTAs, which are deployed by the subaccount, will not be listed.

</td>
</tr>
</table>



<a name="loiob8b51efeb4ef44939c828a435549c357__section_N1014A_N10012_N10001"/>

## Example

To check the deployed MTA archives to a given subaccount, execute:

```
neo list-mtas –host hana.ondemand.com --account mysubaccount --user mymail@example.com 
```

To check the MTAs that are available for subscription to a given subaccount, execute:

```
neo list-mtas –host hana.ondemand.com --account mysubaccount --user mymail@example.com --available-for-subscription
```

