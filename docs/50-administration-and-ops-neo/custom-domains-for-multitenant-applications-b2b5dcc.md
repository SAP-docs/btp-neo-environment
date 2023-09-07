<!-- loiob2b5dcc4fd9842388bb047d2922be48c -->

# Custom Domains for Multitenant Applications

Configuration of custom domains has different setups related to the subscriptions of your subaccount. Subscriptions represent applications that your subaccount has purchased for use from an application provider.

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**

> ### Note:  
> If you want to configure a custom domain for an SAP Cloud Integration application, see [Configuring Custom Domains for SAP Cloud Integration](https://help.sap.com/viewer/368c481cd6954bdfa5d0435479fd4eaf/Cloud/en-US/7230b9ff41914cc0969223e6a020104b.html).

A subscription means that there is a contract between an application provider and a tenant that authorizes the tenant to use the provider's application. As the consumer subaccount, you do not own, deploy, or operate these applications yourself. Subscriptions allow you to configure certain features of the applications and launch them through consumer-specific URLs.

The default URL of a multitenant application is: `https://<application_name><provider_subaccount>-<consumer_subaccount>.<domain>`.

When you configure custom domains for such applications that are part of a subscription, the following scenarios are possible:

-   The custom domain is owned by the application provider who uses an SSL host from their subaccount quota. The provider also does the configuration and assignment of the custom domain. The provider can assign a subdomain of its own custom domain to a particular subscription URL. To do this, the provider needs to have rights in both the provider and consumer subaccount.
-   The customer \(consumer\) uses an SSL host from the consumer subaccount quota. In this case, the customer \(consumer\) owns the custom domain and the SSL host and is therefore able do the necessary configuration on their own.

**Related Information**  


[Developing Multitenant Applications in the Neo Environment](../30-development-neo/developing-multitenant-applications-in-the-neo-environment-54a7615.md "In the Neo environment of SAP BTP, you can develop and run multitenant (tenant-aware) applications. These applications run on a shared compute unit that can be used by multiple consumers (tenants). Each consumer accesses the application through a dedicated URL.")

