<!-- loioc6f5764433354640a1e44b893399eaee -->

# Using an SAP HANA XS Database System

Use SAP HANA single-container database systems designed for developing with SAP HANA in a productive environment.

<a name="reference_bmm_kmy_ndb"/>

<!-- reference\_bmm\_kmy\_ndb -->

## SAP HANA XS Database Systems in Enterprise Accounts



> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://launchpad.support.sap.com/#/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**



<a name="reference_bmm_kmy_ndb__section_vm2_yry_ndb"/>

## Prerequisites

An SAP HANA XS database system is deployed in a subaccount in your enterprise account. For more information, see [Install Database Systems](https://help.sap.com/viewer/3fa880aa54b74110ae99ad01503fcd60/Cloud/en-US/1261e6b87e174c05b774ea38fa3c8c51.html "Install a database system in the Neo environment using the SAP BTP cockpit.") :arrow_upper_right:.



<a name="reference_bmm_kmy_ndb__section_wm2_yry_ndb"/>

## Performance/Scalability Recommendation

Before going live with an application for which a significant number of users and/or significant load is expected, you should do a performance load test. This is best practice in the industry and we strongly recommend it for HANA XS applications.



<a name="reference_bmm_kmy_ndb__section_xm2_yry_ndb"/>

## Administrative Database Users

SAP BTP creates four users that it requires to manage the database: *SYSTEM*, *BKPMON*, *CERTADM*, and *PSADBA*. These users are reserved for use by SAP BTP. For more information, see [Create a Database Administrator User](create-a-database-administrator-user-c0fce6f.md).

> ### Caution:  
> Do not delete or deactivate these users or change their passwords.



<a name="reference_bmm_kmy_ndb__section_ym2_yry_ndb"/>

## Technical Database User

Each SAP HANA XS database system has a technical database user `NEO_<guid>`, which is created automatically when the database system is assigned to a subaccount. A technical database user is not the same as a normal database user and is provided purely as a mechanism for enabling schema access.

> ### Caution:  
> Do not delete or change the technical database user in any way \(password, roles, permissions, and so on\).



<a name="reference_bmm_kmy_ndb__section_zm2_yry_ndb"/>

## Features

See the overview below for details about available features:


<table>
<tr>
<th valign="top">

Feature



</th>
<th valign="top">

Description



</th>
</tr>
<tr>
<td valign="top">

Database users



</td>
<td valign="top">

Specifics for SAP BTP:

-   [Creating Database Users](creating-database-users-a55b836.md)
-   [Create a Database Administrator User](create-a-database-administrator-user-c0fce6f.md)



</td>
</tr>
<tr>
<td valign="top">

User management



</td>
<td valign="top">

You have full administration privileges to manage users

See:

-   [Managing SAP HANA Users](http://help.sap.com/saphelp_hanaplatform/helpdata/en/ed/7af17e5ae14de694d9bee5f35098f4/content.htm?frameset=/en/c0/555f0bbb5710148faabb0a6e35c457/frameset.htm)
-   [Setting Up Roles and Authorizations](http://help.sap.com/saphelp_hanaplatform/helpdata/en/8f/f545995b594245b2508a380457fbc8/content.htm?frameset=/en/9a/b0b327addd411ab6eadeba205a889e/frameset.htm)
-   [SAP HANA User and Role Management](http://help.sap.com/saphelp_hanaplatform/helpdata/en/de/a55d23bb571014bf25f6ed0d3b2b17/content.htm?frameset=/en/de/ec02ebbb57101483bdf3194c301d2e/frameset.htm)



</td>
</tr>
<tr>
<td valign="top">

Database Administration



</td>
<td valign="top">

See [Administration](https://help.sap.com/viewer/d4790b2de2f4429db6f3dff54e4d7b3a/Cloud/en-US/ac41e325a62e4d6c8516d7a63ef41df7.html "Use the SAP BTP cockpit or the console client to administer your database systems and databases in the Neo environment in SAP regions.") :arrow_upper_right:



</td>
</tr>
<tr>
<td valign="top">

Web-based tools



</td>
<td valign="top">

-   SAP HANA Web-based Development Workbench
-   SAP HANA Cockpit
-   SAP HANA XS Administration Tool

See:

-   [Supported SAP HANA Web-based Tools](supported-sap-hana-web-based-tools-ad3717d.md)
-   [Roles Required for Web-based Tools](assign-roles-required-for-the-sap-hana-xs-administration-tool-c006db5.md#loiod7c4ca5dac4f4dbbb47901eebe9ea0d1)
-   [Developing Applications in Web-based Environments](http://help.sap.com/saphelp_hanaplatform/helpdata/en/7f/99b0f952d04792912587c99e299ef5/content.htm?frameset=/en/5f/eb72f0511e43449f9ad79409a5d259/frameset.htm)
-   [SAP HANA XS Administration Tools](http://help.sap.com/saphelp_hanaplatform/helpdata/en/68/6f32f2da7947368f8a6906860bc19b/content.htm?frameset=/en/00/0ca1e3486640ef8b884cdf1a050fbb/frameset.htm)



</td>
</tr>
<tr>
<td valign="top">

Eclipse



</td>
<td valign="top">

-   [Install SAP HANA Tools for Eclipse](install-sap-hana-tools-for-eclipse-b0e351a.md)
-   [Connect to SAP HANA Databases via the Eclipse IDE](https://help.sap.com/viewer/d4790b2de2f4429db6f3dff54e4d7b3a/Cloud/en-US/4efc124a0ccc42b3b502ad3a3908d23d.html "Connect to an SAP HANA single-container (XS) or tenant database system (MDC) using SAP HANA tools via the Eclipse IDE.") :arrow_upper_right:



</td>
</tr>
<tr>
<td valign="top">

Security



</td>
<td valign="top">

Choice of authentication method

See:

-   [Configure SAML 2.0 Authentication](configure-saml-2-0-authentication-2a71022.md)
-   [SAP HANA XS Administration Tools](http://help.sap.com/saphelp_hanaplatform/helpdata/en/68/6f32f2da7947368f8a6906860bc19b/content.htm?frameset=/en/00/0ca1e3486640ef8b884cdf1a050fbb/frameset.htm)



</td>
</tr>
<tr>
<td valign="top">

Connectivity destinations



</td>
<td valign="top">

-   [Connectivity for SAP HANA XS (Enterprise Version)](https://help.sap.com/viewer/b865ed651e414196b39f8922db2122c7/Cloud/en-US/9d0e9e8397f544d9a5de5df52fd1e757.html "") :arrow_upper_right:
-   [Maintaining HTTP Destinations](https://help.sap.com/viewer/b3d0daf2a98e49ada00bf31b7ca7a42e/2.0.latest/en-US/ca340c09551c40b7837e773b9d051821.html)



</td>
</tr>
<tr>
<td valign="top">

Monitoring



</td>
<td valign="top">

-   [Configure Availability Checks for SAP HANA XS Applications from the Cockpit](configure-availability-checks-for-sap-hana-xs-applications-from-the-cockpit-a6663f0.md)

-   [Configure Availability Checks for SAP HANA XS Applications from the Console Client](configure-availability-checks-for-sap-hana-xs-applications-from-the-console-client-951d9b8.md)

-   [View Monitoring Metrics of a Database System](view-monitoring-metrics-of-a-database-system-b02814d.md)

-   [View Monitoring Metrics of an SAP HANA XS Application](https://help.sap.com/viewer/64f7d2b06c6b40a9b3097860c5930641/Cloud/en-US/c39b4a143a3647a9810cdd05882703a0.html "In the SAP BTP cockpit, you can view the history of custom checks to help you monitor your SAP HANA XS application.") :arrow_upper_right:




</td>
</tr>
<tr>
<td valign="top">

Debugging



</td>
<td valign="top">

-   SAP HANA Web-based Development Workbench

    See: [Debug with SAP HANA Web-based Development Workbench](debug-with-sap-hana-web-based-development-workbench-1beaa7a.md)

-   Supported by the SAP HANA Tools plug-in for Eclipse as of release 7.4.



</td>
</tr>
<tr>
<td valign="top">

Launch SAP HANA XS applications



</td>
<td valign="top">

[Launch SAP HANA XS Applications](launch-sap-hana-xs-applications-0dd61c3.md) 



</td>
</tr>
<tr>
<td valign="top">

Java development



</td>
<td valign="top">

[bind-hana-dbms](../50-administration-and-ops-neo/bind-hana-dbms-affa782.md) 



</td>
</tr>
</table>

**Related Information**  


[SAP HANA Administration Guide](https://help.sap.com/viewer/6b94445c94ae495c83a19646e7c3fd56/2.0.00/en-US)

[SAP HANA Security Guide](https://help.sap.com/viewer/b3ee5778bc2e4a089d3299b82ec762a7/2.0.00/en-US)

[SAP HANA Developer Guide for SAP HANA Studio](https://help.sap.com/viewer/52715f71adba4aaeb480d946c742d1f6/2.0.00/en-US)

[SAP HANA Developer Guide for SAP HANA Web Workbench](https://help.sap.com/viewer/b3d0daf2a98e49ada00bf31b7ca7a42e/2.0.00/en-US/)

