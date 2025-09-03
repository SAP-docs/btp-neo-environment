<!-- loio14a0ff1480494bcd993674061fb4f505 -->

# Exporting Solutions



<a name="loio14a0ff1480494bcd993674061fb4f505__prereq_b3f_ghq_m2b"/>

## Prerequisites

-   You have deployed or created the application components, configurations, and content that you want to export as an MTA in an SAP BTP Neo subaccount.
-   Optionally, you have configured the connectivity to a transport service such as CTS+ and the Transport Management Service.



<a name="loio14a0ff1480494bcd993674061fb4f505__context_s5v_4pp_m2b"/>

## Context

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/docs/btp/sap-business-technology-platform/sap-business-technology-platform?version=Cloud) .**

You have the option to export subaccount components as Solutions. You have two possible scenarios:

-   you can generate MTA development descriptor, MTA deployment descriptor template, and MTA extension descriptor template
-   you can export an MTA archive and, optionally, upload it to a transport service such as CTS+ or the Transport Management Service

    > ### Remember:  
    > Exporting MTA archives containing Java modules is not supported. You can, however, export descriptor files that contain information about a Java software module.


The following components are supported:

-   Java applications, including application destinations, data-source bindings, and role group assignments
-   HTML5 applications, including permission role assignments
-   Subaccount destinations
-   HTML5 roles
-   Cloud Portal sites
-   Cloud Portal roles
-   Cloud Portal destinations
-   OData Provisioning service configurations
-   OData Provisioning destinations
-   Security groups
-   Cloud Integration content packages

> ### Note:  
> If a destination leads to a Java application and both are chosen for export, the destination `url` parameter is automatically replaced with a placeholder leading to the Java application `default-url`.

Proceed as follows:



<a name="loio14a0ff1480494bcd993674061fb4f505__steps_e4y_vpp_m2b"/>

## Procedure

1.  Log on to the cockpit, select a subaccount, and choose *Solutions* in the navigation area.

2.  Choose *Export*. Wait until the subaccount components are discovered.

3.  Choose the subaccont-level components that you want to export from the list. You can also use the search field to locate components by name. Afterward, choose *Next*.

    -   The option *Automatically select dependent components* is enabled by default, so that any related components and configurations are automatically selected for you. Disable this option if you want to choose components individually.
    -   The checkbox for selecting all components operates only for visible items. If you want to select all discovered items, first expand the full list by choosing *More* at the bottom of the list.

4.  Deselect the subcomponents that you do not want to export. Afterward, choose *Next*.

5.  Fill out the solution information. It is mandatory to enter a solution ID and a solution version. Afterward, choose *Export*.

6.  Optionally, you can change the export options:

    -   If you leave the default settings, upon export you are presented with download links for the MTA descriptors.
    -   Your can export an MTA archive to CTS+ or the Transport Management Service. For more information the required setup, see [Integration with Transport Management Tools](integration-with-transport-management-tools-905baea.md). If you choose to export the MTA archive to CTS+, you can use either the TransportSystemCTS destination user or the current user to resolve the CTS+ transport request to be used.

7.  Choose *Export*. As a result, you are presented with download links for the MTA development descriptor template, MTA deployment descriptor, MTA extension descriptor template, and the MTA archive. Alternatively, if in the previous step you selected the CTS+ direct export or the Transport Management Service options, the solution is also exported for usage in that system.

    > ### Tip:  
    > You can use the MTA development descriptor template in combination with the MTA archive builder tool to create your MTA archive. The template contains `build-parameters` and `path` sections with all possible build options for the corresponding module type. Note that for your particular build environment you need to manually remove unnecessary parameters. For more information, see [Cloud MTA Build Tool - Configuration](https://sap.github.io/cloud-mta-build-tool/configuration/).


**Related Information**  


[Operating Solutions](operating-solutions-2abf7d4.md "You can deploy, update, monitor, and delete a solution.")

[Integration with Transport Management Tools](integration-with-transport-management-tools-905baea.md)

[Cloud MTA Build Tool](https://sap.github.io/cloud-mta-build-tool/)

