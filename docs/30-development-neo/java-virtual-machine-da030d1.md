<!-- loioda030d10d97610149defa1084cb0b2f1 -->

# Java Virtual Machine

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**

SAP BTP infrastructure runs on SAP's own implementation of a Java Virtual Machine - SAP Java Virtual Machine \(JVM\).

SAP JVM is a certified Java Virtual Machine and Java Development Kit \(JDK\), compliant to Java Standard Edition \(SE\) 8. Technology-wise it is based on the OpenJDK and has been enhanced with a strong focus on supportability and reliability. One example of these enhancements is the SAP JVM Profiler. The SAP JVM Profiler is a tool that helps you analyze the resource consumption of a Java application running on theSAP BTP local runtime. You can use it to profile simple stand-alone Java programs or complex enterprise applications.



<a name="loioda030d10d97610149defa1084cb0b2f1__section_B81F8E8CBFA642E8A33E1B7D2A0FF3F3"/>

## SAP JVM

The SAP JVM is a standard compliant certified JDK, supplemented by additional supportability and developer features and extensive monitoring and tracing information. All these features are designed as interactive, on-demand facilities of the JVM with minimal performance impact. They can be switched on and off without having to restart the JVM \(or the application server that uses the JVM\).



<a name="loioda030d10d97610149defa1084cb0b2f1__section_DFC4BF67D4AA46C5B293957FF2436B1A"/>

## Supportability and Developer Features



<a name="loioda030d10d97610149defa1084cb0b2f1__section_DBD542C7EB864ABF8B83711CFEE4185E"/>

## Debugging on Demand

With SAP JVM debugging on demand, Java developers can activate and deactivate Java debugging directly – there is no need to start the SAP JVM \(or the application server on top of it\) in a special mode. Java debugging in the SAP JVM can be activated and deactivated using the *jvmmon tool*, which is part of the SAP JVM delivery. This feature does not lower performance if debugging is turned off. The SAP JVM JDK is delivered with full source code providing debugging information, making Java debugging even more convenient.



<a name="loioda030d10d97610149defa1084cb0b2f1__section_0E69FD1DFC324767909F6FD921D3610B"/>

## Profiling

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



<a name="loioda030d10d97610149defa1084cb0b2f1__section_5C42D43F888E483F948CBADBB60B9110"/>

## Extensive Monitoring and Tracing Information

The SAP JVM provides comprehensive statistics about threads, memory consumption, garbage collection, and I/O activities. For solving issues with SAP JVM, a number of traces may be enabled on demand. They provide additional information and insight into integral VM parts such as the class loading system, the garbage collection algorithms, and I/O. The traces in the SAP JVM can be switched on and off using the *jvmmon tool*, which is part of the SAP JVM delivery.



<a name="loioda030d10d97610149defa1084cb0b2f1__section_5EAD7C4E3AC241DB8EE9C62F73518080"/>

## Further Information

Critical Java exceptions \(such as NullPointerException, ClassCastException, NoClassDefFoundError, or OutOfMemoryError\) provide additional information and further details to help identify the reason for an exception.

Thread dumps not only contain a Java execution stack trace, but also information about monitors or locks, consumed CPU and memory resources, I/O activities, and a description of communication partners \(in the case of network communication\).

For more information about Java SE Technologies in SAP Products, see [2700275](https://launchpad.support.sap.com/#/notes/2700275).

**Related Information**  


[\(Optional\) Install SAP JVM](optional-install-sap-jvm-76137f4.md)





