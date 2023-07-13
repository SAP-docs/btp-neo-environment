<!-- loioebb281b1246d4ca18a363682eff3475d -->

# Configure the Extension Application's Connectivity to SAP SuccessFactors

Use this procedure to configure the connectivity between your Java or HTML5 extension application and the SAP SuccessFactors system associated with your SAP BTP extension subaccount.



## Prerequisites

-   You have an SAP BTP extension subaccount and the corresponding SAP SuccessFactors customer instance connected to it.
-   You are either an administrator of the subaccount or have a platform role with the following platform scopes defined for it:
    -   readExtensionIntegration

    -   manageExtensionIntegration

    -   manageDestinations


-   You have downloaded and set up the console client for SAP BTP, Neo environment. For more information, see [Console Client for the Neo Environment](../50-administration-and-ops-neo/console-client-for-the-neo-environment-7613230.md).




## Context

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**

The extension applications interact with the extended SAP SuccessFactors system using the HXM Suite OData API. The HXM Suite OData API is a RESTful API based on the OData protocol intended to enable access to data in the SAP SuccessFactors system. You can benefit from the following the following API access scenarios:

-   OData access with SAML2BearerAssertion authentication

    This scenario is used for performing OData API calls with logged-in user propagation, thus enforcing permission checks for accessing objects. For this scenario, you require a `sap_hcmcloud_core_odata` destination.

-   OData access with SAML2BearerAssertion authentication and a technical user

    This scenario is used for performing OData API calls with a predefined technical user when the extension application is performing scheduled jobs or data replication. For this scenario you require a `sap_hcmcloud_core_odata_technical_user` destination.


To enable the API access and configure the connectivity between the Java or HTML5 extension applications and the SAP SuccessFactors system associated with your extension subaccount, you use the `hcmcloud-create-connection` console client command. Using the command, you specify the connection details for the remote communication of the extension application and create the HTTP destinations required for configuring the API access. The command also creates and configures the corresponding OAuth clients in the SAP SuccessFactors company instance.

You can consume this destination in your application using one of these APIs:

-   [HttpDestination API and DestinationFactory](https://help.sap.com/viewer/cca91383641e40ffbe03bdc78f00f681/Cloud/en-US/462dbffef4614044b5c727c9de37672e.html)

-   [ConnectivityConfiguration API](https://help.sap.com/viewer/cca91383641e40ffbe03bdc78f00f681/Cloud/en-US/4da3b13c88ce4220bbd56a4361799668.html)

-   [AuthenticationHeaderProvider API](https://help.sap.com/viewer/cca91383641e40ffbe03bdc78f00f681/Cloud/en-US/df6c1ffd39f0451594d737cf7638ce00.html)


> ### Note:  
> As of August 2019, we have introduced the `skipUserAttributesResolution` destination property which improves the performance. If you want to enable the property for connections created before the property has been introduced, you can do one of the following:
> 
> -   Refresh the extension integration. For more information, see [Refresh the Extension Integration for SAP SuccessFactors](refresh-the-extension-integration-for-sap-successfactors-9d3f809.md).
> 
> -   For the connection for which you want to enable the `skipUserAttributesResolution` property, execute the `hcmcloud-create-connection` command with the `--overwrite` parameter specified. For more information, see: [hcmcloud-create-connection](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/ba4e8bbf0ec4409fae7064bcbbe07e49.html).
> 
> -   Edit the destination and add the `skipUserAttributesResolution` property manually and set its value to `true`. For more information, see: [Managing Destinations](https://help.sap.com/viewer/cca91383641e40ffbe03bdc78f00f681/Cloud/en-US/e4f1d97cbb571014a247d10f9f9a685d.html).

You have the following options for configuring the connectivity:

-   \(Relevant for Java applications only\) If you have an extension application deployed in your subaccount, you can configure the connectivity on an application level in the subaccount where the application is deployed.

-   \(Relevant for Java applications only\) If your subaccount is subscribed to an extension application, you can configure the connectivity on a subscription level in the subaccount subscribed to the application.
-   If you want to create a connection that can be used by all the extension applications that are deployed in your subaccount or that your subaccount is subscribed to, you configure the connectivity on a subaccount level.

    > ### Note:  
    > If you have an HTML5 extension application, use this option.


You can optionally list the connections created for the extension application. You can also delete a connection.



<a name="loioebb281b1246d4ca18a363682eff3475d__steps_r21_t4z_tn"/>

## Procedure

1.  To start the console client for SAP BTP, Neo environment, open the command prompt and navigate to the folder containing neo.bat/sh \(SDK installation folder/tools\). For more information, see [Using the Console Client](../50-administration-and-ops-neo/using-the-console-client-8900b22.md).

2.  To configure the connectivity, in the console client command line, execute the `hcmcloud-create-connection` command, as described in [hcmcloud-create-connection](../50-administration-and-ops-neo/hcmcloud-create-connection-ba4e8bb.md).

3.  \(Optional\) To list the connections created for the extension application, in the console client command line, execute `hcmcloud-list-connections`, as described in [hcmcloud-list-connections](../50-administration-and-ops-neo/hcmcloud-list-connections-38f9af2.md).

    -   For an application deployed in your subaccount, specify the name of your extension application for the `application` parameter.

    -   For an application to which your subaccount is subscribed, specify the application provider subaccount and the name of your extension application for the `application` parameter in the following format: *<app\_provider\_subaccount\>*:*<my\_app\>*.

    -   For a subaccount level connectivity, do not use the `application` parameter.


4.  \(Optional\) If your scenario requires it, remove the connectivity configured between your extension application and the SAP SuccessFactors systems associated with the extension subaccount. In the console client command line, execute `hcmcloud-delete-connection`, as described in [hcmcloud-delete-connection](../50-administration-and-ops-neo/hcmcloud-delete-connection-1445cb5.md).

    -   For an application deployed in your subaccount, specify the name of your extension application for the `application` parameter.

    -   For an application to which your subaccount is subscribed, specify the application provider subaccount and the name of your extension application for the `application` parameter in the following format: *<app\_provider\_subaccount\>*:*<my\_app\>*.

    -   For a subaccount level connectivity, do not use the `application` parameter.



**Related Information**  


[hcmcloud-delete-connection](../50-administration-and-ops-neo/hcmcloud-delete-connection-1445cb5.md "This command removes the specified connection configured between an extension application and a SAP SuccessFactors system associated with the specified subaccount in the Neo environment, or between a specified subaccount in the Neo environment and the SAP SuccessFactors system associated with it.")

[hcmcloud-create-connection](../50-administration-and-ops-neo/hcmcloud-create-connection-ba4e8bb.md "Use this command to configure the connectivity of an extension application to an SAP SuccessFactors system associated with a specified subaccount in the Neo environment, or to configure the connectivity of a specified subaccount in the Neo environment to an SAP SuccessFactors system associated with this subaccount. The command creates the required HTTP destination and registers an OAuth client for the extension application in SAP SuccessFactors.")

[hcmcloud-list-connections](../50-administration-and-ops-neo/hcmcloud-list-connections-38f9af2.md "This command lists the connections configured for a specified extension application or for a specified subaccount.")

