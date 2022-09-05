<!-- loioc006db57b3654c5fbcd9f6136b556c3d -->

# Assign Roles Required for the SAP HANA XS Administration Tool

To work with the SAP HANA XS Administration Tool, add the required rules to your database user.



## Context

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**

The initial set of roles of your database user also contains the *sap.hana.xs.ide.roles::Developer* role, allowing you to work with the SAP HANA Web-based Development Workbench, but not the SAP HANA XS Administration tool.

To be able to work with the SAP HANA XS Administration Tool `(https://<schema><subaccount>.<host>sap/hana/xs/admin/)`, you require the relevant *sap.hana.xs.admin.roles*. However, these are not included in the initial set of roles. To assign these roles to your database user, perform the following steps:



<a name="loioc006db57b3654c5fbcd9f6136b556c3d__steps_dns_yyd_ndb"/>

## Procedure

1.  Log on in with your user to one of the following tools:

    -   Use the Eclipse IDE and connect to your SAP HANA studio. For more information, see [Connect to SAP HANA Databases via the Eclipse IDE](https://help.sap.com/viewer/d4790b2de2f4429db6f3dff54e4d7b3a/Cloud/en-US/4efc124a0ccc42b3b502ad3a3908d23d.html "Connect to an SAP HANA single-container (XS) or tenant database system (MDC) using SAP HANA tools via the Eclipse IDE.") :arrow_upper_right:.
    -   Use the SAP HANA Web-based Development Workbench. For more information, see [Supported SAP HANA Web-based Tools](supported-sap-hana-web-based-tools-ad3717d.md).

2.  In the *Security* section, assign the required set of roles to yourself. For more information, see [Roles Required for Web-based Tools](assign-roles-required-for-the-sap-hana-xs-administration-tool-c006db5.md#loiod7c4ca5dac4f4dbbb47901eebe9ea0d1).


 <a name="loiod7c4ca5dac4f4dbbb47901eebe9ea0d1"/>

<!-- loiod7c4ca5dac4f4dbbb47901eebe9ea0d1 -->

## Roles Required for Web-based Tools

To use the SAP HANA Web-based tools, you require specific roles.




<table>
<tr>
<th valign="top">

Role



</th>
<th valign="top">

Description



</th>
</tr>
<tr>
<td valign="top" align="center" colspan="2">

**SAP HANA Web-based Development Workbench**



</td>
</tr>
<tr>
<td valign="top">

*sap.hana.xs.ide.roles::EditorDeveloper* or parent role *sap.hana.xs.ide.roles::Developer*



</td>
<td valign="top">

Use the Editor component of the SAP HANA Web-based Development Workbench.



</td>
</tr>
<tr>
<td valign="top">

*sap.hana.xs.debugger::Debugger*



</td>
<td valign="top">

Debug server-side JavaScript code.



</td>
</tr>
<tr>
<td valign="top" align="center" colspan="2">

**SAP HANA XS Administration Tool**



</td>
</tr>
<tr>
<td valign="top">

*sap.hana.xs.admin.roles::HTTPDestViewer*



</td>
<td valign="top">

View HTTP destinations.



</td>
</tr>
<tr>
<td valign="top">

*sap.hana.xs.admin.roles::HTTPDestAdministrator*



</td>
<td valign="top">

Full access to HTTP destination configurations \(display and edit\).



</td>
</tr>
<tr>
<td valign="top">

*sap.hana.xs.admin.roles::TrustStoreViewer*



</td>
<td valign="top">

Read-only access to the trust store, which contains the server's root certificate or the certificate of the certification authority that signed the server’s certificate.



</td>
</tr>
<tr>
<td valign="top">

*sap.hana.xs.admin.roles::TrustStoreAdministrator*



</td>
<td valign="top">

Full access to the SAP HANA XS application trust store to manage the certificates required to start SAP HANA XS applications.



</td>
</tr>
</table>

**Related Information**  


[Supported SAP HANA Web-based Tools](supported-sap-hana-web-based-tools-ad3717d.md "SAP BTP supports the following Web-based tools: SAP HANA Web-based Development Workbench, SAP HANA Studio, and SAP HANA XS Administration Tool.")

[SAP HANA Platform 1.0 SPS 12](https://help.sap.com/viewer/product/SAP_HANA_PLATFORM/1.0.12/en-US)

