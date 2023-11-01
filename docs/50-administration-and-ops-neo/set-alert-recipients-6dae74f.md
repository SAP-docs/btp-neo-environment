<!-- loio6dae74f3792446b7be65f5d8187c2425 -->

# set-alert-recipients

Sets alert recipients.



> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**



<a name="loio6dae74f3792446b7be65f5d8187c2425__section_an3_mgj_flb"/>

## Prerequisites

-   You have set up the console client.

    For more information, see [Set Up the Console Client](../30-development-neo/set-up-the-console-client-7613dee.md).

-   The *manageMonitoringConfiguration* scope is assigned to the used platform role for the subaccount. For more information, see [Platform Scopes](platform-scopes-f226074.md).




<a name="loio6dae74f3792446b7be65f5d8187c2425__section_vmx_mlm_blb"/>

## Overview

-   Setting alert recipients becomes effective after five minutes.

-   Setting additional recipients works only with the overwrite parameter \(`-w` or `--overwrite`\). In such a case, you have to overwrite the existing list of recipients with a new one.

-   Setting alert recipients for a Java, HTML5, or SAP HANA XS application triggers sending all alerts for this application.

    Moreover, when the alert is for a Java application, the alert email for JMX checks and default metrics also includes the process ID. The alerts for availability checks and other application types don’t include the process ID.

-   Setting alert recipients on subaccount level triggers sending all alerts for all applications and database systems in this subaccount. In this case, alerts are sent for any type of a database system.




<a name="loio6dae74f3792446b7be65f5d8187c2425__section_bv1_5yg_bmb"/>

## Email Confirmation Requirement

To comply with security requirements, we ask that email recipients confirm their email address before they can receive alert notifications. If users don’t confirm their email address within 2 days, their email address will be removed from the list of alert recipients and they will not receive alert notifications. Users receive emails for confirmation when you set their email addresses as alert recipients. If you set additional recipients with the overwrite parameter, only the new recipients will receive a confirmation email. However, clearing alert recipients and then setting them again triggers emails for confirmation to the recipients again.



```
neo set-alert-recipients -a <subaccount_technical_name> -u <e-mail_or_user> -e <recipient_emails> -h <host>
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

`Type`: string \(up to 30 characters; lowercase letters and numbers, starting with a letter\)

When you configure alerting on subaccount level by omitting the `-b` or `--application` parameter, alerts are sent for all applications and database systems in the subaccount.

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

`-e`, `--email`

</td>
<td valign="top">

Comma-separated list of recipient e-mails

We recommend that you use distribution lists rather than personal email addresses. Keep in mind that you’re responsible for handling of personal email addresses with respect to data privacy regulations applicable.

`Type`: string

</td>
</tr>
<tr>
<td valign="top">

`-h`, `--host`

</td>
<td valign="top">

Enter a region host.

`Type`: URL, for acceptable values see [Regions](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/350356d1dc314d3199dca15bd2ab9b0e.html "You can deploy applications in different regions. Each region represents a geographical location (for example, Europe, US East) where applications, data, or services are hosted.") :arrow_upper_right:.

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

`-w`, `--overwrite`

</td>
<td valign="top">

Overwrites existing recipients

`Default`: false

`Type`: boolean

</td>
</tr>
</table>

> ### Caution:  
> If you stop your application, you won’t receive a notification alert for it because the alerting is suppressed with the manual stop of an application. Alerting is automatically enabled once again when you start the application.



<a name="loio6dae74f3792446b7be65f5d8187c2425__section_x3k_w2z_5fb"/>

## Example

```
neo set-alert-recipients -a mysubaccount -b demo -u p1234567 -e alert_recipients@example.com --host hana.ondemand.com
```

**Related Information**  


[Monitoring Java Applications](https://help.sap.com/viewer/64f7d2b06c6b40a9b3097860c5930641/Cloud/en-US/cf4b2953c2534c0a9b491abf5a4847d7.html "") :arrow_upper_right:

[Monitoring Database Systems](https://help.sap.com/viewer/64f7d2b06c6b40a9b3097860c5930641/Cloud/en-US/d5c5c6a37c944ce78fcccf2b84243d8a.html "You can monitor your database system by viewing its metrics in the SAP BTP cockpit, by retrieving them with the Metrics REST API, or by receiving alerts for them. Furthermore, when you use an SAP HANA database system, you can also configure monitoring for its SAP HANA XS applications.") :arrow_upper_right:

[list-alert-recipients](list-alert-recipients-f326f9d.md "Lists alert recipients.")

[clear-alert-recipients](clear-alert-recipients-0f2b2cd.md "Clears alert recipients.")

