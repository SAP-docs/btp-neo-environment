<!-- loio47c4bfff70e94491a82353ddc66eb9a1 -->

# Register the Extension Application as an Authorized Assertion Consumer Service

Register the extension application as an authorized assertion consumer service to configure its access to the SAP SuccessFactors system through the SAP SuccessFactors identity provider \(IdP\).



## Prerequisites

-   The SAP BTP subaccount in which you configure the connectivity to the SAP SuccessFactors system is an extension subaccount. For more information about extension subaccounts, see [Extensions](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/08b1effc53634890a525f945017e2edc.html).
-   You have set up the console client for SAP BTP, Neo environment. See [Set Up the Console Client](../30-development-neo/set-up-the-console-client-7613dee.md).
-   You are either an administrator of the subaccount or have the developer platform role with the following platform scopes defined for it:
    -   readExtensionIntegration

    -   manageExtensionIntegration

    -   readHTML5Applications


-   You have downloaded and set up the console client for SAP BTP, Neo environment. For more information, see [Console Client for the Neo Environment](../50-administration-and-ops-neo/console-client-for-the-neo-environment-7613230.md).




## Context

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**

Extension applications deployed in an SAP BTP extension subaccount are authenticated against the SAP SuccessFactors \(IdP\). To ensure that only approved applications are using the SAP SuccessFactors IdP for authentication, you need to register the extension application as an authorized assertion consumer service, configure the application URL, the service provider audience URL and the service provider logout URL of the extension application in SAP SuccessFactors Provisioning. To do so you use the `hcmcloud-enable-application-access` console client command.

> ### Note:  
> This procedure is only valid for connections using the default SAP SuccessFactors.



## Procedure

1.  To start the console client for SAP BTP, Neo environment, open the command prompt and navigate to the folder containing neo.bat/sh \(SDK installation folder/tools\). For more information, see [Using the Console Client](../50-administration-and-ops-neo/using-the-console-client-8900b22.md).

2.  To register the extension application as an authorized assertion consumer service. In the console client command line, execute: `hcmcloud-enable-application-access`, as follows:

    -   For an application deployed in your subaccount, specify the name of your extension application for the `application` parameter.

        For example, to register a Java extension application running in your subaccount in the US East region, execute:

        ```
        neo hcmcloud-enable-application-access --application <my_application> --application-type java --account <my_extension_subaccount> --user <my_email@example.com> --host us1.hana.ondemand.com
        ```

    -   For an application to which your subaccount is subscribed, specify the application provider subaccount and the name of your extension application for the `application` parameter in the following format: *<application\_provider\_subaccount\>*:*<my\_application\>*.

        For example, to register a Java extension application to which your subaccount in the US East region is subscribed, execute:

        ```
        neo hcmcloud-enable-application-access --application <application_provider_subaccount:my_application> --application-type java --account <my_extension_subaccount> --user <my_email@example.com> --host us1.hana.ondemand.com
        ```


3.  \(Optional\) Display the status of an application entry in the list of authorized assertion consumer services for the SAP SuccessFactors system associated with an extension subaccount. In the console client command line, execute `hcmcloud-display-application-access`, as follows:

    -   For an application deployed in your subaccount, specify the name of your extension application for the `application` parameter.

        For example, to display the status of the authorized assertion consumer service entry for an application deployed in your subaccount in the US East region, execute:

        ```
        neo hcmcloud-display-application-access-status --application <my_application> --application-type java --account <my_extension_subaccount> --user <my_email@example.com> --host us1.hana.ondemand.com
        ```

    -   For an application to which your subaccount is subscribed, specify the application provider subaccount and the name of your extension application for the `application` parameter in the following format: *<application\_provider\_subaccount\>*:*<my\_application\>*.

        For example, to display the status of the authorized assertion consumer service entry for an application to which your subaccount in the US East region is subscribed, execute:

        ```
        neo hcmcloud-display-application-access-status --application <application_provider_subaccount>:<my_application> --application-type java --account <my_extension_subaccount> --user <my_email@example.com> --host us1.hana.ondemand.com
        ```


4.  \(Optional\) If your scenario requires it, remove the entry of the extension application from the list of authorized assertion consumer services for the SAP SuccessFactors system associated with the extension subaccount. In the console client command line, execute `hcmcloud-disable-application-access`, as follows:

    -   For an application deployed in your subaccount, specify the name of your extension application for the `application` parameter.

        For example, to remove the authorized assertion consumer service entry for a Java application deployed in your subaccount in the US East region, execute:

        ```
        neo hcmcloud-disable-application-access --application <my_application> --application-type java --account <my_extension_subaccount> --user <my_email@example.com> --host us1.hana.ondemand.com
        ```

    -   For an application to which your subaccount is subscribed, specify the application provider subaccount and the name of your extension application for the `application` parameter in the following format: *<application\_provider\_subaccount\>*:*<my\_application\>*.

        For example, to remove the authorized assertion consumer service entry for a Java application to which your subaccount in the US East region is subscribed, execute:

        ```
        neo  hcmcloud-disable-application-access --application <application_provider_subaccount>:<my_application> --application-type java --account <my_extension_subaccount> --user <my_email@example.com> --host us1.hana.ondemand.com
        ```



**Related Information**  


[hcmcloud-enable-application-access](../50-administration-and-ops-neo/hcmcloud-enable-application-access-da0e8ba.md "This command registers an extension application as an authorized assertion consumer service for the SAP SuccessFactors system associated with the specified subaccount to enable the application to use the SAP SuccessFactors identity provider (IdP) for authentication.")

[hcmcloud-disable-application-access](../50-administration-and-ops-neo/hcmcloud-disable-application-access-99e8674.md "This command removes an extension application from the list of authorized assertion consumer services for the SAP SuccessFactors system associated with the specified subaccount.")

[hcmcloud-display-application-access-status](../50-administration-and-ops-neo/hcmcloud-display-application-access-status-75eac93.md "This command displays the status of an extension application entry in the list of assertion consumer services for the SAP SuccessFactors system associated with the specified subaccount. The returned results contain the extension application URL.")

