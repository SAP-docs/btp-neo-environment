<!-- loiofd6b72f17a11478e87fefe3f6ad2e30d -->

# Java Web Tomcat 8

Java Web Apache Tomcat 8 \(Java Web Tomcat 8\) is the next edition of the Java Web application runtime container that has all characteristics and features of its predecessor Java Web Tomcat 7.

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**

This container leverages Apache Tomcat 8.5 Web container without modifications and also adds the already established set of SAP BTP services client APIs. Applications running in the Apache Tomcat 8.5 Web container are portable to Java Web Tomcat 8. Existing applications running in Java Web and Java Web Tomcat 7 application runtime containers can run unmodified in Java Web Tomcat 8 in case they share the same set of enabled APIs.

> ### Restriction:  
> HTTP2 protocol is not supported at SAP BTP.

The supported Java version for Java Web Tomcat 8 is Java 8.

The current version of Java Web Tomcat 8 application runtime container \(neo-java-web 3.x\) provides implementation for the following set of Java Specification Requests \(JSRs\) defined specifications:


<table>
<tr>
<th valign="top">

Specification version



</th>
<th valign="top">

JSR



</th>
</tr>
<tr>
<td valign="top">

Servlet 3.1



</td>
<td valign="top">

[JSR - 340](https://jcp.org/aboutJava/communityprocess/final/jsr340/index.html)



</td>
</tr>
<tr>
<td valign="top">

JavaServer Pages \(JSP\) 2.3



</td>
<td valign="top">

[JSR - 245](https://jcp.org/aboutJava/communityprocess/mrel/jsr245/index2.html) 



</td>
</tr>
<tr>
<td valign="top">

Expression Language \(EL\) 3.0



</td>
<td valign="top">

[JSR - 341](https://jcp.org/aboutJava/communityprocess/final/jsr341/index.html) 



</td>
</tr>
<tr>
<td valign="top">

Debugging Support for Other Languages 1.0



</td>
<td valign="top">

[JSR - 45](https://jcp.org/en/jsr/detail?id=45) 



</td>
</tr>
<tr>
<td valign="top">

Java API for WebSocket



</td>
<td valign="top">

[JSR - 356](https://jcp.org/en/jsr/detail?id=356) 



</td>
</tr>
</table>

The following subset of APIs of SAP BTP services are available within Java Web Tomcat 8: document service APIs, mail service APIs, connectivity service APIs \(destination configuration and authentication header provider\), SAP HANA service and SAP ASE service JDBC APIs, and security APIs.

**Migrating to Java Web Tomcat 8 \(from Another Runtime\)**

1.  If required, change the application.

    In the general case, this step is **not** required.

    An exception are applications using the [HTTP Destination API](https://help.sap.com/viewer/b865ed651e414196b39f8922db2122c7/Cloud/en-US/462dbffef4614044b5c727c9de37672e.html "All connectivity API packages are visible by default from all Web applications. Applications can consume the destinations via a JNDI lookup.") :arrow_upper_right: \(`com.sap.core.connectivity.api.http.HttpDestination`\). In such case, you have to package `HttpDestination` in your application as library. Additionally, you may need to change the application code or destinations. For more information, see [HttpDestination (Version 2)](https://help.sap.com/viewer/b865ed651e414196b39f8922db2122c7/Cloud/en-US/c2a0d33bbc464b8fae30fed707ae9034.html "Use the current HttpDestination library version available for the Connectivity service.") :arrow_upper_right:.

2.  Redeploy \(see [Deploying and Updating Java Applications](deploying-and-updating-java-applications-e5dfbc6.md)\) and restart the application afterwards \(see [restart command](../50-administration-and-ops-neo/restart-7c0f7a1.md) or [Start and Stop Applications](../50-administration-and-ops-neo/start-and-stop-applications-7612f03.md)\).

    If you have questions or problems, create a ticket in component *BC-NEO-RT-JAV*.


