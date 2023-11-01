<!-- loiob0930320e5f946a3a47692be3cebb468 -->

# Providing Java Multitenant Applications to Tenants for Testing

Using the console client, you can create subaccounts and subscribe them to a provider application to test how applications can be provided to multiple consumers.



<a name="loiob0930320e5f946a3a47692be3cebb468__prereq_wfz_k1j_kz"/>

## Prerequisites

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**

-   Set up the console client. For more information, see [Set Up the Console Client](../30-development-neo/set-up-the-console-client-7613dee.md).
-   Develop and deploy an application that is used by multiple consumers. For more information, see [Developing Multitenant Applications in the Neo Environment](../30-development-neo/developing-multitenant-applications-in-the-neo-environment-54a7615.md).
-   You have an enterprise account. For more information, see [Global Accounts](../10-concepts-neo/account-model-722a475.md#loio9b7d44f92eec44a6ae87129c02aeec0d).

-   You are a member to both subaccounts: the one where the multitenant application is deployed and the one that you subscribe to the application.

<a name="task_v24_q1j_kz"/>

<!-- task\_v24\_q1j\_kz -->

## Subscribe Subaccounts to an Application

Using the console client, you can subscribe subaccounts to an application.



<a name="task_v24_q1j_kz__context_wny_x1j_kz"/>

## Context

> ### Note:  
> You can subscribe a subaccount to an application that is running in another subaccount only if both subaccounts \(provider and consumer subaccounts\) belong to the same region.



<a name="task_v24_q1j_kz__steps_kj3_dbj_gl"/>

## Procedure

1.  Open the command prompt and navigate to the folder containing `neo.bat/sh (<SDK installation folder>/tools)`.

2.  Create subaccounts for several consumers.

    To create a subaccount, execute `neo create-account -a <subaccount> -u <user name or email> -h <host> -n <display name of the new subaccount>`.

3.  Subscribe the subaccounts you have created to the provider application.

    For each created subaccount, execute `neo subscribe -a <subaccount> -b <subaccount name>:<application> -u <user name or email> -h <host>`.

    > ### Note:  
    > Specify the parameter `-b` in the format <subaccount name\>:<application\>.


<a name="task_qtj_rbj_kz"/>

<!-- task\_qtj\_rbj\_kz -->

## Test the Multitenant Application

Access the application through the different tenants and verify that the multitenant application works as configured for the respective subaccount \(tenant\).



<a name="task_qtj_rbj_kz__steps_vyj_tcj_kz"/>

## Procedure

1.  Access the application using the dedicated URL for each consumer subaccount in the format `https://<application name><provider subaccount>-<consumer subaccount>.<host>`.

    You see the list of subscriptions and the corresponding application URLs to access them in the *Subscriptions* pane in the cockpit.

2.  Change the configuration of the multitenant application for each consumer subaccount \(tenant\).

3.  Verify that the configuration of the provider application differs for each consumer subaccount \(tenant\).

4.  \(Optional\) You can also check the list of your test subaccounts and subscriptions as follows:


    <table>
    <tr>
    <th valign="top">

    Option
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    **List all applications to which a given subaccount is subscribed**
    
    </td>
    <td valign="top">
    
    Execute `neo list-subscribed-applications -a <subaccount> -u <user name or email> -h <host>`.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    **List subaccounts you have created**
    
    </td>
    <td valign="top">
    
    Execute `neo list-accounts -a <subaccount> -u <user name or email> -h <host>` .
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    **List all subaccounts subscribed to a given application**
    
    </td>
    <td valign="top">
    
    Execute `neo list-subscribed-accounts -a <subaccount> -b <application> -u <user name or email> -h <host>`.
    
    </td>
    </tr>
    </table>
    

<a name="loio69cf27df2dc74392bdf7a7b4310d31fd"/>

<!-- loio69cf27df2dc74392bdf7a7b4310d31fd -->

## Clean Up Your Environment



<a name="loio69cf27df2dc74392bdf7a7b4310d31fd__steps_rh2_kcj_gl"/>

## Procedure

1.  Unsubscribe each consumer subaccount from the application.

    For each consumer subaccount, execute `neo unsubscribe -a <subaccount> -b <application> -u <user name or email>` .

2.  Delete each consumer subaccount.

    For each consumer subaccount, execute `neo delete-account -a <subaccount> -h <host> -u <user name or email>` .


**Related Information**  


 <?sap-ot O2O class="- topic/link " href="cc4f1ceddacb4b16844fd3f3885b73dd.xml" text="" desc="" xtrc="link:1" xtrf="file:/home/builder/src/dita-all/jjq1673438782153/loio9fe952ba277c471bbad80cd40548bb84_en-US/src/content/localization/en-us/b0930320e5f946a3a47692be3cebb468.xml" ?> 

[create-account](../50-administration-and-ops-neo/create-account-05f96cf.md "Creates a new subaccount with an automatically generated unique ID as subaccount technical name and the specified display name and assigns the user as a subaccount owner. The user is authorized against the existing subaccount passed as --account parameter. Optionally, you can clone an existing subaccount configuration to save time and effort.")

[list-accounts](../50-administration-and-ops-neo/list-accounts-2abad16.md "Lists all subaccounts that a customer has. Authorization is performed against the subaccount passed as --account parameter.")

[subscribe](../50-administration-and-ops-neo/subscribe-4c6203d.md "Subscribes the subaccount of the consumer to a provider Java application. Once the command is executed successfully, the subscription is visible in the Subscriptions panel of the cockpit in the consumer subaccount.")

[list-subscribed-accounts](../50-administration-and-ops-neo/list-subscribed-accounts-034244c.md "Lists all subaccounts subscribed to a given Java application.")

[list-subscribed-applications](../50-administration-and-ops-neo/list-subscribed-applications-67d5c6f.md "Lists all Java applications to which a given subaccount is subscribed.")

[delete-account](../50-administration-and-ops-neo/delete-account-8bd9552.md "Deletes a particular subaccount. Only the user who has created the subaccount is allowed to delete it.")

[unsubscribe](../50-administration-and-ops-neo/unsubscribe-862d00e.md "Removes the subscription to a provider Java application from a consumer subaccount.")

