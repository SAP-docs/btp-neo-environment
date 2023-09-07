<!-- loioa32d3d532e2d4dceaaca4ebab68df037 -->

# Using Services in the Neo Environment

Learn more about using services in the Neo environment:

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**

-   [About Services in the Neo Environment](using-services-in-the-neo-environment-a32d3d5.md#loiob8bbace90f5840e8a164c41e62ff2677)
-   [Enable Services in the Neo Environment](using-services-in-the-neo-environment-a32d3d5.md#loio4e12009d06e44eb1943b94483a505d90)
-   [Disable Services in the Neo Environment](using-services-in-the-neo-environment-a32d3d5.md#loiobb93d85070b14ac280f57fbee6044a73)

<a name="loiob8bbace90f5840e8a164c41e62ff2677"/>

<!-- loiob8bbace90f5840e8a164c41e62ff2677 -->

## About Services in the Neo Environment

In the Neo environment, you enable services in the SAP BTP cockpit.

The cockpit lists all services grouped by service category. Some of the services are basic services, which are provided with SAP BTP and are ready-to-use. In addition, extended services are available. A label on the tile for a service indicates if this service is enabled.

An administrator must first enable the service and apply the service-specific configuration \(for example, configure the corresponding roles and destinations\) before any subaccount members can use it.

> ### Note:  
> Some services are exposed only for trial accounts. That means the services are not, or not yet, released for use with a customer or partner account.
> 
> Some services are exposed only if your organization has purchased a license.

The *Service Description* section offers the following:

-   A short description for the selected service

-   \(Optional\) Links to documentation for the selected service

-   \(Optional\) A link to the service UI. Some services provide a UI while others are consumable only via API.


The *Service Configuration* section offers the following:

-   \(Optional\) Links to configuration screens of the service.


> ### Remember:  
> You can access most of the links only after the service has been enabled.

The configuration options for a service may look like in this example for the Portal service:

-   To configure connection parameters to other systems \(by creating connectivity destinations\), choose *Configure *<Portal Service\>** \> *Destinations*.

    This option is available only if the service is enabled.

-   To create custom roles and assign custom or predefined roles to individual users and groups, choose *Configure *<Portal Service\>** \> *Roles*.

    This option is available only if the service is enabled.


<a name="loio4e12009d06e44eb1943b94483a505d90"/>

<!-- loio4e12009d06e44eb1943b94483a505d90 -->

## Enable Services in the Neo Environment

In the Neo environment, you might need to enable services before subaccount members can integrate them with applications. Note that free services are always enabled.



<a name="loio4e12009d06e44eb1943b94483a505d90__prereq_n42_rbg_2cb"/>

## Prerequisites

The Administrator role for the subaccount.



## Context



<a name="loio4e12009d06e44eb1943b94483a505d90__steps_bcp_jcg_2cb"/>

## Procedure

1.  Navigate to the subaccount in which you'd like to enable a service. For more information, see [Navigate in the Cockpit](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/0874895f1f78459f9517da55a11ffebd.html "Learn how to navigate to your global accounts and subaccounts in the SAP BTP cockpit.") :arrow_upper_right:.

2.  In the navigation area, choose *Services*.

3.  Select the service and choose *Enable*.


<a name="loiobb93d85070b14ac280f57fbee6044a73"/>

<!-- loiobb93d85070b14ac280f57fbee6044a73 -->

## Disable Services in the Neo Environment

In the Neo environment, you might need to disable services so that they are not available to subaccount members.



<a name="loiobb93d85070b14ac280f57fbee6044a73__prereq_n42_rbg_2cb"/>

## Prerequisites

The Administrator role for the subaccount.



## Context



<a name="loiobb93d85070b14ac280f57fbee6044a73__steps_bcp_jcg_2cb"/>

## Procedure

1.  Navigate to the subaccount in which you'd like to disable a service. For more information, see [Navigate in the Cockpit](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/0874895f1f78459f9517da55a11ffebd.html "Learn how to navigate to your global accounts and subaccounts in the SAP BTP cockpit.") :arrow_upper_right:.

2.  In the navigation area, choose *Services*.

3.  Select the service and choose *Disable*.

    All data generated by the service is deleted and cannot be retrieved.

    > ### Note:  
    > -   If other services use the service, they may be negatively impacted when you disable it. Your service documentation may provide information about services that are dependent on your service.
    > -   Services in the Neo environment generally have a delay period before they can be reenabled in the subaccount. In these cases, the confirmation message displays the number of hours before you can reenable the service.
    > -   The services enabled by default in the Neo environment cannot be disabled. Such services do not cause performance impact as long as they are not used.
    > -   If the *Disable* button is dimmed, it means that you'll not be able to disable it yourself. You'll need to report an incident to SAP Support to assist you with disabling the service.


