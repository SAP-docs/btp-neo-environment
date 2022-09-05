<!-- loiod5b6a7dde542493b861ad95fb73e18d9 -->

# Configure Integration Based on OAuth 2.0 Client Credentials

Use this procedure to enable your extension application to consume events defined in the SAP SuccessFactors system based on OAuth 2.0 client credentials grant.



<a name="loiod5b6a7dde542493b861ad95fb73e18d9__prereq_o5z_qhf_bhb"/>

## Prerequisites

-   You have an OAuth-protected extension application deployed in SAP BTP.

-   You have specific Role-based permissions to use Intelligent Services Center. See [Intelligent Services Center](https://help.sap.com/viewer/08bcf861c3c84717bfef7621713f55af/LATEST/en-US/2a4a45d56b7e405181d872686bd7f7d1.html).

-   You need to have specific Role-based permissions to use Integration Center. See [Role-based Permissions for Integration Center](https://help.sap.com/viewer/60ba370328e0485797adde67aee846a0/LATEST/en-US/f681601ef30447719438fe9f00fdf14e.html).




## Context

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**

This integration flow enables grant of an OAuth access token based on the client credentials only, without user interaction.

Follow these steps to subscribe an extension application to receive notifications from an SAP SuccessFactors event of your choice:

> ### Note:  
> Alternatively, in the Neo environment, you can perform **step 1** and **step 2** automatically, by configuring the `sfsf-outbound-connections` parameter in the Java application module of your Multi-Target Application \(MTA\) deployment descriptor. See [MTA Module Types, Resource Types, and Parameters for Applications in the Neo Environment](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/f1caa871360c40e7be7ce4264ab9c336.html).



## Procedure

1.  [Create OAuth Client in SAP BTP](create-oauth-client-in-sap-btp-67f43e2.md).

2.  [Create Outbound OAuth Configuration in SAP SuccessFactors](create-outbound-oauth-configuration-in-sap-successfactors-c9546f4.md).

3.  [Create a New Integration](create-a-new-integration-3abd9ce.md).


