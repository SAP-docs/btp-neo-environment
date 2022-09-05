<!-- loio22bda078a05b4ec99c89df5fba8fc5ca -->

# Configure the SAP SuccessFactors Role Provider

If you have a Java extension application, you can change the default SAP BTP role provider to the SAP SuccessFactors role provider.



## Prerequisites

-   You have an SAP BTP extension subaccount and the corresponding SAP SuccessFactors customer instance connected to it. For more information about extension subaccounts, see [Extensions](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/08b1effc53634890a525f945017e2edc.html).
-   You are either an administrator of the subaccount or have a platform role with the following platform scopes defined for it:
-   You have a Java extension application.



## Context

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**

A role provider is the component that retrieves the roles for a particular user. By default, the role provider used for SAP BTP applications and services is the SAP BTP role provider. For Java extension applications, however, you can change the default role provider to the SAP SuccessFactors role provider. Depending on whether the application is running in your subaccount or your subaccount is subscribed to the extension application, you configure the role provider from either the *Roles* section for your application, or the *Subscription* section for your subaccount. In addition, you can view the role provider for each enabled SAP BTP service in the *Services* section of the SAP BTP cockpit.

Alternatively, you can use the `hcmcloud-enable-role-provider` console client command. For more information, see [hcmcloud-enable-role-provider](../50-administration-and-ops-neo/hcmcloud-enable-role-provider-e263f8e.md).

> ### Note:  
> Currently, the automated change of the role provider is available only for Java extension applications for SAP SuccessFactors.



<a name="loio22bda078a05b4ec99c89df5fba8fc5ca__steps_gsd_4gk_jq"/>

## Procedure

1.  In the SAP BTP cockpit, navigate to the application for which you want to change the role provider. To do so, proceed as follows:

    -   For a Java application running in your subaccount, choose *Applications* \> *Java Applications*, and then choose the link of the application.
    -   For a Java application to which your subaccount is subscribed, choose *Applications* \> *Subscriptions*, and then choose the link of the application.

2.  Choose *Security* \> *Roles*.

3.  In the *Role Provider* panel, select the required role provider from the *Provider* dropdown box.

4.  \(Optional\) To view the role provider for an SAP BTP service, in the cockpit navigate to *Services* \> **<service\_name\>**, and then choose *Configure Roles*.

    The system displays the role provider in the *Role Provider* panel in a read-only mode.

    > ### Note:  
    > For an extension subaccount, the role provider for SAP Cloud Portal service is *SAP SuccessFactors*.




## Results

The changes take effect after 5 minutes. If you want the changes to take effect immediately, you restart the application \(valid only for applications running in your subaccount\).

**Related Information**  


[hcmcloud-enable-role-provider](../50-administration-and-ops-neo/hcmcloud-enable-role-provider-e263f8e.md "This command enables the SAP SuccessFactors role provider for the specified Java application.")

