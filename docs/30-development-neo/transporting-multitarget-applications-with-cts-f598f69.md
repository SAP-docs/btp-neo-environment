<!-- loiof598f69a9be347029b7e5e7205fc7d1f -->

# Transporting Multitarget Applications with CTS+

You can enable transport of SAP BTP applications and application content that is available as Multitarget Applications \(MTA\) using the Enhanced Change and Transport System \(CTS+\).



## Prerequisites

-   You have configured your SAP Business Technology Platform subaccounts for transport with CTS+ as described in [How To... Configure SAP BTP for CTS](http://help.sap.com/disclaimer?site=http://go.sap.com/documents/2016/07/bc3e9124-7d7c-0010-82c7-eda71af511fa.html).
-   The content that you want to transport can be made available as a Multitarget Application \(MTA\) archive as described in [Multitarget Applications for the Neo Environment](multitarget-applications-for-the-neo-environment-e1bb7eb.md).



## Context

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of the following technology portfolios: application development; process automation; integration; data, analytics, and enterprise planning; artificial intelligence. The platform offers users the ability to turn data into business value, compose end-to-end business processes, connect entire IT landscapes, and personalize, build and extend SAP applications. This reduces the overall total cost of ownership maintaining SAP landscapes and third-party software across end-to-end business processes.") :arrow_upper_right:.**

You use the Change and Transport System \(CTS\) of ABAP to transport and deploy your applications running on SAP Business Technology Platform in the form of MTAs, for example, from development to a test or production subaccount. Proceed as follows to be able to transport an SAP BTP application:



<a name="loiof598f69a9be347029b7e5e7205fc7d1f__steps_m5c_grg_1y"/>

## Procedure

1.  Package the application in a Multitarget Application \(MTA\) archive. To do this, you have the following options:

    1.  Use the [Cloud MTA Build Tool](https://github.com/SAP/cloud-mta-build-tool)
    2.  Use the Solution Export Wizard as described in [Exporting Solutions](exporting-solutions-14a0ff1.md)

2.  Attach the MTA archive to a CTS+ transport request as described in [How To... Configure SAP BTP for CTS](http://help.sap.com/disclaimer?site=http://go.sap.com/documents/2016/07/bc3e9124-7d7c-0010-82c7-eda71af511fa.html).

    If you use the Solution Export Wizard to package the MTA archive, you can configure it for direct export to CTS+ . This means that a CTS+ transport request is automatically created when the MTA is exported and the archive file is attached to the transport request. The transport request is released and put in the import queue of the follow-on subaccount. Additional configuration steps are necessary for this and are described in [Set Up a Direct Upload of MTA Archives to a CTS+ Transport Request](set-up-a-direct-upload-of-mta-archives-to-a-cts-transport-request-37ceecb.md).

3.  Trigger the import of an SAP BTP application as described in [How To... Configure SAP BTP for CTS](http://help.sap.com/disclaimer?site=http://go.sap.com/documents/2016/07/bc3e9124-7d7c-0010-82c7-eda71af511fa.html).


**Related Information**  


[Resources on CTS+](https://wiki.scn.sap.com/wiki/pages/viewpage.action?pageId=448469096)

[Setting up a CTS+ enabled transport landscape in SAP Business Technology Platform](https://blogs.sap.com/2017/03/29/setting-up-a-cts-enabled-transport-landscape-in-sap-cloud-platform/)

