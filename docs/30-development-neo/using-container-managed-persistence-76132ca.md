<!-- loio76132cac711e1014839a8273b0e91070 -->

# Using Container-Managed Persistence

Container-managed entity managers are the model most commonly used by Web applications. Container-managed entity managers require JTA transactions and are generally used with stateless session beans and transaction-scoped persistence contexts, which are threadsafe.



## Context

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/docs/btp/sap-business-technology-platform/sap-business-technology-platform?version=Cloud) .**

The scenario described in this section is based on the Java EE 6 Web Profile runtime. You use a stateless EJB session bean into which the entity manager is injected using the `@PersistenceContext` annotation.



<a name="loio76132cac711e1014839a8273b0e91070__steps_dy2_xcy_vk"/>

## Procedure

1.  Configure the persistence units in the `persistence.xml` file to use JTA data sources and JTA transactions.

2.  Inject the entity manager into an EJB session bean using the `@PersistenceContext` annotation.


**Related Information**  


[Configure Persistence Units](configure-persistence-units-4f03520.md "To use container-managed entity managers, configure JTA data sources in the persistence.xml file. JTA data sources are managed data sources and are associated with JTA transactions.")

[Inject Entity Managers](inject-entity-managers-89dbbb8.md "EJB session beans, which typically perform the database operations, can use the @PersistenceContext annotation to directly inject the entity manager. The corresponding entity manager factory is created transparently by the container.")

