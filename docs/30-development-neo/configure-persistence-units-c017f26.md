<!-- loioc017f265b7cd463399470c7d452a0dc3 -->

# Configure Persistence Units

To use application-managed entity managers, configure resource-local transactions in the `persistence.xml` file. Resource-local transactions are associated with non-JTA data sources \(that is, unmanaged data sources\) and are explicitly controlled by the application through the `EntityTransaction` interface of the entity manager.



## Context

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/docs/btp/sap-business-technology-platform/sap-business-technology-platform?version=Cloud) .**

To use resource-local transactions, the transaction type attribute has to be set to RESOURCE\_LOCAL, indicating that the entity manager factory should provide resource-local entity managers. When you work with a non-JTA data source, the non-JTA data source element also has to be set in the persistence unit properties in the application code.



## Procedure

1.  In the *Project Explorer* view, select `<project>/Java Resources/src/META-INF/persistence.xml`, and from the context menu choose *Open With* \> *Persistence XML Editor*.

2.  On the *Connection* tab, enter the transaction type `Resource Local`.

3.  Save the file.


