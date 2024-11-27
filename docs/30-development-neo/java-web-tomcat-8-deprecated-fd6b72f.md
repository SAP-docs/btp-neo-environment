<!-- loiofd6b72f17a11478e87fefe3f6ad2e30d -->

# Java Web Tomcat 8 \(Deprecated\)

Java Web Apache Tomcat 8 \(Java Web Tomcat 8\) is the next edition of the Java Web application runtime container that has all characteristics and features of its predecessor Java Web Tomcat 7.

> ### Note:  
> Since 1 January 2024, we've stopped the support for this runtime and stopped providing updates and security patches to it. This is following the [official announcement](https://tomcat.apache.org/tomcat-85-eol.html) of Apache Tomcat 8.5 end of life. Don't use it for new applications \(we recommend using [Java Web Tomcat 9](java-web-tomcat-9-41b1ee9.md) or another supported one listed in [Application Runtime Container](application-runtime-container-7613bd2.md)\).
> 
> If you have Java applications running on that runtime, migrate to Java Web Tomcat 9 as soon as possible. See [Migrating from Java Web Tomcat 8 to Java Web Tomcat 9](migrating-from-java-web-tomcat-8-to-java-web-tomcat-9-1c3c8d4.md).

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of the following technology portfolios: application development; process automation; integration; data, analytics, and enterprise planning; artificial intelligence. The platform offers users the ability to turn data into business value, compose end-to-end business processes, connect entire IT landscapes, and personalize, build and extend SAP applications. This reduces the overall total cost of ownership maintaining SAP landscapes and third-party software across end-to-end business processes.") :arrow_upper_right:.**

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

[https://jcp.org/en/jsr/detail?id=356](https://jcp.org/en/jsr/detail?id=356) 

</td>
</tr>
</table>

