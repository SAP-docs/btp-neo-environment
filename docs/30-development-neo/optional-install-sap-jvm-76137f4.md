<!-- loio76137f42711e1014839a8273b0e91070 -->

# \(Optional\) Install SAP JVM

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**



<a name="loio76137f42711e1014839a8273b0e91070__section_CD05905FEAF64370808F6949C1323254"/>

## Context

SAP BTP infrastructure runs on SAP's own implementation of a Java Virtual Machine - SAP Java Virtual Machine \(JVM\).

SAP JVM is a certified Java Virtual Machine and Java Development Kit \(JDK\), compliant to Java Standard Edition \(SE\) 8. Technology-wise it is based on the OpenJDK and has been enhanced with a strong focus on supportability and reliability. One example of these enhancements is the SAP JVM Profiler. The SAP JVM Profiler is a tool that helps you analyze the resource consumption of a Java application running on theSAP BTP local runtime. You can use it to profile simple stand-alone Java programs or complex enterprise applications.

Customer support is provided directly by SAP for the full maintenance period of SAP applications that use the SAP JVM. For more information, see [Java Virtual Machine](java-virtual-machine-da030d1.md)

Follow the steps below to install an SAP Java Virtual Machine.

> ### Note:  
> This is an optional procedure. You can also run your local server for SAP BTP on a standard JDK platform, that is an Oracle JVM. SAP JVM, however, is a prerequisite for local profiling with the SAP JVM Profiler.



<a name="loio76137f42711e1014839a8273b0e91070__section_361F6AC51627447A9DDC0A5680AD24EB"/>

## Procedure

1.  Open [https://tools.hana.ondemand.com/\#cloud](https://tools.hana.ondemand.com/#cloud)
2.  From the *SAP JVM* section, download the SAP JVM archive file compatible to your operating system and save it to your local file system.
3.  Extract the archive file.

> ### Note:  
> If you use Windows as your operating system, you need to install the Visual C++ 2013 Runtime prior to using SAP JVM. The installation package for the Visual C++ 2013 Runtime can be obtained from Microsoft. Download and install *vcredist\_x64.exe* from the following site: [https://www.microsoft.com/de-de/download/details.aspx?id=40784](https://www.microsoft.com/de-de/download/details.aspx?id=40784). Even if you already have a different version of Visual C++ Runtime, for example Visual C++ 2015, you still need to install Visual C++ 2013 Runtime prior to using SAP JVM. See SAP Note [2676219](https://launchpad.support.sap.com/#/notes/2676219).

**Related Information**  




