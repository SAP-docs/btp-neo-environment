<!-- loiobd585c88b6a640ccaac1eab10fcd5f1b -->

# Extending SAP SuccessFactors in the Neo Environment

You can extend the scope of SAP SuccessFactors HXM Suite using extension applications on SAP BTP.

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of the following technology portfolios: application development; process automation; integration; data, analytics, and enterprise planning; artificial intelligence. The platform offers users the ability to turn data into business value, compose end-to-end business processes, connect entire IT landscapes, and personalize, build and extend SAP applications. This reduces the overall total cost of ownership maintaining SAP landscapes and third-party software across end-to-end business processes.") :arrow_upper_right:.**

This section guides you through the configuration tasks that you need to perform to enable the Neo environment for developing extension applications for your SAP SuccessFactors system.

> ### Note:  
> The content in this section is only relevant for cloud management tools feature set A. For more information, see [Cloud Management Tools - Feature Set Overview](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/caf4e4e23aef4666ad8f125af393dfb2.html).



<a name="loiobd585c88b6a640ccaac1eab10fcd5f1b__section_hy4_rvb_hjb"/>

## Overview

Extending SAP SuccessFactors on SAP BTP allows you to broaden the SAP SuccessFactors scope with applications running on the platform. This makes it quick and easy for companies to adapt and integrate SAP SuccessFactors cloud applications to their existing business processes, thus helping them maintain competitive advantage, engage their workforce and improve their bottom line.



<a name="loiobd585c88b6a640ccaac1eab10fcd5f1b__section_mt4_rvb_hjb"/>

## Integration Layers

With the extension scenario you have the following integration layers between SAP BTP and SAP SuccessFactors:

-   **Security and Connectivity**
    -   SAML 2.0 single sign-on \(SSO\)

    -   Integration between SAP SuccessFactors and the identity provider based on a trust configuration

    -   Extension application connectivity interaction with SAP SuccessFactors based on the HXM Suite OData API

    -   Extension application integration to consume events defined in the SAP SuccessFactors system

-   **Development, Administration and Lifecycle Management**
    -   Easy-to-configure connection between your account in SAP BTP and your SAP SuccessFactors system

    -   Seamless solution deployment, subscription and monitoring

    -   Development capabilities for building extensions that are tightly connected and integrated to SAP SuccessFactors by using all the authentication and authorization capabilities of the SAP BTP


-   **User Interface Integration**

    With the integration between SAP BTP and SAP SuccessFactors you have a harmonized user experience across the standard SAP SuccessFactors modules and the new platform extensions.

    The SAP SuccessFactors Employee Central \(EC\) Home Page provides a framework that allows different modules to provide access to their functionality using tiles. For the extension applications hosted in the extension subaccount in SAP BTP, the cloud platform allows you to register Home Page tiles in the extended SAP SuccessFactors system.

    The integration also enables the SAP Cloud Portal service and configures it for extensibility so that you can create an extension site to integrate your extension application in SAP SuccessFactors.




<a name="loiobd585c88b6a640ccaac1eab10fcd5f1b__section_mn4_rvb_hjb"/>

## Supported APIs

You can find a list and implementation details of the APIs supported by SAP SuccessFactors HXM Suite on SAP Help Portal, at [SAP SuccessFactors HXM Suite OData API: Reference Guide](https://help.sap.com/viewer/28bc3c8e3f214ab487ec51b1b8709adc/LATEST/en-US).



<a name="loiobd585c88b6a640ccaac1eab10fcd5f1b__section_bl4_rvb_hjb"/>

## Extension Application Installation

SAP BTP provides the following options for deploying and configuring SAP SuccessFactors extension application. The preferred option depends on your scenario.

-   Deploying and configuring an extension application using Multi-Target Applications \(preferable for productive scenarios\).

    For more information, see .[Multitarget Applications for the Neo Environment](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/e1bb7eb746d34237b8b47035adff5022.html).

-   Deploying and configuring an extension application using console client commands \(preferable for development scenarios\).

    For more information, see [Installing and Configuring Extension Applications](installing-and-configuring-extension-applications-fd92f74.md).




<a name="loiobd585c88b6a640ccaac1eab10fcd5f1b__section_mdb_34b_mdb"/>

## Process Flow

You have to configure the cloud platform extension integration with SAP SuccessFactors to enable the use of applications running on top of the platform from SAP SuccessFactors.

These are the steps you need to follow:

1.  [Configuring the Subaccount in SAP BTP for SAP SuccessFactors](configuring-the-subaccount-in-sap-btp-for-sap-successfactors-4f31621.md)

2.  [Installing and Configuring Extension Applications](installing-and-configuring-extension-applications-fd92f74.md)


