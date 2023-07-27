<!-- loio555368f123c14351b962b68fa9d32632 -->

# Connect SAP BTP to SAP Ariba SOAP Web Service APIs



<a name="loio555368f123c14351b962b68fa9d32632__prereq_mkm_twj_p1b"/>

## Prerequisites

-   Have a new integration end-point created. See [Create New Integration End-Point](configure-the-sap-ariba-solution-2bd48cf.md#loio1fbecef94dd44130a5c54c3fa05ec341).

-   Have an integration task enabled. See [Enable an Integration Task](configure-the-sap-ariba-solution-2bd48cf.md#loioeeaae4b5d8d84e5ba45bddfb8d8ccace).




## Context

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://launchpad.support.sap.com/#/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**

You configure connectivity in SAP BTP by creating an HTTP destination.



<a name="loio555368f123c14351b962b68fa9d32632__steps_orz_ywj_p1b"/>

## Procedure

1.  Create an HTTP destination in SAP BTP cockpit on application level. See [Create HTTP Destinations](https://help.sap.com/viewer/cca91383641e40ffbe03bdc78f00f681/Cloud/en-US/1e110da0ddd8453aaf5aed2485d84f25.html).

2.  Use the following values for the HTTP destination:


    <table>
    <tr>
    <th valign="top">

    Parameter


    
    </th>
    <th valign="top">

    Value


    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    Name


    
    </td>
    <td valign="top">
    
    Enter a meaningful name.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Type


    
    </td>
    <td valign="top">
    
    HTTP


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Description


    
    </td>
    <td valign="top">
    
    \(Optional\) Enter a meaningful description.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    URL


    
    </td>
    <td valign="top">
    
    Enter the integration task URL.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Proxy Type


    
    </td>
    <td valign="top">
    
    Internet


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Authentication


    
    </td>
    <td valign="top">
    
    BasicAuthentication


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    User


    
    </td>
    <td valign="top">
    
    Enter the integration end point user ID.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Password


    
    </td>
    <td valign="top">
    
    Enter the integration end point password.


    
    </td>
    </tr>
    </table>
    
    > ### Note:  
    > Some of the SOAP Web Service APIs support Basic authentication. Others support authentication without Base64 encoding. Example Authorization headers:
    > 
    > -   Authorization: Basic base64 \(userID:password\)
    > 
    > -   Authorization: Basic userID:password
    > 
    > 
    > For more information on the supported authentications, see:
    > 
    > -   [SAP Ariba Strategic Sourcing solutions](https://help.sap.com/viewer/product/ARIBA_SOURCING/cloud/en-US?task=discover_task)
    > 
    > -   [SAP Ariba Procurement solutions](https://help.sap.com/viewer/product/ARIBA_PROCUREMENT/cloud/en-US?task=discover_task)


