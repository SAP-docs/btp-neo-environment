<!-- loio05f96cf62cec4e58b78514655b070a8e -->

# create-account

Creates a new subaccount with an automatically generated unique ID as subaccount technical name and the specified display name and assigns the user as a subaccount owner. The user is authorized against the existing subaccount passed as --account parameter. Optionally, you can clone an existing subaccount configuration to save time and effort.



> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**



```
neo create-account --display-name <subaccount_display_name> --account <subaccount_technical_name> --user <e-mail_or_user> --host <host> --clone <cloning_options>
```

> ### Note:  
> If you clone an existing extension subaccount, the new subaccount will **not** be an extension subaccount but a regular one. The new subaccount will **not** have the trust and destination settings typical for extension subaccounts.



## Parameters

To list all parameters available for this command, execute ***neo help create-account*** in the command line.


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

`-n`, `--display-name`



</td>
<td valign="top">

Subaccount display name

If you want to create a subaccount whose display name has intervals, use quotes when executing the command. For example: neo ... --display-name "Display Name with Intervals"

`Type`: string \(up to 255 characters\)



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

`Type`: URL. For acceptable values see [Regions and Hosts Available for the Neo Environment](../10-concepts-neo/regions-and-hosts-available-for-the-neo-environment-d722f7c.md)



</td>
</tr>
<tr>
<td valign="top">

\--clone



</td>
<td valign="top">

\(Optional\) List of settings that will be copied \(re-created\) from the existing subaccount into the new subaccount. A comma separated list of values, which are as follows:

-   `trust`
-   `members`
-   `destinations`
-   `all`

Each value combination is acceptable, for example, `trust,members` or `all`. If specified, all the configurations of the passed type\(s\) will be cloned to the newly created subaccount.

> ### Tip:  
> We recommend listing explicitly the required cloning options instead of using `--clone all` in automated scripts. This will ensure backward compatibility in case the available cloning options, enveloped by `all`, change in future releases.



</td>
</tr>
</table>



## Example

```
neo create-account --account mysubaccount --display-name mynewsubaccount --user myuser --host hana.ondemand.com
```



## Cloning Existing Subaccounts

You may choose among the following cloning options:


<table>
<tr>
<th valign="top">

Cloning Option



</th>
<th valign="top">

Description



</th>
</tr>
<tr>
<td valign="top">

 `all` 



</td>
<td valign="top">

All settings \(trust, members and destinations\) from the existing subaccount will be copied into the new one.

> ### Caution:  
> The list of cloned configurations might be extended in the future.



</td>
</tr>
<tr>
<td valign="top">

 `trust` 



</td>
<td valign="top">

The following trust settings will be re-created in the new subaccount similarly to the relevant settings in the existing subaccount:

-   Trusted Identity Authentication tenants - the new subaccount will have trust to the Identity Authentication tenants registered in the existing subaccount. The respective Identity Authentication tenants, in turn, will automatically register a new service provider corresponding to the new SAP BTP subaccount.

    > ### Note:  
    > SAP BTP will generate a new pair of key and certificate on behalf of the new subaccount. Remember to replace them with your proprietary key and certificate when using the subaccount for productive purposes.


All other trust settings \(for example, trusted on-premise identity providers\) from the existing subaccount will **not** be copied into the new subaccount.

> ### Note:  
> If you do not have any trusted Identity Authentication tenants in the existing subaccount, cloning the trust settings will result in trust with SAP ID Service \(as default identity provider\) in the new subaccount.



</td>
</tr>
<tr>
<td valign="top">

 `members` 



</td>
<td valign="top">

All members with their roles from the existing subaccount will be copied into the new one.



</td>
</tr>
<tr>
<td valign="top">

 `destinations` 



</td>
<td valign="top">

All destinations from the existing subaccount will be created into the new one. In addition, the relevant certificates and passwords for the destinations will also be cloned so the destination configurations will be fully functional in the new subaccount.



</td>
</tr>
</table>

Example of cloning an existing subaccount to create a new subaccount with the same trust settings and existing destinations:

```
neo create-account --account mysubaccount --display-name mynewsubaccount --user myuser --host hana.ondemand.com --clone trust,destinations
```

