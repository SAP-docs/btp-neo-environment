<!-- loiobb269c2b9ce94840a057015264d0b253 -->

# Apply Dynamic Data Source Lookup

The data source is determined dynamically at runtime and does not need to be defined in the `web.xml` or `persistence.xml` file. This allows you to bind additional schemas to an application and obtain the corresponding data source, without having to modify the application code or redeploy the application.



## Context

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of the following technology portfolios: application development; process automation; integration; data, analytics, and enterprise planning; artificial intelligence. The platform offers users the ability to turn data into business value, compose end-to-end business processes, connect entire IT landscapes, and personalize, build and extend SAP applications. This reduces the overall total cost of ownership maintaining SAP landscapes and third-party software across end-to-end business processes.") :arrow_upper_right:.**

A dynamic JNDI lookup is applied as follows, depending on whether you are using an unmanaged or a managed data source:

-   Unmanaged - supported in all Java runtimes

    ```
    context.lookup("unmanageddatasource:<data source name>")
    ```

-   Managed - supported in Java EE runtimes \(Java EE 6 Web Profile and Java EE 7 Web Profile TomEE 7\)

    ```
    context.lookup("manageddatasource:<data source name>")
    ```


The steps described below are based on JPA application-managed persistence using a Java runtime.



## Procedure

1.  Create the persistence unit to be used for the dynamic data source lookup:

    1.  In the *Project Explorer* view, select `<project>/Java Resources/src/META-INF/persistence.xml`, and from the context menu choose *Open With* \> *Persistence XML Editor*.

    2.  Switch to the *Source* tab of the `persistence.xml` file and create a persistence unit, as shown in the example below. The corresponding data source is not defined in either the `persistence.xml` or `web.xml` file:

        ```
        <persistence-unit name="mypersistenceunit" transaction-type="RESOURCE_LOCAL">
        <provider>org.eclipse.persistence.jpa.PersistenceProvider</provider>
        <class>com.sap.cloud.sample.persistence.Person</class>
        <properties>
        <property name="eclipselink.ddl-generation" value="create-tables"/>
        </properties>
        </persistence-unit>
        ```


2.  In the servlet code, implement a JNDI data source lookup. In the example below, the data source name is "mydatasource":

    ```
    ds = (DataSource) context.lookup("unmanageddatasource:mydatasource");
    ```

3.  Create an entity manager factory in the normal manner. In the example below, the persistence unit is named "mypersistenceunit", as defined in the `persistence.xml` file:

    ```
    Map properties = new HashMap();
                properties.put(PersistenceUnitProperties.NON_JTA_DATASOURCE, ds);
    emf = Persistence.createEntityManagerFactory("mypersistenceunit", properties);
    ```

4.  Use the console client to create a schema binding with the same data source name. To do this, open the command window in the `<SDK>/tools` folder and enter the [bind-schema](../50-administration-and-ops-neo/bind-schema-ce689b2.md) command, using the data source name you defined in step 2:

    ```
    neo bind-schema -h <host> -u <user> -a <subaccount> -b <application name> --data-source mydatasource --id <schema ID>
    
    ```

    > ### Note:  
    > Note that you need to use the same data source name you have defined in step 2.


