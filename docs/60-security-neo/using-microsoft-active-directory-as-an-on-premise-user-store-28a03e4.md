<!-- loio28a03e44bb2f49278e0fecc246726d5c -->

# Using Microsoft Active Directory as an On-Premise User Store

You can use Microsoft Active Directory as an on-premise LDAP server providing a user store for your SAP BTP applications.



## Prerequisites

-   You have installed the SDK.
-   You have set up the SDK location and landscape host.
-   You have set up the console client.

    For more information, see [Install the SAP BTP SDK for Neo Environment](../30-development-neo/install-the-sap-btp-sdk-for-neo-environment-7613843.md).

-   You have installed and deployed SAP HANA cloud connector. See [Installation](https://help.sap.com/viewer/b865ed651e414196b39f8922db2122c7/Cloud/en-US/57ae3d62f63440f7952e57bfcef948d3.html "Choose a procedure to install the Cloud Connector on your operating system.") :arrow_upper_right:.



## Context

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**

 <a name="task_n31_ndv_ds"/>

<!-- task\_n31\_ndv\_ds -->

## 1. Deploy the Application

When deploying the application, you have to set system properties of the application VM. For more information, see [Configure VM Arguments](../50-administration-and-ops-neo/configure-vm-arguments-b82d392.md).

The properties are the following:


<table>
<tr>
<th valign="top">

System Property



</th>
<th valign="top">

Value



</th>
<th valign="top">

Description



</th>
</tr>
<tr>
<td valign="top">

`com.sap.cloud.security.um.user_provider_name`



</td>
<td valign="top">

*onpremise*



</td>
<td valign="top">

This property specifies what user provider the application VM uses.



</td>
</tr>
<tr>
<td valign="top">

`com.sap.cloud.security.um.destination_name`



</td>
<td valign="top">

*<on-premise\_destination\_name\>*



</td>
<td valign="top">

This property specifies the destination used by the on-premise user provider for the connection to the on-premise system. For more information about the destination, see [Managing Destinations](https://help.sap.com/viewer/b865ed651e414196b39f8922db2122c7/Cloud/en-US/e4f1d97cbb571014a247d10f9f9a685d.html "") :arrow_upper_right:.



</td>
</tr>
</table>

> ### Note:  
> The WAR file that you are using as a source during the deployment has to be protected declaratively or programmatically. For more information, see [Authentication](authentication-e637f62.md#loioe637f62abb571014857cb0232adc43a7).

> ### Example:  
> ```
> neo deploy --host hana.ondemand.com --account mysubaccount --application myapp --source samples/deploy_war/example.war --user mymail@example.com
> --vm-arguments "-Dcom.sap.cloud.security.um.user_provider_name=onpremise -Dcom.sap.cloud.security.um.destination_name=mydestination"
> ```

> ### Note:  
> The VM arguments passed using this command will have effect only until you re-deploy the application.

 <a name="task_kzd_1fv_ds"/>

<!-- task\_kzd\_1fv\_ds -->

## 2. Install and Configure SAP HANA Cloud Connector

Create the required destination and configure SAP HANA clolud connector as described in [Configure an On-Premise User Store](https://help.sap.com/viewer/b865ed651e414196b39f8922db2122c7/Cloud/en-US/933034aeb00d489eaf21d50bbb12fed5.html "Configure SAP BTP Java applications to use your corporate LDAP server or on-premise SAP system as a user store.") :arrow_upper_right:.

