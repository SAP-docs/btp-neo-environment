<!-- loioe658f24cbb571014a2f9e19ed3502198 -->

# Using Application-Managed Persistence

Application-managed entity managers are created manually using the `EntityManagerFactory` interface. Application-managed entity managers require resource-local transactions and non-JTA data sources, which you must declare as JNDI resource references.



## Context

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**

The scenario described in this section is based on the Java Web runtime, which supports only manual creation of the entity manager factory.



<a name="loioe658f24cbb571014a2f9e19ed3502198__steps_cv2_4xz_vk"/>

## Procedure

1.  Declare a JNDI resource reference.

2.  Configure the persistence units in the `persistence.xml` file to use resource-local transactions and non-JTA data sources.

3.  Use a JNDI lookup in the application code to retrieve the data source.

4.  Create an entity manager factory and entity manager.


**Related Information**  


[Declare JNDI Resource References](declare-jndi-resource-references-e5d4679.md "An application can use one or more data sources. A data source can be a default data source or an explicitly named data source. Before a data source can be used, you must declare it as a JNDI resource reference in the web.xml deployment descriptor.")

[Configure Persistence Units](configure-persistence-units-c017f26.md "To use application-managed entity managers, configure resource-local transactions in the persistence.xml file. Resource-local transactions are associated with non-JTA data sources (that is, unmanaged data sources) and are explicitly controlled by the application through the EntityTransaction interface of the entity manager.")

[Retrieve Data Sources](retrieve-data-sources-39b1fcd.md "In the application code, obtain an initial JNDI context by creating a javax.naming.InitialContext object, then retrieve the data source by looking up the naming environment through the InitialContext. Alternatively, you can directly inject the data source.")

[Create Entity Managers](create-entity-managers-572e334.md "Use the EntityManagerFactory interface to manually create and manage entity managers in your Web application.")

[Apply Dynamic Data Source Lookup](apply-dynamic-data-source-lookup-bb269c2.md "The data source is determined dynamically at runtime and does not need to be defined in the web.xml or persistence.xml file. This allows you to bind additional schemas to an application and obtain the corresponding data source, without having to modify the application code or redeploy the application.")

[Entity Transaction API](entity-transaction-api-e663d58.md "When working with a resource-local entity manager, use the EntityTransaction API to manually set the transaction boundaries in your application code. You can obtain the entity transaction attached to the entity manager by calling EntityManager.getTransaction().")

