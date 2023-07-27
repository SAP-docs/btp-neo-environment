<!-- loio6648ccfa8a654454b3f43631817c69ef -->

# Register a Home Page Tile for the Extension Application

You register a Home Page tile for the extension application in the extended SAP SuccessFactors system so that you can access the application directly from the SAP SuccessFactors Employee Central \(EC\) Home Page.



## Prerequisites

> ### Note:  
> The support of the Home Page tiles in SAP SuccessFactors has been discontinued. See [Home Page Tiles](https://help.sap.com/docs/SAP_SUCCESSFACTORS_PLATFORM/59f821da545a4bdb94f1eb8fa22e4b36/00c8674252d1461691bec004be68f425.html).
> 
> We recommend that you use the latest home page. See [Migrating to the Latest Home Page](https://help.sap.com/docs/SAP_SUCCESSFACTORS_PLATFORM/59f821da545a4bdb94f1eb8fa22e4b36/8d2921382f9544dc8d14cb249ec6a289.html).

-   You have deployed and started the extension application for which you are registering the Home Page tile.
-   You have registered the extension application as an authorized assertion consumer service. For more information, see [Register the Extension Application as an Authorized Assertion Consumer Service](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/47c4bfff70e94491a82353ddc66eb9a1.html).

-   You have the Home Page tile provided as part of the application interface.

    You develop the content of the tile as a dedicated HTML page inside the application and size it according to the desired tile size. You describe the tiles in a `tiles.json` descriptor and package them in a `ZIP` archive. For more information about the structure of the `tiles.json` descriptor, see [Home Page Tiles JSON File](home-page-tiles-json-file-872d124.md).

-   You have downloaded and set up the console client for SAP BTP, Neo environment. For more information, see [Console Client for the Neo Environment](../50-administration-and-ops-neo/console-client-for-the-neo-environment-7613230.md).

-   You have created the `tiles.json` descriptor.



## Context

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://launchpad.support.sap.com/#/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**

The SAP SuccessFactors EC Home Page provides a framework that allows different modules to provide access to their functionality using tiles. For the extension applications hosted in the SAP BTP extension subaccount, SAP BTP allows you to register Home Page tiles in the extended SAP SuccessFactors system. To do so, you use the `hcmcloud-register-home-page-tiles` console client command. Both Java and HTML5 extension applications are supported.



<a name="loio6648ccfa8a654454b3f43631817c69ef__steps_b5d_h2k_lt"/>

## Procedure

1.  To start the console client for SAP BTP, Neo environment, open the command prompt and navigate to the folder containing neo.bat/sh \(SDK installation folder/tools\). For more information, see [Using the Console Client](../50-administration-and-ops-neo/using-the-console-client-8900b22.md).

2.  Register the SAP SuccessFactors EC Home Page tiles in the SAP SuccessFactors company instance linked to the specified SAP BTP subaccount. In the console client command line, execute: `hcmcloud-register-home-page-tiles`, as follows:

    -   For an application deployed in your subaccount, specify the name of your extension application for the `application` parameter.

        For example, to register a Home Page tile for a Java extension application running in your subaccount in the US East region, execute:

        ```
        neo hcmcloud-register-home-page-tiles --application <my_application> --application-type java --account <my_extension_subaccount> --user <my_email@example.com> --host us1.hana.ondemand.com --location <path to the tiles.json file>
        ```

    -   For an application to which your subaccount is subscribed, specify the application provider subaccount and the name of the extension application for the `application` parameter in the following format: *<application\_provider\_subaccount\>*:*<my\_application\>*.

        For example, to register a Home Page tile for a Java extension application to which your subaccount in the US East region is subscribed, execute:

        ```
        neo hcmcloud-register-home-page-tiles --application <application_provider_subaccount:my_application> --application-type java --account <my_extension_subaccount> --user <my_email@example.com> --host us1.hana.ondemand.com --location <path to the tiles.json file>
        ```


    > ### Note:  
    > The size of the tile descriptor file must not exceed 100 KB.

3.  \(Optional\) List the extension application Home Page tiles registered in the SAP SuccessFactors company instance associated with the extension subaccount. In the console client command line, execute `hcmcloud-get-registered-home-page-tiles`, as follows:

    -   For an application deployed in your subaccount, specify the name of your extension application for the `application` parameter.

        For example, to list the tiles registered for a Java extension application deployed in your subaccount in the US East region, execute:

        ```
        neo hcmcloud-get-registered-home-page-tiles --application <my_application> --application-type java --account <my_extension_subaccount> --user <my_email@example.com> --host us1.hana.ondemand.com
        ```

    -   For an application to which your subaccount is subscribed, specify the application provider subaccount and the name of the extension application for the `application` parameter in the following format: *<application\_provider\_subaccount\>*:*<my\_application\>*.

        For example, to list the tiles registered for a Java extension application to which your subaccount in the US East region is subscribed, execute:

        ```
        neo hcmcloud-get-registered-home-page-tiles --application <application_provider_subaccount>:<my_application> --application-type java --account <my_extension_subaccount> --user <my_email@example.com> --host us1.hana.ondemand.com
        ```


    > ### Note:  
    > If you do not specify the `application` parameter, the command returns all the tiles registered in the SAP SuccessFactors EC Home Page of the SAP SuccessFactors company instance linked to the extension subaccount.
    > 
    > There is no lifecycle dependency between the tiles and the application, so the application may not be started or may not be deployed anymore.

4.  \(Optional\) If your scenario requires it, unregister the SAP SuccessFactors EC Home Page tiles registered for the extension application. In the console client command line, execute `hcmcloud-unregister-home-page-tiles`, as follows:

    -   For an application deployed in your subaccount, specify the name of your extension application for the `application` parameter.

        For example, to unregister the SAP SuccessFactors EC Home Page tiles for a Java application deployed in your subaccount in the US East region, execute:

        ```
        neo hcmcloud-unregister-home-page-tiles --application <my_application> --application-type java --account <my_extension_subaccount> --user <my_email@example.com> --host us1.hana.ondemand.com
        ```

    -   For an application to which your subaccount is subscribed, specify the application provider subaccount and the name of your extension application for the `application` parameter in the following format: *<application\_provider\_subaccount\>*:*<my\_application\>*.

        For example, to unregister the SAP SuccessFactors EC Home Page tiles for a Java application to which your subaccount in the US East region is subscribed, execute:

        ```
        neo hcmcloud-unregister-home-page-tiles --application <application_provider_subaccount>:<my_application> --application-type java --account <my_extension_subaccount> --user <my_email@example.com> --host us1.hana.ondemand.com
        ```


    > ### Note:  
    > There is no lifecycle dependency between the tiles and the application, so the application may not be started or may not be deployed anymore.


