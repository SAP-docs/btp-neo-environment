<!-- loioc017f265b7cd463399470c7d452a0dc3 -->

# Configure Persistence Units

To use application-managed entity managers, configure resource-local transactions in the `persistence.xml` file. Resource-local transactions are associated with non-JTA data sources \(that is, unmanaged data sources\) and are explicitly controlled by the application through the `EntityTransaction` interface of the entity manager.



## Context

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**

To use resource-local transactions, the transaction type attribute has to be set to RESOURCE\_LOCAL, indicating that the entity manager factory should provide resource-local entity managers. When you work with a non-JTA data source, the non-JTA data source element also has to be set in the persistence unit properties in the application code.



## Procedure

1.  In the *Project Explorer* view, select `<project>/Java Resources/src/META-INF/persistence.xml`, and from the context menu choose *Open With* \> *Persistence XML Editor*.

2.  On the *Connection* tab, enter the transaction type ***Resource Local***.

3.  Save the file.


