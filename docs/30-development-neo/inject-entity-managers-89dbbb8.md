<!-- loio89dbbb837f3d480ba3560c77b0f5929a -->

# Inject Entity Managers

EJB session beans, which typically perform the database operations, can use the `@PersistenceContext` annotation to directly inject the entity manager. The corresponding entity manager factory is created transparently by the container.



## Context

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**



## Procedure

1.  In the EJB session bean, inject the entity manager as follows. A persistence context type has not been explicitly specified in the example below and is therefore, by default, transaction-scoped:

    ```
    @PersistenceContext
    private EntityManager em;
    
    ```

    To use an extended persistence context, set the value of the persistence context type to EXTENDED \(@PersistenceContext\(type=PersistenceContextType.EXTENDED\)\), and declare the session bean as stateful. An extended persistence context allows a session bean to maintain its state across multiple JTA transactions. An extended persistence context is not threadsafe.

2.  If you have more than one persistence unit, inject the required number of entity managers by specifying the persistence unit name as defined in the `persistence.xml` file:

    ```
    @PersistenceContext(unitName="hanadb")
    private EntityManager em1;
    ...
    @PersistenceContext(unitName="maxdb")
    private EntityManager em2;
    
    ```

3.  Inject an instance of the EJB session bean class into, for example, the servlet of the web application with an annotation in the following form, where `PersonBean` is an example session bean class:

    ```
    @EJB PersonBean personBean;
    ```

    The persistence context made available is based on JTA and provides automatic transaction management. Each EJB business method automatically has a managed transaction, unless specified otherwise. The entity manager life cycle, such as instantiation and closing, is controlled by the container. Therefore, do not use methods designed for resource-local transactions, such as `em.getTransaction().begin()`, `em.getTransaction().commit()`, and `em.close()`.


**Related Information**  


[Configure Data Sources As Connection Properties](testing-on-the-local-runtime-bdf459e.md#loio73e8d4c514f14a399c25711dd43f6975 "To test an application on the local server, define any data sources the application uses as connection properties for the local database. You don't need to do this if the application uses the default data source.")

