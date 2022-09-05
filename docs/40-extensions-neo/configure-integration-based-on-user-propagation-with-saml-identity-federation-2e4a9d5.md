<!-- loio2e4a9d5318b046d5b1a7258ccc43cf74 -->

# Configure Integration Based on User Propagation with SAML Identity Federation

Use this procedure to enable your extension application to consume events defined in the SAP SuccessFactors system based on user propagation with SAML identity federation.



<a name="loio2e4a9d5318b046d5b1a7258ccc43cf74__prereq_jgz_3kz_2cb"/>

## Prerequisites

-   You have an extension application deployed in SAP BTP.

-   You have specific Role-based permissions to use Intelligent Services Center. See [Intelligent Services Center](https://help.sap.com/viewer/08bcf861c3c84717bfef7621713f55af/LATEST/en-US/2a4a45d56b7e405181d872686bd7f7d1.html).

-   You need to have specific Role-based permissions to use Integration Center. See [Role-based Permissions for Integration Center](https://help.sap.com/viewer/60ba370328e0485797adde67aee846a0/LATEST/en-US/f681601ef30447719438fe9f00fdf14e.html).




## Context

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**

This integration flow is based on exchanging the SAML \(bearer\) assertion from the SAP SuccessFactors identity provider for an OAuth access token from the SAP BTP authorization server. Using the access token, SAP SuccessFactors can access the OAuth-protected application.

You can integrate the extension application to subscribe to an event defined in the SAP SuccessFactors system. For example, if you want your extension application to be notified when a job title of an employee has been changed, you have to use the *Change in Job Title* event.

Follow these steps to subscribe an extension application to receive notifications from an SAP SuccessFactors event of your choice:

> ### Note:  
> Alternatively, in the Neo environment, you can perform **step 1** to **step 4** automatically, by configuring the `sfsf-outbound-connections` parameter in the Java application module of your Multi-Target Application \(MTA\) deployment descriptor. See [MTA Module Types, Resource Types, and Parameters for Applications in the Neo Environment](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/f1caa871360c40e7be7ce4264ab9c336.html).



## Procedure

1.  [Generate OAuth X509 Key in SAP SuccessFactors](generate-oauth-x509-key-in-sap-successfactors-f636503.md)

2.  [Create OAuth Client in SAP BTP](create-oauth-client-in-sap-btp-67f43e2.md)

3.  [Create Trusted Identity Provider in SAP BTP Cockpit](create-trusted-identity-provider-in-sap-btp-cockpit-83e5ad2.md)

4.  [Create Outbound OAuth Configuration in SAP SuccessFactors](create-outbound-oauth-configuration-in-sap-successfactors-2fcdea4.md)

5.  [Create a New Integration](create-a-new-integration-3abd9ce.md)


