<!-- loio7613c8c7711e1014839a8273b0e91070 -->

# Runtime for Java

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**



The SAP BTP Runtime for Java comprises the components which create the environment for provisioning and running applications on SAP BTP. The runtime is represented by Java Virtual Machine, Application Runtime Container and Compute Units. Cloud applications can interact at runtime with the containers and services via the platform APIs.



<a name="loio7613c8c7711e1014839a8273b0e91070__section_CE66D9EE57FC40D985EEA6B3C3C81289"/>

## Components

-   Java Virtual Machine

    SAP BTP infrastructure runs on Java Virtual Machines that are built and supported by SAP. Java 17 code runs on SapMachine, a build of OpenJDK released by SAP, enriched with supportability features and patched if needed for SAP products. Old Java 8 code runs on SAP's own implementation of a Java Virtual Machine - SAP Java Virtual Machine \(SAP JVM\).

    SapMachine and SAP JVM are certified Open Java Development Kits \(OpenJDK\), Java Virtual Machine and Java Development Kit \(JDK\), compliant to Java Standard Edition \(SE\) 8, 11 and 17. Technology-wise they are based on the OpenJDK. Especially SAP JVM 8 has been enhanced with a strong focus on supportability wrt. OpenJDK 8.

-   Application Runtime Container

    Applications developed on SAP BTP run on a modular and lightweight runtime container which allows them to consume standard Java EE APIs and platform services that are centrally provided and shared across the platform. SAP BTP leverages open source as a key element and Java EE 6 Web Profile as a default programming model.

-   Compute Units

    A Compute Unit is a virtualized hardware on which a SAP BTP application runs.


**Related Information**  


[Java Virtual Machine](java-virtual-machine-da030d1.md)

[Application Runtime Container](application-runtime-container-7613bd2.md)

[Supported Java APIs](supported-java-apis-e836a95.md)

