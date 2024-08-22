<!-- loio0f2b2cda9d844939bad3cbda32c167d8 -->

# clear-alert-recipients

Clears alert recipients.



> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of the following technology portfolios: application development; process automation; integration; data, analytics, and enterprise planning; artificial intelligence. The platform offers users the ability to turn data into business value, compose end-to-end business processes, connect entire IT landscapes, and personalize, build and extend SAP applications. This reduces the overall total cost of ownership maintaining SAP landscapes and third-party software across end-to-end business processes.") :arrow_upper_right:.**



<a name="loio0f2b2cda9d844939bad3cbda32c167d8__section_an3_mgj_flb"/>

## Prerequisites

-   You have set up the console client.

    For more information, see [Set Up the Console Client](../30-development-neo/set-up-the-console-client-7613dee.md).

-   The *manageMonitoringConfiguration* scope is assigned to the used platform role for the subaccount. For more information, see [Platform Scopes](platform-scopes-f226074.md).




<a name="loio0f2b2cda9d844939bad3cbda32c167d8__section_lbk_nmm_blb"/>

## Overview

-   Clearing alert recipients becomes effective after five minutes.

-   If no emails are specified, it clears all recipients.

-   Clearing alert recipients and setting them again triggers emails for confirmation to the recipients one more time.




```
neo clear-alert-recipients -a <subaccount_technical_name> -u <e-mail_or_user> -h <host>
```



## Parameter


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

Use your email, SAP ID, or user name

`Type`: string

</td>
</tr>
<tr>
<td valign="top">

`-h`, `--host`

</td>
<td valign="top">

Enter a region host.

`Type`: URL. For acceptable values, see [Regions and Hosts Available for the Neo Environment](../10-concepts-neo/regions-and-hosts-available-for-the-neo-environment-d722f7c.md)

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

`-b`, `--application` 

</td>
<td valign="top">

Application name for Java or HTML5 applications, or productive SAP HANA instance database name and application name in the format *<instance name\>*:*<application name\>* for SAP HANA XS applications

`Type`: string \(up to 30 characters; lowercase letters and numbers, starting with a letter\)

</td>
</tr>
<tr>
<td valign="top">

`-e`, `--email`

</td>
<td valign="top">

Comma-separated list of recipient e-mails

`Type`: string

</td>
</tr>
</table>



<a name="loio0f2b2cda9d844939bad3cbda32c167d8__section_xgb_14t_5fb"/>

## Example

```
neo clear-alert-recipients -a mysubaccount -b demo -u p1234567 --host hana.ondemand.com
```

**Related Information**  


[Monitoring Java Applications](https://help.sap.com/viewer/64f7d2b06c6b40a9b3097860c5930641/Cloud/en-US/cf4b2953c2534c0a9b491abf5a4847d7.html "") :arrow_upper_right:

[Monitoring Database Systems](https://help.sap.com/viewer/64f7d2b06c6b40a9b3097860c5930641/Cloud/en-US/d5c5c6a37c944ce78fcccf2b84243d8a.html "You can monitor your database system by viewing its metrics in the SAP BTP cockpit, by retrieving them with the Metrics REST API, or by receiving alerts for them. Furthermore, when you use an SAP HANA database system, you can also configure monitoring for its SAP HANA XS applications.") :arrow_upper_right:

[list-alert-recipients](list-alert-recipients-f326f9d.md "Lists alert recipients.")

[set-alert-recipients](set-alert-recipients-6dae74f.md "Sets alert recipients.")

