<!-- loioe5d46793bb5710148c05ee3ad01abd39 -->

# Declare JNDI Resource References

An application can use one or more data sources. A data source can be a default data source or an explicitly named data source. Before a data source can be used, you must declare it as a JNDI resource reference in the `web.xml` deployment descriptor.



## Context

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://launchpad.support.sap.com/#/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**



<a name="loioe5d46793bb5710148c05ee3ad01abd39__steps_mwg_p4z_vk"/>

## Procedure

1.  In the *Project Explorer* view, open the `WebContent/WEB-IN/web.xml` file.

2.  Add the following code after the `<servlet-mapping>` elements. The resource reference name is only an example; the one you use may differ.

    ```
    <resource-ref>
          <res-ref-name>jdbc/DefaultDB</res-ref-name>
          <res-type>javax.sql.DataSource</res-type>
    </resource-ref>
    
    ```

    The resource attributes denote the following:

    -   Name – the JNDI name of the resource. The Java EE Specification recommends that you declare the data source reference in the jdbc subcontext \(`jdbc/NAME`\).
    -   Type – the type of resource that is returned during the lookup.

3.  If the application uses multiple data sources, add a resource reference for each data source:

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

    -   The data source name is the JNDI name used for the lookup.
    -   The same name must be used for the schema binding.

        > ### Note:  
        > If you declare the data source reference in a jdbc subcontext, you must use the same pattern for the name of the schema binding \(`jdbc/NAME`\).


4.  Save the file.


**Related Information**  


[Create Schemas Using the Cockpit](https://help.sap.com/viewer/d4790b2de2f4429db6f3dff54e4d7b3a/Cloud/en-US/7d8402ab04ae4e47bd7c11cdff309e4f.html "Create schemas for a selected subaccount in the Neo environment.") :arrow_upper_right:

[Administering Database Schemas](https://help.sap.com/viewer/d4790b2de2f4429db6f3dff54e4d7b3a/Cloud/en-US/2040a8a60de84c09994f64f74896b18f.html "An overview of the different tasks you can perform to administer database schemas in the Neo environment.") :arrow_upper_right:

