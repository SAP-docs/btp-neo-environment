<!-- loioad3717d2c242436095fd12c158d7876f -->

# Supported SAP HANA Web-based Tools

SAP BTP supports the following Web-based tools: SAP HANA Web-based Development Workbench, SAP HANA Studio, and SAP HANA XS Administration Tool.



## Prerequisites

-   You have a database user. See [Creating Database Users](creating-database-users-a55b836.md).
-   Your database user is assigned the roles required for the relevant tool. See [Roles Required for Web-based Tools](assign-roles-required-for-the-sap-hana-xs-administration-tool-c006db5.md#loiod7c4ca5dac4f4dbbb47901eebe9ea0d1).



## Context

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**

You can access the SAP HANA Web-based tools using the Cockpit or the tool URLs. The following table summarizes what each supported tool does, and how to acess it.

**Supported Web-Based Tools for SAP HANA Development and Administration**


<table>
<tr>
<th valign="top">

Tool

</th>
<th valign="top">

Description

</th>
<th valign="top">

Where to Find It in the Cockpit

</th>
<th valign="top">

Tool URL

</th>
</tr>
<tr>
<td valign="top">

SAP HANA Web-based Development Workbench

</td>
<td valign="top">

Includes an all-purpose editor tool that enables you to maintain and run design-time objects in the SAP HANA repository. It does not support modeling activities.

For more information, see the [Developer Guide for SAP HANA Web Workbench](https://help.sap.com/viewer/b3d0daf2a98e49ada00bf31b7ca7a42e/2.0.00/en-US/).

</td>
<td valign="top">

*Development Tools* section: *SAP HANA Web-based Development Workbench* 

</td>
<td valign="top">

`https://<database instance><subaccount>.< host>/sap/hana/xs/ide/` 

</td>
</tr>
<tr>
<td valign="top">

SAP HANA Cockpit

</td>
<td valign="top">

Provides you with a single point-of -access to a range of Web-based applications for the online administration of SAP HANA.

For more information, see the [SAP HANA Administration Guide](https://help.sap.com/viewer/6b94445c94ae495c83a19646e7c3fd56/2.0.00/en-US).

> ### Note:  
> It is not possible to use the SAP HANA database lifecycle manager \(HDBLCM\) with the cockpit.



</td>
<td valign="top">

*Administration Tools* section: *SAP HANA Cockpit* 

</td>
<td valign="top">

`https://<database instance><subaccount>.<host>/sap/hana/xs/admin/cockpit` 

</td>
</tr>
<tr>
<td valign="top">

SAP HANA XS Administration Tool

</td>
<td valign="top">

Allows you, for example, to configure security options and HTTP destinations.

For more information, see the [SAP HANA Administration Guide](https://help.sap.com/viewer/6b94445c94ae495c83a19646e7c3fd56/2.0.00/en-US).

</td>
<td valign="top">

*Administration Tools* section: *SAP HANA XS Administration* 

</td>
<td valign="top">

`https://<database instance><subaccount>.<host>/sap/hana/xs/admin/` 

</td>
</tr>
</table>

> ### Remember:  
> When using the tools, log on with your database user \(**not** your SAP BTP user\). If this is your initial logon, you will be prompted to change your password. You are responsible for choosing a strong password and keeping it secure.

**Related Information**  


[Regions](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/350356d1dc314d3199dca15bd2ab9b0e.html "You can deploy applications in different regions. Each region represents a geographical location (for example, Europe, US East) where applications, data, or services are hosted.") :arrow_upper_right:

[Developing Applications in Web-based Environments](http://help.sap.com/saphelp_hanaplatform/helpdata/en/7f/99b0f952d04792912587c99e299ef5/content.htm)

[Debug with SAP HANA Web-based Development Workbench](debug-with-sap-hana-web-based-development-workbench-1beaa7a.md "You can only debug SAP HANA server-side JavaScript with the SAP HANA Tools plugin for Eclipse as of release 7.4. If you are working with lower plugin versions, use the SAP HANA Web-based Development Workbench to perform your debugging tasks.")

