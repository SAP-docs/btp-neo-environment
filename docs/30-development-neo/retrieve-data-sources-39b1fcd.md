<!-- loio39b1fcd42c864eea9fcdf381a64c13b8 -->

# Retrieve Data Sources

In the application code, obtain an initial JNDI context by creating a `javax.naming.InitialContext` object, then retrieve the data source by looking up the naming environment through the `InitialContext`. Alternatively, you can directly inject the data source.



## Context

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/docs/btp/sap-business-technology-platform/sap-business-technology-platform?version=Cloud) .**



## Procedure

1.  To create an initial JNDI context and look up the data source, add the following code to your application and make sure that the JNDI name matches the one specified in the `web.xml` file:

    ```
    InitialContext ctx = new InitialContext();
    DataSource ds = (DataSource) ctx.lookup("java:comp/env/jdbc/DefaultDB");
    ```

    According to the Java EE Specification, you should add the prefix `java:comp/env` to the JNDI resource name \(as specified in the `web.xml`\) to form the lookup name. For more information about defining and referencing resources according to the Java EE standard, see the *Java EE Specification*.

2.  Alternatively, to directly inject the data source, use the `@Resource` annotation:

    -   Default data source

        Since the default data source is provided automatically, it can be injected without an explicit resource name, as shown below. You don't need to also declare the JNDI resource reference in the `web.xml` or `persistence.xml` file:

        ```
        @Resource
        private javax.sql.DataSource ds;
        ```

    -   Explicitly named data sources

        These are injected with a specific resource name, as specified in the `web.xml` or `persistence.xml` file:

        ```
        @Resource(name="jdbc/datasource1")
            private javax.sql.DataSource ds1;
        
        @Resource(name="jdbc/datasource2")
            private javax.sql.DataSource ds2;
        ```



**Related Information**  


[Java EE Specification](https://jcp.org/aboutJava/communityprocess/final/jsr244/index.html)

