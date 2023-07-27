<!-- loio67d5c6f1141a4c298886b150b2d8a232 -->

# list-subscribed-applications

Lists all Java applications to which a given subaccount is subscribed.



> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://launchpad.support.sap.com/#/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**



```
neo list-subscribed-applications --account <subaccount_technical_name> --user <e-mail_or_user> --host <host>
```



## Parameters

To list all parameters available for this command, execute `neo help list-subscribed applications` in the command line.


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

This is the subaccount of the applications consumer.

`Type`: string \(up to 30 characters; lowercase letters and numbers, starting with a letter\)



</td>
</tr>
<tr>
<td valign="top">

`-u`, `--user`



</td>
<td valign="top">

Use your email, SAP ID or user name

To be able to execute this command, the specified user must be a member of the subaccount.

`Type`: string



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
</table>



## Example

```
neo list-subscribed-applications --account consumersubaccount --user myuser --host hana.ondemand.com
```

**Related Information**  


[Subscribe to Java Multitenant Applications in the Neo Environment](../22-getting-started-neo/subscribe-to-java-multitenant-applications-in-the-neo-environment-e7e62c8.md "Create, list, and remove subscriptions for a Java application using the console client and view all our subscriptions in the cockpit.")

[Subscribe to HTML5 Multitenant Applications in the Neo Environment](../22-getting-started-neo/subscribe-to-html5-multitenant-applications-in-the-neo-environment-f16cd5b.md "Manage subscriptions to HTML5 applications by viewing, creating, or removing subscriptions in the cockpit.")

[subscribe](subscribe-4c6203d.md "Subscribes the subaccount of the consumer to a provider Java application. Once the command is executed successfully, the subscription is visible in the Subscriptions panel of the cockpit in the consumer subaccount.")

[unsubscribe](unsubscribe-862d00e.md "Removes the subscription to a provider Java application from a consumer subaccount.")

[list-subscribed-accounts](list-subscribed-accounts-034244c.md "Lists all subaccounts subscribed to a given Java application.")

