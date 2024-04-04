<!-- loio277c2c6a03ca4dc993a9139119947ac5 -->

# Configuring Platform Identity Provider \[Feature Set B\]

Use the procedures below to configure an Identity Authentication tenant as platform identity provider in your Neo subaccount in Feature Set B.

The platform identity provider you configure will be used for accessing service and platform tools, such as:

-   [Console Client for the Neo Environment](../50-administration-and-ops-neo/console-client-for-the-neo-environment-7613230.md)
-   [Git Service](https://help.sap.com/docs/git-service?version=Cloud)
-   [Cloud Connector \(Neo environment\)](https://help.sap.com/docs/connectivity/sap-btp-connectivity-neo/cloud-connector-neo-environment?version=Cloud)
-   [SAP Solutions Management Service for SAP BTP](https://help.sap.com/docs/solutions-lifecycle-management) when BASIC authentication is used in applications
-   SAP HANA system from SAP HANA Studio \(see [Tutorial: Add an SAP HANA System](https://help.sap.com/docs/SAP_HANA_PLATFORM/52715f71adba4aaeb480d946c742d1f6/abedb1c22b0746a8a44a38b810c99b58.html)\)

> ### Note:  
> This platform identity provider is *not* used for accessing the SAP BTP cockpit. For accessing the SAP BTP cockpit, you use the custom identity provider configured at *global account level*. For more information, see [Establish Trust and Federation of Custom Identity Providers for Platform Users \[Feature Set B\]](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/c36898473d704e07a33268c9f9d29515.html "You want to use a custom identity provider for the platform users of SAP BTP in different environments and at the different account levels: global account, directory, and subaccount. By default, platform users in multi-environment subaccounts are users in the default identity provider.") :arrow_upper_right:.

<a name="task_tvg_cwc_lxb"/>

<!-- task\_tvg\_cwc\_lxb -->

## Prerequisite: Configure Trust at Global Account Level



<a name="task_tvg_cwc_lxb__context_ncv_dwc_lxb"/>

## Context

To configure an Identity Authentication tenant as a platform identity provider for you Neo subaccount, you need to have a trust configuration at *global account level* with it. For more inormation, see [Establish Trust and Federation of Custom Identity Providers for Platform Users \[Feature Set B\]](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/c36898473d704e07a33268c9f9d29515.html "You want to use a custom identity provider for the platform users of SAP BTP in different environments and at the different account levels: global account, directory, and subaccount. By default, platform users in multi-environment subaccounts are users in the default identity provider.") :arrow_upper_right:.

> ### Note:  
> When you configure trust at global account level, the trusted Identity Authentication tenant creates an application with the name *SAP Business Technology Platform*. All security settings in this application apply to *all Neo subaccounts*.

<a name="task_o2r_svc_lxb"/>

<!-- task\_o2r\_svc\_lxb -->

## Configure the Platform Identity Provider at Neo Subaccount Level



<a name="task_o2r_svc_lxb__steps_pjc_1wc_lxb"/>

## Procedure

1.  In your web browser, open the SAP BTP cockpit, and navigate to your Neo subaccount.

    See [Navigate in the Cockpit](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/0874895f1f78459f9517da55a11ffebd.html "Learn how to navigate to your global accounts and subaccounts in the SAP BTP cockpit.") :arrow_upper_right:.

2.  Go to *Security* \> *Trust* \> *Platform Identity Provider for Tools*.

    The screen shows the platform identity provider in use. By default, this is SAP ID Service.

3.  Choose the *Select Identity Authentication Tenant* button.

    A list of all tenants available for your current Neo subaccount appears.

4.  Select the required tenant from the list.

    The screen now shows the Identity Authentication tenant as the platform identity provider in use. You can switch back to SAP ID Service \(using the respective button\) or change to another tenant \(if available\).


