<!-- loio81ddfa57e10247899bd49db49b12c9a4 -->

# Using Sandbox Environment



<a name="loio81ddfa57e10247899bd49db49b12c9a4__prereq_cvy_bwh_p1b"/>

## Prerequisites

-   You have an extension application in SAP Ariba APIs and a respective API key.

-   You have explored the SAP Ariba APIs and are familiar with the API calls and the SAP Ariba APIs sandbox environment URL.




## Context

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**

You can develop and test your extension application running on SAP BTP against SAP Ariba APIs sandbox environment using this API key. The connectivity from the SAP BTP to an API published on SAP Ariba APIs sandbox environment is done via HTTP [destination](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/e66f3eecbb5710148397a19b46c4979b.html) in SAP BTP.

For more information on how to develop a Java application running on SAP BTP, see [Getting Started with Java Applications](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/e66f3eecbb5710148397a19b46c4979b.html).



## Procedure

1.  Create an HTTP destination for an SAP Ariba API in SAP BTP cockpit on application level. See [Create HTTP Destinations](https://help.sap.com/viewer/cca91383641e40ffbe03bdc78f00f681/Cloud/en-US/1e110da0ddd8453aaf5aed2485d84f25.html).

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

     `https://openapi.ariba.com/api/<service_name>/<version>/sandbox` 


    
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

    NoAuthentication


    
    </td>
    </tr>
    <tr>
    <td valign="top">

    apiKey


    
    </td>
    <td valign="top">

    Enter the SAP Ariba APIs registered application API key.


    
    </td>
    </tr>
    </table>
    

