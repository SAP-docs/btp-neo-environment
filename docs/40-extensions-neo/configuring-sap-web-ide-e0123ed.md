<!-- loioe0123ed45a9a4eb48595431b8429e5ac -->

# Configuring SAP Web IDE



## Context

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**

When developing a UI for an SAP S/4HANA Cloud solution, you can:

-   Test the UI in the SAP Web IDE. In this case, the particular service must be exposed via a communication arrangement.

-   Deploy the UI application developed in the SAP Web IDE in your SAP S/4HANA Cloud solution. In this case, a communication arrangement needs to be created for the SAP\_COM\_0013 scenario.


Within your account in SAP BTP, you are automatically subscribed to the SAP Web IDE. The authentication against the SAP Web IDE is based on the Identity Authentication tenant that is provided together with the SAP S/4HANA Cloud tenant.

In this scenario these are the important aspects:

-   The single sign-on configuration between SAP S/4HANA Cloud and SAP BTP ensures the secure and consistent data access for the applications.

-   OAuth configuration for OData connectivity for enabling the use of SAP S/4HANA OData APIs ensures the secure data communication with the extended solution.

-   With the SAP S/4HANA Cloud tenant provisioning by default it is established a trust between the Identity Authentication tenant and the SAP S/4HANA Cloud tenant and the following business catalogs assigned:


    <table>
    <tr>
    <th valign="top">

    Business Catalog ID


    
    </th>
    <th valign="top">

    Area


    
    </th>
    <th valign="top">

    Description


    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    *SAP\_BCR\_CORE\_COM* 


    
    </td>
    <td valign="top">
    
    Communication Management


    
    </td>
    <td valign="top">
    
    Users assigning communication arrangements to the key user


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *SAP\_BCR\_CORE\_EXT\_UI* 


    
    </td>
    <td valign="top">
    
    Extensibility – Deployment of Fiori Applications


    
    </td>
    <td valign="top">
    
    Users creating UI extensions


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *SAP\_BCR\_CORE\_EXT* 


    
    </td>
    <td valign="top">
    
    Extensibility


    
    </td>
    <td valign="top">
    
    Users creating extensions

    > ### Note:  
    > You need this catalog if you want to create custom business objects.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *SAP\_CORE\_BC\_EXT\_TST* 


    
    </td>
    <td valign="top">
    
    Extensibility – Custom Apps and Services


    
    </td>
    <td valign="top">
    
    You need this catalog if you want to implement and test a UI against a custom business object.


    
    </td>
    </tr>
    </table>
    



## Procedure

1.  Configure the Single Sign-On \(SSO\).

    A single sign-on \(SSO\) configuration between SAP S/4HANA Cloud and SAP BTP and the principal propagation enablement ensure the secure and consistent access for the extension solutions. You need to use SSO and OData access with principal propagation, to ensure that the data is accessed on behalf of the proper authorized user.

    Follow the steps described in [Optional: Configure Single-Sign On Manually](optional-configure-single-sign-on-manually-789a120.md).

    1.  Configure the SAP BTP trust.

    2.  Create a certificate and get the metadata file. Then, import it in the Identity Authentication tenant.


2.  Set up the extension application.

    To set up the extension application, you need to configure the connectivity between SAP BTP and SAP S/4HANA Cloud tenant.

    The connectivity configuration steps are required on both systems:

    > ### Note:  
    > The OAuth authentication method can be used only when a common identity provider is configured for both systems.

    1.  On SAP S/4HANA Cloud side, you have to maintain the communication settings. See **step 1** from [Connectivity Settings Using SAML Bearer Assertion Authentication](connectivity-settings-using-saml-bearer-assertion-authentication-1598e9d.md).

    2.  On the SAP BTP side, you have to create an HTTP destination with *OAuth2SAMLBearerAssertion* for authentication method. See **step 2** from [Connectivity Settings Using SAML Bearer Assertion Authentication](connectivity-settings-using-saml-bearer-assertion-authentication-1598e9d.md).


3.  Check the setup of the OAuth communication.

    You need to check whether the whole setup is working. See [Check the Setup of the OAuth Communication](check-the-setup-of-the-oauth-communication-ceebbb6.md).


