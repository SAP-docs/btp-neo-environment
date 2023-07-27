<!-- loio269860ae2d3745f086008b0a5f7d49b5 -->

# Alternative Tools for Enabling the SQL Trace

In addition to using the cockpit, you can also enable the SQL trace from the Eclipse IDE, and using the console client. Whichever tool you use, you need to set the log level of the logger `com.sap.core.persistence.sql.trace` to the log level *DEBUG*.

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://launchpad.support.sap.com/#/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**



## Console Client

You can use the console client to set the log level as a logging property for one or more loggers. To do so, use the command `neo set-log-level` with the log parameters `logger <logger_name>` and `level <log_level>`.

See [Using Logs in the Console Client](https://help.sap.com/viewer/f88a032109f0429caea276fc6e3a95f9/Cloud/en-US/e4fd83c5bb5710149b1e94f127f108e4.html "") :arrow_upper_right:

**Related Information**  


[Deploy on the Cloud with the Console Client](deploy-on-the-cloud-with-the-console-client-030863c.md "Deploying an application publishes it to SAP BTP. During deploy, you can define various specifics of the deployed application using the deploy command optional parameters.")

