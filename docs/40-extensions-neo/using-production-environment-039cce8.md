<!-- loio039cce87c276464f9875e7283b431e64 -->

# Using Production Environment



<a name="loio039cce87c276464f9875e7283b431e64__prereq_orr_dv3_p1b"/>

## Prerequisites

-   Have developed and tested your extension application against SAP Ariba APIs sandbox environment.

-   Have an application registered in SAP Ariba Developer Portal \([USA region](https://developer.ariba.com/api/) or [Europe region](https://eu.developer.ariba.com/api/)\) promoted for production access.




## Context

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**

Until now you have developed and tested your extension application against SAP Ariba APIs sandbox environment.

Now you want your application to work against your productive SAP Ariba system. You have promoted your SAP Ariba APIs application for production access. You need to configure the SAP Connectivity service to SAP Ariba APIs productive environment.



## Procedure

1.  If the API uses OAuth, [create an HTTP destination](https://help.sap.com/viewer/cca91383641e40ffbe03bdc78f00f681/Cloud/en-US/1e110da0ddd8453aaf5aed2485d84f25.html) to the SAP Ariba APIs OAuth Server in SAP BTP cockpit on application level. Use the following values:


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
    
         `https://api.ariba.com/v2/oauth/token` 


    
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
    
        Enter the SAP Ariba APIs registered application OAuth client ID.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
        Password


    
    </td>
    <td valign="top">
    
        Enter the SAP Ariba APIs registered application OAuth client secret.


    
    </td>
    </tr>
    </table>
    
2.  Create another HTTP destination to an SAP Ariba APIs in SAP BTP cockpit on application level or update the destination that you have used for the sandbox environment. Use the following values:


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
    
         `https://openapi.ariba.com/api/<service_name>/<version>/prod` 


    
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
    
        Depending on the API you need one of these options:

    -   NoAuthentication, if the API requires OAuth authentication.

    -   BasicAuthentication, if the API requires Basic authentication. Use the same credentials as in the service provider.



    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
        apiKey


    
    </td>
    <td valign="top">
    
        Enter the registered application API key.


    
    </td>
    </tr>
    </table>
    
3.  If the API uses OAuth authention, update your extension application to use OAuth 2.0 authentication.

    To access protected resources with OAuth 2.0, you need to acquire an access token. Find more information at [https://developer.ariba.com/api/guides](https://developer.ariba.com/api/guides) \(for the USA region\) or [https://eu.developer.ariba.com/api/guides](https://eu.developer.ariba.com/api/guides) \(for the Europe region\), in the **Authentication** section.


