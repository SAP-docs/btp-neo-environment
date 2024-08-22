<!-- loio572e33429cd0428a9091ae859b27662f -->

# Create Entity Managers

Use the `EntityManagerFactory` interface to manually create and manage entity managers in your Web application.



## Context

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of the following technology portfolios: application development; process automation; integration; data, analytics, and enterprise planning; artificial intelligence. The platform offers users the ability to turn data into business value, compose end-to-end business processes, connect entire IT landscapes, and personalize, build and extend SAP applications. This reduces the overall total cost of ownership maintaining SAP landscapes and third-party software across end-to-end business processes.") :arrow_upper_right:.**



## Procedure

1.  Use `javax.persistence.Persistence.createEntityManagerFactory` to create an `EntityManagerFactory` object that operates on the data source that you have retrieved:

    ```
    Map properties = new HashMap();
    properties.put(PersistenceUnitProperties.NON_JTA_DATASOURCE, ds);
    emf = Persistence.createEntityManagerFactory("persistence-with-jpa", properties);
    
    ```

    In the code above, the non-JTA data source element has been set in the persistence unit properties, and the persistence unit name is the name of the persistence unit as it is declared in the `persistence.xml` file.

    > ### Note:  
    > Include the above code in the servlet `init()` method, as illustrated in the tutorial *Adding Application-Managed Persistence with JPA \(SDK for Java Web\)*, since this method is called only once during initialization when the servlet instance is loaded.

2.  Use the entity manager factory obtained above to create an entity manager as follows:

    ```
    EntityManager em = emf.createEntityManager();
    ```




## Next Steps

Application-managed entity managers are always extended and therefore retain the entities beyond the scope of a transaction. You should therefore close an entity manager when it is no longer needed by calling `EntityManager.close()`, or alternatively `EntityManager.clear()` wherever appropriate, such as at the end of a transaction. An entity manager cannot be used concurrently by multiple threads, so design your entity manager handling to avoid doing this.

**Related Information**  


[Entity Transaction API](entity-transaction-api-e663d58.md "When working with a resource-local entity manager, use the EntityTransaction API to manually set the transaction boundaries in your application code. You can obtain the entity transaction attached to the entity manager by calling EntityManager.getTransaction().")

[Configure Data Sources As Connection Properties](testing-on-the-local-runtime-bdf459e.md#loio73e8d4c514f14a399c25711dd43f6975 "To test an application on the local server, define any data sources the application uses as connection properties for the local database. You don't need to do this if the application uses the default data source.")

[Tutorial: Adding Application-Managed Persistence with JPA \(SDK for Java Web\)](tutorial-adding-application-managed-persistence-with-jpa-sdk-for-java-web-e4aeacd.md#loioe4aeacd2bb5710148ee99255136d96a5 "Use JPA to apply application-managed persistence in a simple Java EE web application that manages a list of persons.")

