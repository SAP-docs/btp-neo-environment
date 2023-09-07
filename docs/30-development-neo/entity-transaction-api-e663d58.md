<!-- loioe663d584bb571014a99af48717abd94a -->

# Entity Transaction API

When working with a resource-local entity manager, use the EntityTransaction API to manually set the transaction boundaries in your application code. You can obtain the entity transaction attached to the entity manager by calling `EntityManager.getTransaction()`.

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**

To create and update data in the database, you need an active transaction. The EntityTransaction API provides the `begin()` method for starting a transaction, and the `commit()` and `rollback()` methods for ending a transaction. When a commit is executed, all changes are synchronized with the database.



## Example

The tutorial code \(*Adding Application-Managed Persistence with JPA \(SDK for Java Web\)*\) shows how to create and persist an entity:

```

Person person = new Person("<name>");
em.getTransaction().begin();
em.persist(person); 
em.getTransaction().commit(); 
em.close();

```

The `EntityManager.persist()` method makes an entity persistent by associating it with an entity manager. It is inserted into the database when the `commit()` method is called. The `persist()` method can be called only on new entities.

**Related Information**  


[Tutorial: Adding Application-Managed Persistence with JPA \(SDK for Java Web\)](tutorial-adding-application-managed-persistence-with-jpa-sdk-for-java-web-e4aeacd.md#loioe4aeacd2bb5710148ee99255136d96a5 "Use JPA to apply application-managed persistence in a simple Java EE web application that manages a list of persons.")

