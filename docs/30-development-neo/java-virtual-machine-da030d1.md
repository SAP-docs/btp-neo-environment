<!-- loioda030d10d97610149defa1084cb0b2f1 -->

# Java Virtual Machine

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://launchpad.support.sap.com/#/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**

SAP BTP infrastructure runs on Java Virtual Machines that are built and supported by SAP. Java 17 code runs on SapMachine, a build of OpenJDK released by SAP, enriched with supportability features and patched if needed for SAP products. Old Java 8 code runs on SAP's own implementation of a Java Virtual Machine - SAP Java Virtual Machine \(SAP JVM\).

SapMachine and SAP JVM are certified Open Java Development Kits \(OpenJDK\), Java Virtual Machine and Java Development Kit \(JDK\), compliant to Java Standard Edition \(SE\) 8, 11 and 17. Technology-wise they are based on the OpenJDK. Especially SAP JVM 8 has been enhanced with a strong focus on supportability with regard to OpenJDK 8. Many of these enhancements were added by SAP to OpenJDK 17.



<a name="loioda030d10d97610149defa1084cb0b2f1__section_zrv_pfp_rvb"/>

## SapMachine

SapMachine is a standard compliant certified OpenJDK supplemented by additional supportability and developer features. OpenJDK 17 already contain many improvements of legacy SAP JVM 8 over OpenJDK 8. Where these features are added only to later versions of OpenJDK, they are backported to SapMachine 17 to make them available to SAP BTP. For example, “JEP 358 Helpful NullPointerExceptions” is implemented in SapMachine 11 and 17, but in OpenJDK it is only available starting at OpenJDK 14.

**Supportability and Developer Features**

-   **Debugging on Demand**

    With SapMachine debugging on demand, Java developers can activate and deactivate debugging the JVM directly – there is no need to start the JVM \(or the application server on top of it\) in a special mode. Debugging in SapMachine can be activated and deactivated using the *jcmd* tool, which is part of the delivery. This feature does not lower performance if debugging is turned off. The SapMachine JDK is delivered with full source code providing debugging information, making debugging even more convenient.

-   **Extensive Monitoring and Tracing Information**

    SapMachine and recent OpenJDK versions provide comprehensive statistics about threads, memory consumption, garbage collection, and I/O activities. For solving issues with SapMachine, a number of traces may be enabled on demand. They provide information and insight into integral VM parts such as metaspace, the garbage collection algorithms, or underlying system virtualization. The traces can be switched on and off using the *jcmd* tool, which is part of the SapMachine delivery.




<a name="loioda030d10d97610149defa1084cb0b2f1__section_akf_xgp_rvb"/>

## SAP JVM

The SAP JVM is a standard compliant certified JDK, supplemented by additional supportability and developer features like debugging on demand and extensive monitoring and tracing information. All these features are designed as interactive, on-demand facilities of the JVM with minimal performance impact. They can be switched on and off without having to restart the JVM \(or the application server that uses the JVM\) using the jvmmon tool. Many of these features nowadays are available in OpenJDK and all derived builds, first of all SapMachine.

In addition, SAP JVM offers a proprietary profiling infrastructure:

**Profiling**

To address the root cause of all performance and memory problems, the SAP JVM comes with the SAP JVM Profiler, a powerful tool that supports the developer in identifying runtime bottlenecks and reducing the memory footprint. Profiling can be enabled on-demand without VM configuration changes and works reliably even for very large Java applications.

The user interface – the SAP JVM Profiler – can be easily integrated into any Eclipse-based environment by using the established plug-in installation system of the Eclipse platform. It allows you to connect to a running SAP JVM and analyze collected profiling data in a graphical manner. The profiler plug-in provides a new perspective similar to the debug and Java perspective.

A number of profiling traces can be enabled or disabled at any point in time, resulting in snapshots of profiling information for the exact points of interest. The SAP JVM Profiler helps with the analysis of this information and provides views of the collected data with comprehensive filtering and navigation facilities.

The profiling traces provided address the following use cases:

-   Memory Allocation Analysis – investigates the memory consumption of your Java application and finds allocation hotspots
-   Performance Analysis – investigates the runtime performance of your application and finds expensive Java methods
-   Network Trace - analyzes the network traffic
-   File I/O Trace - provides information about file operations
-   Synchronization Trace - detects synchronization issues within your application
-   Method Parameter Trace – yields detailed information about individual method calls including parameter values and invocation counts
-   Profiling Lifecycle Information – a lightweight monitoring trace for memory consumption, CPU load, and GC events.

For more information about Java SE Technologies in SAP Products, see [2700275](https://launchpad.support.sap.com/#/notes/2700275).

**Related Information**  




