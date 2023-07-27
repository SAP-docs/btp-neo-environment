<!-- loio8b1dc240f6684140b030da1abf62beec -->

# Sample Web Services Extension Applications



<a name="loio8b1dc240f6684140b030da1abf62beec__prereq_c1w_5xj_p1b"/>

## Prerequisites

Have configured connectivity from SAP BTP to SAP Ariba SOAP Web Service API.



## Context

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://launchpad.support.sap.com/#/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**

You can use these sample extension applications as a reference when developing your extension application running on the SAP BTP that consumes the SAP Ariba SOAP Web Service API.


<table>
<tr>
<th valign="top">

Sample



</th>
<th valign="top">

Description



</th>
</tr>
<tr>
<td valign="top">

Requisition Client for the SAP Ariba Procure-to-Pay Solution

[https://github.com/SAP/cloud-ariba-p2p-requisition-client-ext](https://github.com/SAP/cloud-ariba-p2p-requisition-client-ext)



</td>
<td valign="top">

You can use this sample to submit requisitions to your SAP Ariba instance.

Extends: SAP Ariba Procure-To-Pay

Uses: Import Requisition\(s\) API



</td>
</tr>
<tr>
<td valign="top">

Catalog Client for the SAP Ariba Procure-to-Pay Solution

[https://github.com/SAP/cloud-ariba-p2p-catalog-client-ext](https://github.com/SAP/cloud-ariba-p2p-catalog-client-ext)



</td>
<td valign="top">

You can use this sample to make a catalog search for a specified item in your SAP Ariba instance.

Extends: SAP Ariba Procure-To-Pay

Uses: Catalog Item Search API



</td>
</tr>
<tr>
<td valign="top">

SAP Ariba Simple Requisition Extension

[https://github.com/SAP/cloud-ariba-simple-requisition-ext](https://github.com/SAP/cloud-ariba-simple-requisition-ext)



</td>
<td valign="top">

This is a Web application running on SAP BTP that demonstrates the consumption of SAP Ariba Procure-to-Pay API for purchasing requisitions.

Extends: SAP Ariba Procure-To-Pay

Uses: Import Requisition\(s\) API



</td>
</tr>
<tr>
<td valign="top">

SAP Ariba QR Code Requisition Extension

[https://github.com/SAP/cloud-ariba-qrcode-requisition-ext](https://github.com/SAP/cloud-ariba-qrcode-requisition-ext)



</td>
<td valign="top">

This is a Web application running on SAP BTP that shows how to search for catalog items and submit requisitions using the SAP Ariba Procure-to-Pay API.

There are two possible usage scenarios for this application:

-   Scan a QR Code to show details about a specified item and submit a requisition through the application UI.

-   Scan a QR Code to submit requisition without starting the application UI.


Extends: SAP Ariba Procure-To-Pay

Uses: Catalog Item Search API, Import Requisition\(s\) API



</td>
</tr>
</table>

