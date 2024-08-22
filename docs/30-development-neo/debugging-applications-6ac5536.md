<!-- loio6ac5536ea4e143bd84e39b6fb8a140b0 -->

# Debugging Applications

After you have created a Web application and tested it locally, you may want to inspect its runtime behavior and state by debugging the application in SAP BTP.



## Context

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of the following technology portfolios: application development; process automation; integration; data, analytics, and enterprise planning; artificial intelligence. The platform offers users the ability to turn data into business value, compose end-to-end business processes, connect entire IT landscapes, and personalize, build and extend SAP applications. This reduces the overall total cost of ownership maintaining SAP landscapes and third-party software across end-to-end business processes.") :arrow_upper_right:.**

The debugger enables you to detect and diagnose errors in your application. It allows you to control the execution of your program by setting breakpoints, suspending threads, stepping through the code, and examining the contents of the variables. You can debug a servlet or a JSP file on a SAP BTP server without losing the state of your application.

> ### Note:  
> Currently, it is only possible to debug Web applications in SAP BTP that have exactly one application process \(node\).

<a name="concept_xgq_d35_rn"/>

<!-- concept\_xgq\_d35\_rn -->

## Tasks

-   [Debug Applications Locally](debug-applications-locally-bf7f7d8.md)
-   [Debug Applications on the Cloud](debug-applications-on-the-cloud-10b63fe.md)

**Related Information**  


[Profiling Applications](../50-administration-and-ops-neo/profiling-applications-8967d19.md "The SAP JVM Profiler helps you analyze resource-related problems in your Java application regardless of whether the JVM is running locally or on the cloud.")

