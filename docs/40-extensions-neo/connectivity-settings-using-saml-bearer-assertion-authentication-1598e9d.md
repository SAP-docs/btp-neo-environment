<!-- loio1598e9d80ec241a282e4b02e1ff625c7 -->

# Connectivity Settings Using SAML Bearer Assertion Authentication



## Context

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**

To set up the SAP Web IDE, you need to configure the connectivity between SAP BTP and SAP S/4HANA Cloud tenant. You have to use SAML Bearer Assertion authentication, and you need to configure both SAP S/4HANA Cloud and SAP BTP sides.

The general procedure is described in [Using SAML Bearer Assertion Authentication](using-saml-bearer-assertion-authentication-a4f1d55.md#loioa4f1d55c57b446fc8d66a9f59009225f). These are the SAP Web IDE specifics you need to take into account:



## Procedure

1.  [Set Up SAP S/4HANA Cloud Side](using-saml-bearer-assertion-authentication-a4f1d55.md#loio3b5d869c98044f039b6d400def2c0f0d).

    1.  Create a communication user.

    2.  Create a communication system.

        In step 2.f, when specifying the *Technical Data* section, you need to specify a hostname. The hostname of the SAP Web IDE is the SAP Web IDE URL. You can get it by following the steps in [Configure and Check the SSO Configuration](configure-and-check-the-sso-configuration-f907bd4.md).

        > ### Note:  
        > If you have integrated SAP Web IDE with SAP S/4HANA Cloud 1805 or earlier using the communication scenario SAP\_COM\_0013, you need to update the integration. See
        > 
        > [Updating the Integration of SAP S/4HANA and SAP Web IDE](https://help.sap.com/viewer/825270ffffe74d9f988a0f0066ad59f0/CF/en-US/8e9f4cd296df4dfd88230081bebe12c5.html).

    3.  Create a communication arrangement and select a communication scenario.

        In this case the scenario is `SAP_COM_0013`, SAP Web IDE Integration.


2.  [Set Up SAP BTP Side](using-saml-bearer-assertion-authentication-a4f1d55.md#loio4da2a4450422409a9b4b237a9858d3ea).

    When creating an HTTP destination, these are the SAP Web IDE-specific values:

    1.  Configure the basic settings:


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
        
        `Name`
        
        </td>
        <td valign="top">
        
        Enter a meaningful name.
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        `Type`
        
        </td>
        <td valign="top">
        
        `HTTP`
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        `Description`
        
        </td>
        <td valign="top">
        
        \(Optional\) Enter a meaningful description.
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        `URL`
        
        </td>
        <td valign="top">
        
        The service URL from the communication arrangement. To do that, copy the first part of the *Service URL/Service Interface* column \(the part before /sap/..\).
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        `Proxy Type`
        
        </td>
        <td valign="top">
        
        `Internet`
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        `Authentication`
        
        </td>
        <td valign="top">
        
        `OAuth2SAMLBearerAssertion`
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        `Audience`
        
        </td>
        <td valign="top">
        
        This is the *SAML2 Audience* from the *OAuth 2.0 Details* in the communication arrangement. See [Set Up SAP S/4HANA Cloud Side](using-saml-bearer-assertion-authentication-a4f1d55.md#loio3b5d869c98044f039b6d400def2c0f0d), **step 3**.
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        `Client Key`
        
        </td>
        <td valign="top">
        
        The name of the communication user you have in the SAP S/4HANA Cloud tenant.
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        `Token Service URL`
        
        </td>
        <td valign="top">
        
        This is the *Token Service URL* from the *OAuth 2.0 Details* in the communication arrangement. See [Set Up SAP S/4HANA Cloud Side](using-saml-bearer-assertion-authentication-a4f1d55.md#loio3b5d869c98044f039b6d400def2c0f0d), **step 3**.
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        `Token Service User`
        
        </td>
        <td valign="top">
        
        The name of the communication user you have in the SAP S/4HANA Cloud tenant.
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        `Token Service Password`
        
        </td>
        <td valign="top">
        
        The password for the communication user.
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        `System User`
        
        </td>
        <td valign="top">
        
        This parameter is not used, leave the field empty.
        
        </td>
        </tr>
        </table>
        
    2.  Configure the required additional properties. To do so, in the *Additional Properties* panel, choose *New Property*, and enter the following property:


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
        
        `authnContextClassRef`
        
        </td>
        <td valign="top">
        
        `urn:oasis:names:tc:SAML:2.0:ac:classes:X509` 
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        `WEBIDEEnabled`
        
        </td>
        <td valign="top">
        
        `true` 
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        `WEBIDEUsage`
        
        </td>
        <td valign="top">
        
        `odata_abap,ui5_execute_abap,dev_abap` 
        
        </td>
        </tr>
        </table>
        


