<!-- loiod2886a5dd7814888b1ebb98cec56130d -->

# Consume a Multitenant Connectivity Application



## Prerequisites

-   Your SAP BTP user is a member of a subaccount.
-   You are subscribed to a provider application, hosted by a provider subaccount. For more information, see [Multitenancy Roles](multitenancy-roles-48b552f.md) and [Providing Java Multitenant Applications to Tenants for Testing](../22-getting-started-neo/providing-java-multitenant-applications-to-tenants-for-testing-b093032.md).

> ### Note:  
> This tutorial assumes that your subaccount is subscribed to the following exemplary application \(deployed in a provider subaccount\): [Create a Multitenant Connectivity Application](create-a-multitenant-connectivity-application-d88900b.md)



## Context

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**

This tutorial explains how you can consume a sample connectivity application based on the multitenancy concept. That is, you are a member of a subaccount which is subscribed for applications provided by other subaccounts. The output of the application you are about to consume, displays a welcome page showing the URI of the tenant-specific destination configuration. This means that the administrator of your consumer subaccount may have been previously set a tenant-specific configuration for this application. However, in case such configuration has not been set, the application would use a default one, set by the administrator of the provider subaccount.

Users of a consumer subaccount, which is subscribed to an application, can access the application using a tenant-specific URL. This would lead the application to use a tenant-specific destination configuration. For more information, see [Multitenancy in the Connectivity Service](https://help.sap.com/viewer/b865ed651e414196b39f8922db2122c7/Cloud/en-US/b92140a0c6b942e1a0f72e9fd1133fd9.html "Using multitenancy for applications that require a connection to a remote service or on-premise application.") :arrow_upper_right:.

> ### Note:  
> As a consumer, you can set a tenant-specific destination configuration on **subscription** level.

 <a name="concept_rxt_4m1_pr"/>

<!-- concept\_rxt\_4m1\_pr -->

## Procedure



## 1. Define destination configuration

You can consume a provider application if your subaccount is subscribed to it. In this case, administrators of your consumer subaccount can configure a tenant-specific destination configuration, which can later be used by the provider application.

To illustrate the tenant-specific consumption, the URL used in this example is diferent from the one in the exemplary provider application tutorial.

**Example:**

```ini

Name=search_engine_destination
URL=http://www.yahoo.com
Type=HTTP
ProxyType=Internet
Authentication=NoAuthentication
TrustAll=true

```

> ### Tip:  
> The destination name depends on the provider application.
> 
> For more information on how to configure a destination for provider subaccount, see:
> 
>  [Configure Destinations from the Console Client](https://help.sap.com/viewer/b865ed651e414196b39f8922db2122c7/Cloud/en-US/e51558bbbb571014bfc89325eaf075c0.html "") :arrow_upper_right:.
> 
> [Configure Destinations from the Cockpit](https://help.sap.com/viewer/b865ed651e414196b39f8922db2122c7/Cloud/en-US/60735ad11d8a488c83537cdcfb257135.html "") :arrow_upper_right:



## 2. Access the application

Go to a browser and request the application on behalf of your subaccount. Use the following URL pattern:

 `https://<application_name><provider_subaccount>-<consumer_subaccount>.<host>/<application_path>` 



## Result

The application is requested in a browser. Its output is relevant to your tenant-specific destination configuration.

**Related Information**  


[Create a Multitenant Connectivity Application](create-a-multitenant-connectivity-application-d88900b.md)

[Configure Destinations from the Console Client](https://help.sap.com/viewer/b865ed651e414196b39f8922db2122c7/Cloud/en-US/e51558bbbb571014bfc89325eaf075c0.html "") :arrow_upper_right:

[Configure Destinations from the Eclipse IDE](https://help.sap.com/viewer/b865ed651e414196b39f8922db2122c7/Cloud/en-US/e520383cbb571014858bc5d52295f433.html "") :arrow_upper_right:

[Configure Destinations from the Cockpit](https://help.sap.com/viewer/b865ed651e414196b39f8922db2122c7/Cloud/en-US/60735ad11d8a488c83537cdcfb257135.html "") :arrow_upper_right:

