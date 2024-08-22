<!-- loio4f035202395d410f93ae345ac02c60ce -->

# Configure Persistence Units

To use container-managed entity managers, configure JTA data sources in the `persistence.xml` file. JTA data sources are managed data sources and are associated with JTA transactions.



## Context

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of the following technology portfolios: application development; process automation; integration; data, analytics, and enterprise planning; artificial intelligence. The platform offers users the ability to turn data into business value, compose end-to-end business processes, connect entire IT landscapes, and personalize, build and extend SAP applications. This reduces the overall total cost of ownership maintaining SAP landscapes and third-party software across end-to-end business processes.") :arrow_upper_right:.**

To configure JTA data sources, set the transaction type attribute \(`transaction-type`\) to JTA and specify the names of the JTA data sources \(`jta-data-source`\), unless the application is using the default data source.



## Procedure

1.  In the *Project Explorer* view, select `<project>/Java Resources/src/META-INF/persistence.xml`, and from the context menu choose *Open With* \> *Persistence XML Editor*.

2.  On the *Connection* tab, enter the transaction type `JTA` or leave the default setting, which is JTA.

3.  If the application is using an explicitly named data source, enter the JNDI name of the data source in the *JTA data source* field.

    If it uses the default data source, you don't need to specify a data source in the `persistence.xml` file.

4.  If the application uses more than one data source, define a corresponding number of persistence units, each with its own data source. The data source name is the JNDI name used for the lookup and must match the name used for the schema binding. To do this, switch to the *Source* tab of the `persistence.xml` file.

    The example below shows the persistence units defined for two data sources, where each data source is associated with a different database:

    ```
    <persistence>
    <persistence-unit name="hanadb" transaction-type="JTA">
    <provider>org.eclipse.persistence.jpa.PersistenceProvider</provider>
    <jta-data-source>jdbc/hanaDB</jta-data-source>
            <class>com.sap.cloud.sample.persistence.Person</class>
            <properties>
                <property name="eclipselink.ddl-generation" value="create-tables" />
            </properties>
    </persistence-unit>
    <persistence-unit name="maxdb" transaction-type="JTA">
            <provider>org.eclipse.persistence.jpa.PersistenceProvider</provider>
            <jta-data-source>jdbc/maxDB</jta-data-source>
            <class>com.sap.cloud.sample.persistence.Person</class>
            <properties>
                <property name="eclipselink.ddl-generation" value="create-tables" />
            </properties>
        </persistence-unit>
    </persistence>
    
    ```

5.  Save the file.


**Related Information**  


[Configure Data Sources As Connection Properties](testing-on-the-local-runtime-bdf459e.md#loio73e8d4c514f14a399c25711dd43f6975 "To test an application on the local server, define any data sources the application uses as connection properties for the local database. You don't need to do this if the application uses the default data source.")

