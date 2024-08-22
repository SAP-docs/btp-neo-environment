<!-- loiod3df5b457d0c43fca117da0dc14e2f0d -->

# Identity Authentication Tenant as an Application Identity Provider

You can register a tenant for Identity Authentication service as an identity provider for your subaccount.



## Prerequisites

-   You have defined service provider settings for the SAP BTP subaccount. See [Configure the Local Service Provider](application-identity-provider-dc61853.md#loiodcdfe339f94947bc96508daa686cc56d).
-   You have chosen a custom local provider configuration type for this subaccount \(using *Cockpit* \> *Trust* \> *Local Service Provider* \> *Configuration Type* \> *Custom*\)



## Context

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of the following technology portfolios: application development; process automation; integration; data, analytics, and enterprise planning; artificial intelligence. The platform offers users the ability to turn data into business value, compose end-to-end business processes, connect entire IT landscapes, and personalize, build and extend SAP applications. This reduces the overall total cost of ownership maintaining SAP landscapes and third-party software across end-to-end business processes.") :arrow_upper_right:.**

Identity Authentication service provides identity management for SAP BTP applications. You can register a tenant for Identity Authentication service as an identity provider for the applications in your SAP BTP subaccount.

> ### Note:  
> If you add a tenant for Identity Authentication service already configured for trust with the same service provider name, the existing trust configuration on the tenant for Identity Authentication service side will be updated. If you add a tenant for Identity Authentication configured for trust with SAP BTP with a different service provider name, a new trust configuration will be created on the tenant for Identity Authentication service side.

> ### Note:  
> When you remove a tenant for Identity Authentication service as trusted identity provider, the relevant service provider configuration in the Identity Authentication tenant is preserved.



## Procedure

1.  In the SAP BTP cockpit, navigate to the required SAP BTP subaccount. See [Navigate in the Cockpit](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/0874895f1f78459f9517da55a11ffebd.html "Learn how to navigate to your global accounts and subaccounts in the SAP BTP cockpit.") :arrow_upper_right:.

2.  Choose the *Security* \> *Trust* section.

3.  Choose the *Application Identity Provider* tab page. Proceed here depending on one of the following cases:

    -   You have a tenant for Identity Authentication service registered for the same customer ID \(s-user\) as the global account \(see [Global Accounts](../10-concepts-neo/account-model-722a475.md#loio9b7d44f92eec44a6ae87129c02aeec0d)\). You want to add the tenant as an identity provider.

        1.  Click *Add Identity Authentication Tenant*.
        2.  Choose the required Identity Authentication tenant and save the changes.

        In this case, the trust will be established automatically upon registration on both the SAP BTP and the tenant for Identity Authentication service side. See [Initial Setup \(Identity Authentication\)](https://help.sap.com/viewer/6d6d63354d1242d185ab4830fc04feb1/Cloud/en-US/31af7da133874e199a7df1d42905241b.html)

    -   You want to add a tenant for Identity Authentication service not related to your SAP user.

        In this case, you need to register the tenant for Identity Authentication service as described in [Application Identity Provider](application-identity-provider-dc61853.md#loiodc618538d97610148155d97dcd123c24). In addition, configure trust on the tenant as described in [Configure Trust \(Identity Authentication\)](https://help.sap.com/viewer/6d6d63354d1242d185ab4830fc04feb1/Cloud/en-US/f96e4c5930a94d1ba117e05a3f3c30fc.html).





## Results

The tenant for Identity Authentication appears in the list of SAML identity providers. You can now administrate further the Identity Authentication tenant by opening Identity Authentication Admin Console \(hover over the registered tenant for Identity Authentication and click *Identity Authentication Admin Console*\). You can manage the registered tenant for Identity Authentication as any other registered identity provider.

> ### Note:  
> It will take about 2 minutes for the trust configuration with the tenant for Identity Authentication to become active.

> ### Note:  
> Each SAP BTP subaccount is a separate service provider in the tenant for Identity Authentication.

> ### Tip:  
> If you need each of your SAP BTP applications to be represented by its own service provider, create and use a separate subaccount for each application. See [Create a Subaccount](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/05280a123d3044ae97457a25b3013918.html "Create subaccounts in your global account using the SAP BTP cockpit.") :arrow_upper_right:.

**Related Information**  


[Identity Authentication](https://help.sap.com/viewer/6d6d63354d1242d185ab4830fc04feb1/Cloud/en-US/d17a116432d24470930ebea41977a888.html)

[Application Identity Provider](application-identity-provider-dc61853.md#loiodc618538d97610148155d97dcd123c24 "The application identity provider supplies the user base for your applications. For example, you can use your corporate identity provider for your applications. This is called identity federation. SAP BTP supports Security Assertion Markup Language (SAML) 2.0 for identity federation.")

