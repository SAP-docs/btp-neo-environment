<!-- loio71fdf1c0aaf141d18dd5ae2b41c86da3 -->

# Using an SAP System as an On-Premise User Store

 <a name="task_slh_dj4_g4"/>

<!-- task\_slh\_dj4\_g4 -->

## Overview

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**

You can configure applications running on SAP BTP to use a user store of an SAP NetWeaver \(7.2 or higher\) Application Server for Java system and a SAP Single Sign-On system. That way SAP BTP does not need to keep the whole user database, but requests the necessary information from an on-premise system.



## Prerequisites

-   You have installed the SDK.
-   You have set up the SDK location and landscape host.
-   You have set up the console client.

    For more information, see [Install the SAP BTP SDK for Neo Environment](../30-development-neo/install-the-sap-btp-sdk-for-neo-environment-7613843.md).

-   You have a SAP NetWeaver 7.2 or higher Application Server for Java system
-   You have installed and deployed federation software component archive \(SCA\) from SAP Single Sign-On \(SSO\) 2.0.

    For more information, see [Downloading and Installing the Federation Software](http://help.sap.com/saphelp_nwsso20/helpdata/en/57/90ac05d89d4bc9877a9eeab46b2ded/frameset.htm).




## Context

 <a name="concept_sj1_wm4_g4"/>

<!-- concept\_sj1\_wm4\_g4 -->

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
> neo deploy --host hana.ondemand.com --account myacc --application myapp --source samples/deploy_war/example.war --user mymail@example.com
> --vm-arguments "-Dcom.sap.cloud.security.um.user_provider_name=onpremise -Dcom.sap.cloud.security.um.destination_name=mydestination"
> ```

> ### Note:  
> The VM arguments passed using this command will have effect only until you re-deploy the application.

 <a name="task_uyt_4p4_g4"/>

<!-- task\_uyt\_4p4\_g4 -->

## 2. Configure the On-Premise System



## Context

The on-premise system is an AS Java with a deployed SCA from SAP Single Sign-On \(SSO\) 2.0. For the configuration of the on-premise AS Java system, proceed as follows:



<a name="task_uyt_4p4_g4__steps_mjh_sp4_g4"/>

## Procedure

1.  Configure a service user with SCIM\_READONLY role.

    For more information about the role assignment process, see [Assigning Principals to Roles or Groups](http://help.sap.com/saphelp_nw73/helpdata/en/4a/82ac96c56739f1e10000000a42189c/frameset.htm).

2.  If necessary, set the policy configuration to use the appropriate authentication method.

    You can use the following methods of authentication:

    -   Basic authentication

        The on-premise AS Java system is configured to use basic authentication by default. That means the `sap.com/tc~sec~scim~server*scim_v1` policy configuration is set to use *basic* Web template by default.

    -   Client certificate authentication

        For client certificate authentication, you need to update the `sap.com/tc~sec~scim~server*scim_v1` policy configuration to use *client\_cert* Web template. In addition, you have to configure the on-premise system to use the client certificate properly. For more information about the on-premise system configuration, see [Using X.509 Client Certificates on the AS Java](http://help.sap.com/saphelp_nw73/helpdata/en/62/881e3e3986f701e10000000a114084/content.htm).


    For more information about the policy configuration, see [Editing the Authentication Policy of AS Java Components](http://help.sap.com/saphelp_nw73/helpdata/en/4a/734e26fa92731fe10000000a42189c/frameset.htm).

3.  If your user does not exist in the on-premise system, create a technical user.

    For more information, see [Creating a Technical User](http://help.sap.com/saphelp_nw73/helpdata/en/43/f5e4b56b494c5de10000000a155369/frameset.htm).


 <a name="concept_e4q_vw4_g4"/>

<!-- concept\_e4q\_vw4\_g4 -->

## 3. Configure the Destination to the On-Premise System

For the proper communication with the on-premise AS Java system, you need to configure the destination of the Java application on SAP BTP. For more information, see [Configure Destinations from the Cockpit](https://help.sap.com/viewer/b865ed651e414196b39f8922db2122c7/Cloud/en-US/60735ad11d8a488c83537cdcfb257135.html "") :arrow_upper_right:.

You have to set the following properties for the destination of the cloud application:


<table>
<tr>
<th valign="top">

Destination Property



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

Name



</td>
<td valign="top">

*<on-premise\_destination\_name\>*



</td>
<td valign="top">

The name of the destination must match with the value of system property `com.sap.cloud.security.um.destination_name`.



</td>
</tr>
<tr>
<td valign="top">

Type



</td>
<td valign="top">

*HTTP*



</td>
<td valign="top">

For more information, see [HTTP Destinations](https://help.sap.com/viewer/b865ed651e414196b39f8922db2122c7/Cloud/en-US/b068356dd7c34cf7ad6b6023deeb317d.html "") :arrow_upper_right:.



</td>
</tr>
<tr>
<td valign="top">

URL



</td>
<td valign="top">

*https:// < AS Java Host\>:<AS Java HTTPS Port\>/scim/v1/* Or *http:// <Virtual host configured in Cloud Connector\>:<virtual Port\>/scim/v1/*



</td>
<td valign="top">

The URL to the on-premise AS Java system if it is exposed via reverse proxy. Or in case the on-premise systems is exposed via HANA Cloud Connector the virtual URL configured in Cloud Connector. In this case, the configured protocol should be http as the connectivity service is using secure tunneling to the on-premise system.



</td>
</tr>
<tr>
<td valign="top">

Proxy Type



</td>
<td valign="top">

*Internet* or *OnPremise*



</td>
<td valign="top">

-   Internet

    If you use an internet proxy, you have to make sure that the on-premise system is accessible from the application VM.

-   OnPremise

    If you use an on-premise proxy, you have to install SAP HANA cloud connector and configure a tunnel from the destination URL to the on-premise system. For more information about SAP HANA cloud connector, see [Cloud Connector](https://help.sap.com/viewer/cca91383641e40ffbe03bdc78f00f681/Cloud/en-US/e6c7616abb5710148cfcf3e75d96d596.html "Learn more about the Cloud Connector: features, scenarios and setup.") :arrow_upper_right:.




</td>
</tr>
<tr>
<td valign="top">

Authentication



</td>
<td valign="top">

*BasicAuthentication* or *ClientCertificateAuthentication*



</td>
<td valign="top">

For the configuration of such an authentication, you need to specify the credentials of the service user from the on-premise system. For more information about the destination configuration, see [HTTP Destinations](https://help.sap.com/viewer/b865ed651e414196b39f8922db2122c7/Cloud/en-US/b068356dd7c34cf7ad6b6023deeb317d.html "") :arrow_upper_right:.



</td>
</tr>
<tr>
<td valign="top">

User



</td>
<td valign="top">

*<user name\>*



</td>
<td valign="top">

This property is used for basic authentication only, and it specifies the name of the service user in the on-premise AS Java system.



</td>
</tr>
<tr>
<td valign="top">

Password



</td>
<td valign="top">

*<password\>*



</td>
<td valign="top">

This property is used for basic authentication only, and it specifies the service user's password.



</td>
</tr>
</table>

