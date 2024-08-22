<!-- loio1b651b3aa5f54538a8f452f6fda0f5c3 -->

# Default Trace File

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of the following technology portfolios: application development; process automation; integration; data, analytics, and enterprise planning; artificial intelligence. The platform offers users the ability to turn data into business value, compose end-to-end business processes, connect entire IT landscapes, and personalize, build and extend SAP applications. This reduces the overall total cost of ownership maintaining SAP landscapes and third-party software across end-to-end business processes.") :arrow_upper_right:.**



## Context

This page describes the format of the `Default Trace` file. You can view this file for your Web applications via the cockpit.

For more information, see [Investigating Performance Issues Using the SQL Trace](../30-development-neo/investigating-performance-issues-using-the-sql-trace-e820e18.md).



## Default Trace Header


<table>
<tr>
<th valign="top">

Parameter

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

`FILE_TYPE`

</td>
<td valign="top">

The type of the `Default Trace`

</td>
</tr>
<tr>
<td valign="top">

`FILE_ID`

</td>
<td valign="top">

The identifier of the `Default Trace`

</td>
</tr>
<tr>
<td valign="top">

`ENCODING`

</td>
<td valign="top">

The encoding type used in the cloud database

</td>
</tr>
<tr>
<td valign="top">

`RECORD_SEPARATOR`

</td>
<td valign="top">

ASCII symbol for separating the log records. In our case, it is "**|**" \(ASCII code: **124**\)

</td>
</tr>
<tr>
<td valign="top">

`COLUMN_SEPARATOR`

</td>
<td valign="top">

ASCII symbol for separating the columns in the `Default Trace`. In our case, it is "**\#**" \(ASCII code: **35**\)

</td>
</tr>
<tr>
<td valign="top">

`ESC_CHARACTER`

</td>
<td valign="top">

ASCII symbol for escape. In our case, it is "**\\**" \(ASCII code: **92**\)

</td>
</tr>
<tr>
<td valign="top">

`COLUMNS`

</td>
<td valign="top">

Each log record contains the following information in the order displayed in the log file header: *Time*, *TZone*, *Severity*, *Logger*, *ACH*, *User*, *Thread*, *Bundle name*, *JPSpace*, *JPAppliance*, *JPComponent*, *Tenant Alias*, and *Text*.

</td>
</tr>
<tr>
<td valign="top">

`SEVERITY_MAP`

</td>
<td valign="top">

The severity map represents the following severity levels order:

FINEST|Information|FINER|Information|FINE|Information|CONFIG|Information|DEBUG|Information|PATH|Information|INFO|Information|WARNING|Warning|ERROR|Error|SEVERE|Error|FATAL|Error

</td>
</tr>
<tr>
<td valign="top">

`HEADER_END`

</td>
<td valign="top">

 

</td>
</tr>
</table>

Besides the main log information, the `Default Trace` logs information about the tenant users that have accessed a relevant Web application. This information is provided in the new *Tenant Alias* column parameter, which is automatically logged by the runtime. The *Tenant Alias* is:

-   A human-readable string;
-   For new accounts, it is shorter than the tenant ID \(8-30 characters\);
-   Unique for the relevant SAP BTP landscape;
-   Equal to the account name \(for new accounts\); might be equal to the tenant ID \(for old accounts\).



## Example

In this example, the application has been accessed on behalf of two tenants - with identifiers **42e00744-bf57-40b1-b3b7-04d1ca585ee3** and **5c42eee4-d5ad-494e-9afb-2be7e55d0f9c**.

```
FILE_TYPE:DAAA96DE-B0FB-4c6e-AF7B-A445F5BF9BE2
FILE_ID:1391169413918
ENCODING:[UTF8|NWCJS:ASCII]
RECORD_SEPARATOR:124
COLUMN_SEPARATOR:35
ESC_CHARACTER:92
COLUMNS:Time|TZone|Severity|Logger|ACH|User|Thread|Bundle name|JPSpace|JPAppliance|JPComponent|Tenant Alias|Text|
SEVERITY_MAP:FINEST|Information|FINER|Information|FINE|Information|CONFIG|Information|DEBUG|Information|PATH|Information|INFO|Information|WARNING|Warning|ERROR|Error|SEVERE|Error|FATAL|Error
HEADER_END

2014 01 31 12:07:09#+00#INFO#com.sap.demo.tenant.context.TenantContextServlet##anonymous#http-bio-8041-exec-1##myaccount#myapplication#web#null#null#myaccount#The app was accessed on behalf of tenant with ID: '42e00744-bf57-40b1-b3b7-04d1ca585ee3'|
2014 01 31 12:08:30#+00#INFO#com.sap.demo.tenant.context.TenantContextServlet##anonymous#http-bio-8041-exec-3##myaccount#myapplication#web#null#null#subscriberaccount#The app was accessed on behalf of tenant with ID: '5c42eee4-d5ad-494e-9afb-2be7e55d0f9c'|


```

**Related Information**  


[Logging for the Neo Environment](https://help.sap.com/viewer/ee8e8a203e024bbb8c8c2d03fce527dc/Cloud/en-US/e6e8ccd3bb571014b6afdc54744eef4d.html)

[Developing Multitenant Applications in the Neo Environment](../30-development-neo/developing-multitenant-applications-in-the-neo-environment-54a7615.md "In the Neo environment of SAP BTP, you can develop and run multitenant (tenant-aware) applications. These applications run on a shared compute unit that can be used by multiple consumers (tenants). Each consumer accesses the application through a dedicated URL.")

