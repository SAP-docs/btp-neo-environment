<!-- loiof90799fe7ef04753bb6442c8e2fa26d8 -->

# Special Settings for EclipseLink Versions Earlier than 2.5

EclipseLink versions prior to 2.5 do not include the SAP HANA database platform. To deploy applications on the SAP HANA database, you need to specify it as the target database and, for application-managed persistence, import the corresponding JAR file into your project.

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**



## Container-Managed Persistence

Specify the target database as a persistence unit property:

1.  Select the `<project>/Java Resources/src/META-INF/persistence.xml` file and from the context menu, choose *Open With* \> *Persistence XML Editor*.
2.  On the *Options* tab, enter ***com.sap.persistence.platform.database.HDBPlatform*** in the *Target database* field.

The source code should now contain the following:

```
<properties>
            <property name="eclipselink.target-database" value="com.sap.persistence.platform.database.HDBPlatform"/>
</properties>
```



## Application-Managed Persistence

Specify the target database as shown above or directly in the servlet code, as shown in the example below:

```
ds = (DataSource) ctx.lookup("java:comp/env/jdbc/DefaultDB");
connection = ds.getConnection();
Map properties = new HashMap();
properties.put(PersistenceUnitProperties.NON_JTA_DATASOURCE, ds);
properties.put("eclipselink.target-database", "com.sap.persistence.platform.database.HDBPlatform");
```

Add the SAP HANA JAR to the Web application project:

1.  Select the `<project>/WebContent/WEB-INF/lib` node.
2.  From the context menu, choose *Import* \> *General* \> *File System*, then choose *Next*.
3.  Browse to the local directory where you downloaded and unpacked the SAP BTP SDK, select the `repository/plugins` directory, and choose *OK*.
4.  Select *com.sap.core.persistence.osgi.hdb.platform\_x.y.z.jar* and choose *Finish*.



## General Points

Set the target database property before you deploy the application on the SAP HANA database. If you don't, you'll get an error, and if this happens, you need to re-create the table with the correct definitions, setting the DDL generation type to ***Drop and Create Tables*** , then redeploy the application. Afterwards, set the generation type back to ***Create Tables*** so that you do not lose your data once you deploy again.

When testing the application locally, remove the DDL generation type altogether.

