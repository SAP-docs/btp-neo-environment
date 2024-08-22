<!-- loioe7e62c88b0184307af165a7d9323aa2e -->

# Subscribe to Java Multitenant Applications in the Neo Environment

Create, list, and remove subscriptions for a Java application using the console client and view all our subscriptions in the cockpit.



<a name="loioe7e62c88b0184307af165a7d9323aa2e__prereq_qjz_bwr_3cb"/>

## Prerequisites

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of the following technology portfolios: application development; process automation; integration; data, analytics, and enterprise planning; artificial intelligence. The platform offers users the ability to turn data into business value, compose end-to-end business processes, connect entire IT landscapes, and personalize, build and extend SAP applications. This reduces the overall total cost of ownership maintaining SAP landscapes and third-party software across end-to-end business processes.") :arrow_upper_right:.**

-   An enterprise account. For more information, see [Global Accounts](../10-concepts-neo/account-model-722a475.md#loio9b7d44f92eec44a6ae87129c02aeec0d).
-   Develop and deploy an application in the Neo environment for multiple consumers. For more information, see [Developing Multitenant Applications in the Neo Environment](../30-development-neo/developing-multitenant-applications-in-the-neo-environment-54a7615.md).
-   Provider and consumer subaccounts that belong to the same region. For more information, see [Regions and Hosts Available for the Neo Environment](../10-concepts-neo/regions-and-hosts-available-for-the-neo-environment-d722f7c.md).
-   If applicable, purchase SaaS licenses for the applications you want to consume.Set up the console client. For more information, see [Set Up the Console Client](../30-development-neo/set-up-the-console-client-7613dee.md).

<a name="task_hcj_fch_1y"/>

<!-- task\_hcj\_fch\_1y -->

## Create Java Subscriptions

To create Java subscriptions, use the `subscribe` command.

> ### Example:  
> ```
> neo subscribe --account consumersubaccount --application mysubaccount:myapp --user myuser --host us1.hana.ondemand.com
> ```

<a name="task_czx_vbh_1y"/>

<!-- task\_czx\_vbh\_1y -->

## List Java Subscription in the Console Client

-   To list all Java applications subscribed to a subaccount, use the `list-subscribed-applications` command.

    > ### Example:  
    > ```
    > neo list-subscribed-applications --account consumersubaccount --user myuser --host hana.ondemand.com
    > ```

-   To list all subaccounts subscribed to a Java application, use the `list-subscribed-accounts` command.

    > ### Example:  
    > ```
    > neo list-subscribed-accounts --account mysubaccount --application demo --user myuser --host us1.hana.ondemand.com
    > ```


<a name="task_o3s_dgd_by"/>

<!-- task\_o3s\_dgd\_by -->

## View Java Subscriptions in the Cockpit



<a name="task_o3s_dgd_by__steps_bc5_ggd_by"/>

## Procedure

1.  Open the subaccount in the cockpit.

2.  In the navigation area, choose *Applications* \> *Subscriptions*.

    You see a list of subscriptions to Java applications, with the provider subaccount from which the subscription was obtained and the subscribed application.

3.  To navigate to the subscription overview, choose the application name. You have the following options:

    -   To launch an application, choose the link in the *Application URLs* panel.

    -   To create connectivity destinations, choose *Destinations* in the navigation area.

    -   To create or assign roles, choose *Roles* in the navigation area.



<a name="task_g22_z2h_1y"/>

<!-- task\_g22\_z2h\_1y -->

## Remove Java Subscriptions

> ### Note:  
> Some subscriptions automatically created by the platform cannot be removed.

To remove Java subscriptions, use the `unsubscribe` command.

> ### Example:  
> ```
> neo unsubscribe --account consumersubaccount --application mysubaccount:myapp --user myuser --host us1.hana.ondemand.com
> ```

**Related Information**  


[Subscribe to HTML5 Multitenant Applications in the Neo Environment](subscribe-to-html5-multitenant-applications-in-the-neo-environment-f16cd5b.md "Manage subscriptions to HTML5 applications by viewing, creating, or removing subscriptions in the cockpit.")

[list-subscribed-applications](../50-administration-and-ops-neo/list-subscribed-applications-67d5c6f.md "Lists all Java applications to which a given subaccount is subscribed.")

[list-subscribed-accounts](../50-administration-and-ops-neo/list-subscribed-accounts-034244c.md "Lists all subaccounts subscribed to a given Java application.")

[subscribe](../50-administration-and-ops-neo/subscribe-4c6203d.md "Subscribes the subaccount of the consumer to a provider Java application. Once the command is executed successfully, the subscription is visible in the Subscriptions panel of the cockpit in the consumer subaccount.")

[unsubscribe](../50-administration-and-ops-neo/unsubscribe-862d00e.md "Removes the subscription to a provider Java application from a consumer subaccount.")

