<!-- loio48b552fa449945b9afc7885e1919ce2b -->

# Multitenancy Roles

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**



## Context

The multitenancy concept concerns two main user roles:

-   `Application Provider` - an organizational unit that uses SAP BTP to build, run and sell applications to customers, that is, the application consumers.
-   `Application Consumer` - an organizational unit, typically a customer or a department inside a customer’s organization, which uses an SAP BTP application for a certain purpose. Obviously, the application is in fact used by end users, who might be employees of the organization \(for instance, in the case of an HR application\) or just arbitrary users, internal or external \(for instance, in the case of a collaborative supplier application\).



## Subaccounts and Subaccount Members

To use SAP BTP, both the application provider and the application consumer need to have a subaccount. The subaccount is the central organizational unit in SAP HANA Cloud Plaftorm. It is the central entry point to SAP BTP for both application providers and consumers. It may consist of a set of applications, a set of subaccount members and a subaccount-specific configuration.

Subaccount members are users who must be registered via the SAP ID service. Subaccount members may have different privileges regarding the operations which are possible for a subaccount \(for example, subaccount administration, deploy/start/stop applications\). Note that the subaccount belongs to an organization and not to an individual. Nevertheless, the interaction with the subaccount is performed by individuals, the members of the subaccount. The subaccount-specific configuration allows application providers and application consumers to adapt their subaccount to their specific environment and needs.

An application resides in exactly one subaccount, the hosting subaccount. It is uniquely identified by the subaccount name and the application name. Applications consume SAP BTP resources, for instance, compute units, structured and unstructured storage and outgoing bandwidth. Costs for consumed resources are billed to the owner of the hosting subaccount, who can be an application provider, an application consumer, or both.



## Deployment Application Models

-   *Consumer-Managed Application Model*

    In the consumer-managed application model, a copy of the application is deployed into the consumer subaccount. The application consumer buys the application from the application provider via SAP Store. In addition, the application consumer separately buys all required SAP BTP resources \(such as compute units, storage or bandwidth\) from the platform provider, that is SAP. All platform resources consumed by the application are directly billed to the application consumer. The compute units hosting the application are not shared between multiple application consumers. Instead, each application consumer runs the application on dedicated compute units \(VMs\). In the consumer-managed application model, the application consumer is responsible to operate the application.

-   *Provider-Managed Application Model*

    In the provider-managed application model, the application is deployed into the provider subaccount only. The application provider may decide to start a dedicated compute unit for each consumer or to share one or multiple compute units between them. The application is operated and maintained by the application provider. Platform resources consumed by the application are billed to the application provider. The application provider is responsible for passing the costs on to the consumers. Application providers can define their own price model, which can be independent from the platform resources prices.

    In the provider-managed deployment model, there is no deployment required into the consumer subaccount. Instead, consumers are "subscribed" to the provider application, once they have purchased the application. As a result, a subscription for the purchased application is created in the consumer subaccount. This subscription enables consumers to launch the application, using a consumer-specific URL, and configure it to their needs.

    Typically, the application consumer configures the used identity provider, the user roles for the application, or, if required by the subscribed application, the connection parameters to another system.


**Related Information**  


[Providing Java Multitenant Applications to Tenants for Testing](../22-getting-started-neo/providing-java-multitenant-applications-to-tenants-for-testing-b093032.md "Using the console client, you can create subaccounts and subscribe them to a provider application to test how applications can be provided to multiple consumers.")

