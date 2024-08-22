<!-- loioe7beab5abb571014949ff631a2e90095 -->

# Persistence Units

A JPA model contains a persistence configuration file, `persistence.xml`, which describes the defined persistence units. A persistence unit in turn defines all entity classes managed by the entity managers in your application and includes the metadata for mapping the entity classes to the database entities.

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of the following technology portfolios: application development; process automation; integration; data, analytics, and enterprise planning; artificial intelligence. The platform offers users the ability to turn data into business value, compose end-to-end business processes, connect entire IT landscapes, and personalize, build and extend SAP applications. This reduces the overall total cost of ownership maintaining SAP landscapes and third-party software across end-to-end business processes.") :arrow_upper_right:.**



## JPA Provider

The `persistence.xml` file is located in the `META-INF` folder within the persistence unit `src` folder. The JPA persistence provider used by the is org.eclipse.persistence.jpa.PersistenceProvider.



## Example

In the `persistence.xml` file in the tutorial *Adding Container-Managed Persistence with JPA \(SDK for Java EE 6 Web Profile\)*, the persistence unit is named `persistence-with-ejb`, the transaction type is JTA \(default setting\), and the DDL generation type has been set to `Create Tables`, as shown below:

```

<?xml version="1.0" encoding="UTF-8"?>
<persistence version="2.0" xmlns="http://java.sun.com/xml/ns/persistence" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
    xsi:schemaLocation="http://java.sun.com/xml/ns/persistence http://java.sun.com/xml/ns/persistence/persistence_2_0.xsd">
    <persistence-unit name="persistence-with-ejb">
        <provider>org.eclipse.persistence.jpa.PersistenceProvider</provider>
        <class>com.sap.cloud.sample.persistence.Person</class>
        <properties>
            <property name="eclipselink.ddl-generation" value="create-tables" />
        </properties>
    </persistence-unit>
</persistence>

```



<a name="loioe7beab5abb571014949ff631a2e90095__section_A73E8EB46D9A41A58F811DCC667738DA"/>

## DDL Generation Type

The the EclipseLink capabilities to generate database tables. The following values are valid for generating the DDL for the entity specified in the `persistence.xml` file:

-   `none`: EclipseLink does not generate a DDL \(no schema is generated\).
-   `create-tables`: EclipseLink attempts to execute a CREATE TABLE SQL statement. It creates a DDL for non-existent tables and leaves existing tables unchanged \(they are not dropped or replaced\).
-   `drop-and-create-tables`: EclipseLink attempts to DROP all tables and then CREATE all tables.

    > ### Note:  
    > Drop-and-create tables are often used during the development phase, when there are frequent changes to the schema or data needs to be deleted. Don't forget to change it to `create-tables` before you deploy the application; all data is lost when you drop a table.




<a name="loioe7beab5abb571014949ff631a2e90095__section_59C2A659B73A4AC892617F9668F52ED1"/>

## Transaction Type

JTA transactions are used for container-managed persistence, and resource-local transactions for application-managed persistence. The SDK for Java Web supports resource-local transactions only.

