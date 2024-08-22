<!-- loio8eaaffc96a4b4a059c9713ef40f7981c -->

# Prerequisites for Using the End-To-End Trace Analysis

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of the following technology portfolios: application development; process automation; integration; data, analytics, and enterprise planning; artificial intelligence. The platform offers users the ability to turn data into business value, compose end-to-end business processes, connect entire IT landscapes, and personalize, build and extend SAP applications. This reduces the overall total cost of ownership maintaining SAP landscapes and third-party software across end-to-end business processes.") :arrow_upper_right:.**





### Configuring Connections for Collecting Statistical Data for SAP BTP

You need to configure the connection to the SAP BTP for retrieving the statistical data. Proceed as follows, depending on the tool you use:

-   Define the API service access point as described in [Configuration](https://support.sap.com/en/solution-manager/sap-solution-manager-7-2/expert-portal/applications/hybrid-operations/public-cloud-operations/sap-cloud-platform.html#section_2067386612).
-   Enable the automatic trace upload as described in [Tracing Capabilities](https://support.sap.com/en/solution-manager/sap-solution-manager-7-2/expert-portal/applications/hybrid-operations/public-cloud-operations/sap-cloud-platform.html#section_8181016).



### Configuring connections for collecting statistical data for ABAP Systems

You need to configure а connection to your ABAP system for retrieving the statistical data. Proceed as follows, depending on the tool you use:

-   for SAP Solution Manager 7.2 SP06 and higher - see [Managing Technical System Information](https://help.sap.com/viewer/c413647f87a54db59d18cb074ce3dafd/7.2.06/en-US/0e08c84de63e43ec938a92be699931f8.html) and [Executing the Configuration Scenarios](https://help.sap.com/viewer/c413647f87a54db59d18cb074ce3dafd/7.2.06/en-US/235dfd9cdc004f878f51940178e3b472.html).
-   for Focused Run for SAP Solution Manager \(FRUN\) - see [Managed Systems Preparation & Maintenance Guides](https://support.sap.com/en/solution-manager/focused-solutions/focused-run-expert-portal/managed-systems-maintenance-guide.html) and [Preparing Managed Systems - SAP NetWeaver Application Server ABAP](https://support.sap.com/en/solution-manager/focused-solutions/focused-run-expert-portal/managed-systems-maintenance-guide/preparing-managed-systems.html#section_607433417).



### Runtime requirements for SAP BTP

Requests passing through SAP BTP require `SAP-PASSPORT` as the HTTP header. For more information, see [Approving HTTP Headers](../30-development-neo/approving-http-headers-df89d9c.md). When you start your tracing from an HTML5 application, then the `SAP-PASSPORT` is generated and injected automatically for you.

