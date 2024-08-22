<!-- loioe79cfef4bb57101494cde44e48426511 -->

# Programming with Plain JDBC

Program with JDBC in the Neo environment in cases in which its low-level control is more appropriate than JPA.

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of the following technology portfolios: application development; process automation; integration; data, analytics, and enterprise planning; artificial intelligence. The platform offers users the ability to turn data into business value, compose end-to-end business processes, connect entire IT landscapes, and personalize, build and extend SAP applications. This reduces the overall total cost of ownership maintaining SAP landscapes and third-party software across end-to-end business processes.") :arrow_upper_right:.**



> ### Caution:  
> Creating your own `DataSource` is not supported in the Neo environment and may cause issues. JDBC URLs should only be provided via backend services, not hardcoded, as they may change due to internal updates of the Neo environment.

Working with JDBC entails manually writing SQL statements to read and write objects from and to the database.



<a name="loioe79cfef4bb57101494cde44e48426511__section_N10050_N10013_N10001"/>

## JNDI Resource Reference

An application can use one or more data sources. A data source can be a default, or explicitly named. Either way, before a data source can be used, you must declare it as a JNDI resource reference.

Declare a JNDI resource reference to a JDBC data source in the `web.xml` deployment descriptor located in the `WebContent/WEB-INF` directory as shown below. The resource reference name is only an example:

```

<resource-ref>
    <res-ref-name>jdbc/DefaultDB</res-ref-name>
    <res-type>javax.sql.DataSource</res-type>
</resource-ref>

```

The resource attributes are as follows:

-   `<res-ref-name>`: The JNDI name of the resource. The Java EE Specification recommends that you declare the data source reference in the jdbc subcontext \(`jdbc/NAME`\).
-   `<res-type>`: The type of resource that is returned during the lookup.

Add the `<resource-ref>` elements after the `<servlet-mapping>` elements in the deployment descriptor.

If the application uses multiple data sources, add a resource reference for each data source:

```
<resource-ref>
      <res-ref-name>jdbc/datasource1</res-ref-name>
      <res-type>javax.sql.DataSource</res-type>
</resource-ref>
<resource-ref>
      <res-ref-name>jdbc/datasource2</res-ref-name>
      <res-type>javax.sql.DataSource</res-type>
</resource-ref>
```



## Data Source Lookup

You can obtain an initial JNDI context from Tomcat by creating a `javax.naming.InitialContext` object. Then consume the data source by looking up the naming environment through the `InitialContext`, as follows:

```

InitialContext ctx = new InitialContext();
DataSource ds = (DataSource) ctx.lookup("java:comp/env/jdbc/DefaultDB");

```

According to the Java EE Specification, you should add the prefix `java:comp/env` to the JNDI resource name \(as specified in `web.xml`\) to form the lookup name.

If the application uses multiple data sources, construct the lookup in a similar manner to the following:

```
InitialContext ctx = new InitialContext();
DataSource ds1 = (DataSource) ctx.lookup("java:comp/env/jdbc/datasource1");
DataSource ds2 = (DataSource) ctx.lookup("java:comp/env/jdbc/datasource2");
```



<a name="loioe79cfef4bb57101494cde44e48426511__section_N10036_N10013_N10001"/>

## Data Source Injection

You can directly inject the data source using annotations as shown below.

-   Default data source

    A default data source is automatically provided; therefore, you don't need to declare the JNDI resource reference in the `web.xml` deployment descriptor or in the resource name. To inject the data source, use the following code:

    ```
    @Resource
    private javax.sql.DataSource ds;
    ```

-   If the application uses explicitly named data sources, you must first declare them in the `web.xml` file. Inject them as shown in the following example:

    ```
    @Resource(name="jdbc/datasource1")
        private javax.sql.DataSource ds1;
    
    @Resource(name="jdbc/datasource2")
        private javax.sql.DataSource ds2;
    ```




<a name="loioe79cfef4bb57101494cde44e48426511__section_2F4125C829D8448E9A85A07400DE59D2"/>

## JDBC Connection

The data source let you create a JDBC connection to the database. You can use the resulting Connection object to instantiate a Statement object and execute SQL statements, as shown in the following example:

```sql

private static final String STMT_SELECT_ALL = "SELECT ID, FIRSTNAME, LASTNAME FROM " + TABLE_NAME;
Connection conn = dataSource.getConnection();
		try {
        PreparedStatement pstmt = conn.prepareStatement(STMT_SELECT_ALL);
        ResultSet rs = pstmt.executeQuery();
  ...

```



<a name="loioe79cfef4bb57101494cde44e48426511__section_3134F8B86E2D4F17A171C1981DD87D42"/>

## Database Tables

Use plain SQL statements to create the tables you require. Since there is currently no tool support available, you have to manually maintain the table life cycles. The exact syntax you'll use may differ, depending on the underlying database. The Connection object provides metadata about the underlying database and its tables and fields, which can be accessed as shown in the code below:

```
String database = conn.getMetaData().getDatabaseProductName();

```

To create a table in the Apache Derby database, you could use the following SQL statement executed with a PreparedStatement object:

```sql

private static final String STMT_CREATE_TABLE_DERBY = "CREATE TABLE "
		+ TABLE_NAME + " (ID INTEGER GENERATED ALWAYS AS IDENTITY
              PRIMARY KEY, " +  "FIRSTNAME VARCHAR (255), LASTNAME VARCHAR
              (255))";

PreparedStatement pstmt = conn.prepareStatement(STMT_CREATE_TABLE_DERBY);
pstmt.executeUpdate();

```



<a name="loioe79cfef4bb57101494cde44e48426511__section_40BF49691D004648A51F3728BAC85DBD"/>

## DAO Objects and SQL Statements

See the tutorial *Adding Persistence Using JDBC* for information about executing SQL statements and applying the Data Access Object \(DAO\) design pattern in your Web application.

**Related Information**  


[Tutorial: Adding Persistence with JDBC \(SDK for Java Web\)](tutorial-adding-persistence-with-jdbc-sdk-for-java-web-e4c5285.md#loioe4c52854bb571014aeb88753d0dad158 "Use JDBC to persist data in a simple Java EE web application that manages a list of persons.")

[Java EE Specification](https://jcp.org/aboutJava/communityprocess/final/jsr244/index.html)

