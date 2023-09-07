<!-- loiof177a15bab8c47168cbcf471b7726f78 -->

# Java EE 7 Web Profile TomEE 7

The Java EE 7 Web Profile TomEE 7 provides implementation of the Java EE 7 Web Profile specification.

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**

> ### Restriction:  
> Java 7 for Java EE7 Web Profile TomEE7 runtime is deprecated. If you are running Java applications on that runtime with that Java version, migrate to Java 8 on the same runtime.
> 
> To do this, redeploy the applications or update their Java version. If you redeploy the applications, specify explicitly Java 8 as the version \(see [Deploying and Updating Java Applications](deploying-and-updating-java-applications-e5dfbc6.md)\). In both cases, restart the applications afterwards \(see [restart command](../50-administration-and-ops-neo/restart-7c0f7a1.md)\).

The current version of Java EE 7 Web Profile TomEE application runtime container \(neo-javaee7-wp 1.x\) provides implementation for the following Java Specification Requests \(JSRs\):


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

Java EE 7 \(Web Profile\)



</td>
<td valign="top">

[JSR - 342](https://jcp.org/en/jsr/detail?id=342)



</td>
</tr>
<tr>
<td valign="top">

Servlet 3.1



</td>
<td valign="top">

[JSR - 340](http://jcp.org/en/jsr/detail?id=340)



</td>
</tr>
<tr>
<td valign="top">

JavaServer Pages \(JSP\) 2.3



</td>
<td valign="top">

[JSR - 245](http://jcp.org/en/jsr/detail?id=245)



</td>
</tr>
<tr>
<td valign="top">

Expression Language \(EL\) 3.0



</td>
<td valign="top">

[JSR - 341](http://jcp.org/en/jsr/detail?id=341)



</td>
</tr>
<tr>
<td valign="top">

Debugging Support for Other Languages 1.0



</td>
<td valign="top">

[JSR - 45](http://jcp.org/en/jsr/detail?id=45)



</td>
</tr>
<tr>
<td valign="top">

Standard Tag Library for JavaServer Pages \(JSTL\) 1.2



</td>
<td valign="top">

[JSR - 52](http://www.jcp.org/en/jsr/detail?id=52)



</td>
</tr>
<tr>
<td valign="top">

Java API for RESTful Web Services \(JAX-RS\) 2.0



</td>
<td valign="top">

[JSR - 339](http://jcp.org/en/jsr/detail?id=339)



</td>
</tr>
<tr>
<td valign="top">

JavaServer Faces \(JSF\) 2.2



</td>
<td valign="top">

[JSR - 344](http://jcp.org/en/jsr/detail?id=344)



</td>
</tr>
<tr>
<td valign="top">

Common Annotations for Java Platform 1.2



</td>
<td valign="top">

[JSR - 250](http://jcp.org/en/jsr/detail?id=250)



</td>
</tr>
<tr>
<td valign="top">

Enterprise JavaBeans \(EJB\) Lite 3.2

> ### Note:  
> EJB Timer Servce is also supported \(although not part of the EJB Lite specification\).



</td>
<td valign="top">

[JSR - 345](http://jcp.org/en/jsr/detail?id=345)



</td>
</tr>
<tr>
<td valign="top">

Java Transaction API \(JTA\) 1.2



</td>
<td valign="top">

[JSR - 907](http://jcp.org/en/jsr/detail?id=907)



</td>
</tr>
<tr>
<td valign="top">

Java Persistence API \(JPA\) 2.1



</td>
<td valign="top">

[JSR - 338](http://jcp.org/en/jsr/detail?id=338)



</td>
</tr>
<tr>
<td valign="top">

Dependency Injection for Java 1.0



</td>
<td valign="top">

[JSR - 330](http://www.jcp.org/en/jsr/detail?id=330)



</td>
</tr>
<tr>
<td valign="top">

Contexts and Dependency Injection for Java EE platform 1.1



</td>
<td valign="top">

[JSR - 346](http://jcp.org/en/jsr/detail?id=346)



</td>
</tr>
<tr>
<td valign="top">

Bean Validation 1.1



</td>
<td valign="top">

[JSR - 349](http://jcp.org/en/jsr/detail?id=349)



</td>
</tr>
<tr>
<td valign="top">

Managed Beans 1.0



</td>
<td valign="top">

[JSR - 316](http://jcp.org/en/jsr/detail?id=316)



</td>
</tr>
<tr>
<td valign="top">

Interceptors 1.2



</td>
<td valign="top">

[JSR - 345](http://jcp.org/en/jsr/detail?id=345)



</td>
</tr>
</table>

Source: [JSR-342](http://jcp.org/en/jsr/detail?id=342) \(Web Profile\), Chapter 2: Web Profile Definition

For more information about the differences between EJB 3.2 and EJB 3.2 Lite, see the Java EE 7 specification, JSR 345: Enterprise JavaBeans, section 21.1.



<a name="loiof177a15bab8c47168cbcf471b7726f78__section_6E56F5A283004681B3B03A5F19768C90"/>

## Development Process

The Java EE 7 Web Profile TomEE 7 enables you to easily create your applications for SAP BTP.



<a name="loiof177a15bab8c47168cbcf471b7726f78__section_kkx_tmh_smb"/>

## Migrating to Java EE 7 Web Profile TomEE 7 \(from Another Runtime\)

1.  If required, change the application.

    In the general case, this step is **not** required.

    An exception are applications using the [HTTP Destination API](https://help.sap.com/viewer/b865ed651e414196b39f8922db2122c7/Cloud/en-US/462dbffef4614044b5c727c9de37672e.html "All connectivity API packages are visible by default from all Web applications. Applications can consume the destinations via a JNDI lookup.") :arrow_upper_right: \(`com.sap.core.connectivity.api.http.HttpDestination`\). In such case, you have to package `HttpDestination` in your application as library. Additionally, you may need to change the application code or destinations. For more information, see [HttpDestination (Version 2)](https://help.sap.com/viewer/b865ed651e414196b39f8922db2122c7/Cloud/en-US/c2a0d33bbc464b8fae30fed707ae9034.html "Use the current HttpDestination library version available for the Connectivity service.") :arrow_upper_right:.

2.  Redeploy \(see [Deploying and Updating Java Applications](deploying-and-updating-java-applications-e5dfbc6.md)\) and restart the application afterwards \(see [restart command](../50-administration-and-ops-neo/restart-7c0f7a1.md) or [Start and Stop Applications](../50-administration-and-ops-neo/start-and-stop-applications-7612f03.md)\).

    If you have questions or problems, create a ticket in component *BC-NEO-RT-JAV*.




<a name="loiof177a15bab8c47168cbcf471b7726f78__section_6426FC0C57E344BA97905F08109309ED"/>

## Related Information

[Java EE at a Glance](http://www.oracle.com/technetwork/java/javaee/overview/index.html) 

[Supported Java APIs](supported-java-apis-e836a95.md)

