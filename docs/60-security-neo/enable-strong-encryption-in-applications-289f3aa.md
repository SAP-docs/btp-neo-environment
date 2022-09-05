<!-- loio289f3aa7d26d4507a87dd7bac62a04e2 -->

# Enable Strong Encryption in Applications

This is a deprecated procedure how to install Java Cryptography Extension \(JCE\) Unlimited Strength Jurisdiction Policy Files on SAP JVM to enable unlimited cryptography power. You do not need to use it anymore. All supported runtimes already come with a Java version that supports strong encryption.



## Prerequisites

You have the appropriate Java Cryptography Extension \(JCE\) Unlimited Strength Jurisdiction Policy Files enabling cryptography with unlimited strength.



## Context

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**



## Procedure

1.  Pack the encryption policy files \(JCE Unlimited Strength Jurisdiction Policy Files\) in the following folder of the Web application:

    `META-INF/ext_security/jre7` - for applications, running on JDK 1.7

2.  If the application consists of multiple WAR files, pack the encryption policy files in one of them.

3.  Deploy the application on SAP BTP.




## Results

The encryption policy files \(Java Cryptography Extension \(JCE\) Unlimited Strength Jurisdiction Policy Files\) will be installed on the JVM of the application prior to start. As a result, the application can use unlimited strength encryption.



The WAR file of the application must have the following file entries:

`META-INF/ext_security/jre7/local_policy.jar`

`META-INF/ext_security/jre7/US_export_policy.jar`

**Related Information**  


[Deploying and Updating Java Applications](../30-development-neo/deploying-and-updating-java-applications-e5dfbc6.md "The Java application lifecycle management (Java ALM) service for SAP BTP lets you deploy and update Java applications via console client commands, the SAP BTP cockpit, or the Java ALM REST API.")

