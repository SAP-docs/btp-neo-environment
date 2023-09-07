<!-- loio841e3eaf32fa4bc3becc6ccd50758278 -->

# Building Samples with Maven

All samples provided can be built with Apache Maven. The Maven build shows how a headless build and test can be completely automated.



<a name="loio841e3eaf32fa4bc3becc6ccd50758278__context_N10015_N10012_N10001"/>

## Context

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**

The build and test does the following:

-   Builds a Java Web application based on the SAP BTP API
-   Demonstrates how to run rudimentary unit tests \(not available in all samples\)
-   Installs, starts, waits for, and stops the local server runtime
-   Deploys the application to the local server runtime and runs the integration test
-   Starts, waits for, and stops the cloud server runtime
-   Deploys the application to the cloud server runtime and runs the integration test

**Related Information**  


[Build Samples from the Command Line](build-samples-from-the-command-line-ad423da.md "You can use the Apache Maven command line tool to run local and cloud integration tests for any of the SDK samples.")

[Building Java Web Applications with Maven](http://scn.sap.com/community/developer-center/cloud-platform/blog/2014/05/27/building-java-applications-with-maven)

[Working with the "Neo" Maven Plugin](http://scn.sap.com/community/developer-center/cloud-platform/blog/2014/05/27/working-with-the-neo-maven-plugin)

