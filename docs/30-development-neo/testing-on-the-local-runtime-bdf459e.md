<!-- loiobdf459ef3e1d4bf099705db9b8792140 -->

# Testing on the Local Runtime

Test an application in the Neo environment that uses the default data source and runs locally on Apache Derby on the local runtime.

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of the following technology portfolios: application development; process automation; integration; data, analytics, and enterprise planning; artificial intelligence. The platform offers users the ability to turn data into business value, compose end-to-end business processes, connect entire IT landscapes, and personalize, build and extend SAP applications. This reduces the overall total cost of ownership maintaining SAP landscapes and third-party software across end-to-end business processes.") :arrow_upper_right:.**

> ### Note:  
> The Java tools for Eclipse used in this page are no longer available. We are in the process of updating the content accordingly.

If an application uses the default data source and runs locally on Apache Derby, provided as standard for local development, you can test it on the local runtime without any further configuration. To use explicitly named data sources or a different database, you'll need to configure the `connection.properties` file appropriately.

<a name="loio73e8d4c514f14a399c25711dd43f6975"/>

<!-- loio73e8d4c514f14a399c25711dd43f6975 -->

## Configure Data Sources As Connection Properties

To test an application on the local server, define any data sources the application uses as connection properties for the local database. You don't need to do this if the application uses the default data source.



## Prerequisites

Start the local server at least once \(with or without the application\) to create the relevant folder.



## Procedure

1.  In the *Project Explorer* view, open the folder `Servers/SAP Cloud Platform local runtime/config_master/connection_data` and select *connection.properties*.

2.  From the context menu, choose *Open With* \> *Properties File Editor*.

3.  Add the connection parameter `com.sap.cloud.persistence.dsname` to the block of connection parameters for the local database you are using, as shown in the example below:

    ```
    com.sap.cloud.persistence.dsname=jdbc/datasource1
    javax.persistence.jdbc.driver=org.apache.derby.jdbc.EmbeddedDriver
    javax.persistence.jdbc.url=jdbc:derby:memory:DemoDB;create=true
    javax.persistence.jdbc.user=demo
    javax.persistence.jdbc.password=demo
    eclipselink.target-database=Derby
    ```

    If the application has been bound to the data source based on an explicitly named data source instead of using the default data source, ensure the following:

    -   Provide a data source name in the connection properties that matches the name used in the data source binding definition.

    -   Add prefixes before each property in a property group for each data source binding you define. If an application is bound only to the default data source, this configuration is considered the default no matter which name you specified in the connection properties. The application can address the data source by any name.


4.  Repeat this step for all data sources that the application uses.

5.  For the Java EE 6 Web Profile runtime, add the connection parameter `com.sap.cloud.persistence.dsname` twice, once for the managed data source and once for the unmanaged data source, with the names given below. Add each entry in its own block of connection properties:

    ```
    com.sap.cloud.persistence.dsname=jdbc/defaultManagedDataSource
    com.sap.cloud.persistence.dsname=jdbc/defaultUnmanagedDataSource
    
    ```

6.  To indicate that a block of parameters belong together, add a prefix to the parameters, as shown in the example below. The prefix is freely definable; the dot isn't required:

    ```
    1.com.sap.cloud.persistence.dsname=jdbc/datasource1
    1.javax.persistence.jdbc.driver=org.apache.derby.jdbc.EmbeddedDriver
    1.javax.persistence.jdbc.url=jdbc:derby:memory:DemoDB;create=true
    1.javax.persistence.jdbc.user=demo
    1.javax.persistence.jdbc.password=demo
    1.eclipselink.target-database=Derby
    
    2.com.sap.cloud.persistence.dsname=jdbc/defaultManagedDataSource
    2.javax.persistence.jdbc.driver=org.apache.derby.jdbc.EmbeddedDriver
    2.javax.persistence.jdbc.url=jdbc:derby:memory:DemoDB;create=true
    2.javax.persistence.jdbc.user=demo
    2.javax.persistence.jdbc.password=demo
    2.eclipselink.target-database=Derby
    
    3.com.sap.cloud.persistence.dsname=jdbc/defaultUnmanagedDataSource
    3.javax.persistence.jdbc.driver=org.apache.derby.jdbc.EmbeddedDriver
    3.javax.persistence.jdbc.url=jdbc:derby:memory:DemoDB;create=true
    3.javax.persistence.jdbc.user=demo
    3.javax.persistence.jdbc.password=demo
    3.eclipselink.target-database=Derby
    ```

7.  Save the file.

8.  Start or restart the server so that the new properties are read.


