<!-- loio4cbdab6e2eb14c92ab76540ffb32174c -->

# Maven Plugin

SAP offers a Maven plugin that supports you in using Maven to develop Java applications for SAP BTP. It allows you to conveniently call the SAP BTP console client and its commands from the Maven environment.

> ### Caution:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/docs/btp/sap-business-technology-platform/sap-business-technology-platform?version=Cloud) .**

> ### Tip:  
> Additional IP outbound addresses will soon be used in all regions in the Neo environment. For more information, see [Additional IP Addresses Added to SAP BTP, Neo Runtime Regions](https://help.sap.com/whats-new/cf0cb2cb149647329b5d02aa96303f56?version=Cloud&Component=Region&Valid_as_Of=2026-11-02:2026-11-02). To subscribe to such notifications, see SAP Note [3513325](https://me.sap.com/notes/3513325).

Most commands that are supported by the console client are available as goals in the plugin. To use the plugin, you require a SAP BTP SDK for Neo environment, which can be automatically downloaded with the plugin. Each version of the SDK always has a matching Maven plugin version.

