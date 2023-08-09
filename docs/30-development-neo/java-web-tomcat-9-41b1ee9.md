<!-- loio41b1ee9f59ad4e9b88bfedae360d421e -->

# Java Web Tomcat 9

Java Web Apache Tomcat 9 \(Java Web Tomcat 9\) is the next edition of the Java Web application runtime container that has all characteristics and features of its predecessor Java Web Tomcat 8.

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://launchpad.support.sap.com/#/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**

This container leverages Apache Tomcat 9 Web container without modifications and also adds the already established set of SAP BTP services client APIs. Applications running in the Apache Tomcat 9 Web container are portable to Java Web Tomcat 9. Existing applications running in Java Web Tomcat 7 and Java Web Tomcat 8 application runtime containers can run unmodified in Java Web Tomcat 9 in case they share the same set of enabled APIs.

Java Web Tomcat 9 runtime is displayed as *neo-java-web runtime version 4.x* in the console client. See:

-   [Console Client for the Neo Environment](../50-administration-and-ops-neo/console-client-for-the-neo-environment-7613230.md)
-   [Choose Application Runtime Version](../50-administration-and-ops-neo/choose-application-runtime-version-13afe5c.md)
-   [Choose JRE Version](../50-administration-and-ops-neo/choose-jre-version-ee71c1a.md)

> ### Restriction:  
> HTTP2 protocol is not supported at SAP BTP.

> ### Note:  
> Applications that use HTTP Destination \(version 1\) API should adopt HTTP Destination \(version 2\) API.



<a name="loio41b1ee9f59ad4e9b88bfedae360d421e__section_drv_wtc_srb"/>

## Supported Java Versions


<table>
<tr>
<th valign="top">

Java version



</th>
<th valign="top">

Description



</th>
</tr>
<tr>
<td valign="top">

Java 8



</td>
<td valign="top">

Default for all versions of Java Web Tomcat 9 runtime.



</td>
</tr>
<tr>
<td valign="top">

Java 17



</td>
<td valign="top">

Available in versions **4.16 or higher** of Java Web Tomcat 9 runtime.

To use this Java version, deploy your application in one of the following ways:

-   In the Neo console client, use the `deploy` command with parameter `--java-version 17`. See [deploy](../50-administration-and-ops-neo/deploy-937db4f.md).
-   In the SAP BTP cockpit, use *JRE 17* for the *JVM Version* option of the deploy application dialog \(*<subaccount level in the cockpit\>* \> *Applications* \> *Java Applications* \> *Deploy Application*\). See [Deploy on the Cloud with the Cockpit](deploy-on-the-cloud-with-the-cockpit-abded96.md).



</td>
</tr>
<tr>
<td valign="top">

Java 11



</td>
<td valign="top">

Available in versions **4.15 or lower** of Java Web Tomcat 9 runtime. Replaced by Java 17 in the higher versions.



</td>
</tr>
</table>



<a name="loio41b1ee9f59ad4e9b88bfedae360d421e__section_tj3_1cd_srb"/>

## Migrating from Java 11 to Java 17

1.  Pin your application to the older runtime version \(4.15\) with Java 11 until you are ready to migrate to Java 17.

    In the console client, use the deploy command with additional parameters:`--runtime neo-java-web --runtime-version 4.15 --java-version 11`. See [deploy](../50-administration-and-ops-neo/deploy-937db4f.md).

2.  Test the application to make sure it works as expected.
3.  Update your application using `--java version 17` as deploy parameter in the console client, or use*JRE 17* as the *JVM Version* in the SAP BTP cockpit \(see [Deploy on the Cloud with the Cockpit](deploy-on-the-cloud-with-the-cockpit-abded96.md)\).



<a name="loio41b1ee9f59ad4e9b88bfedae360d421e__section_cq4_xtc_srb"/>

## Supported Java Specification Requests \(JSRs\)

The current version of Java Web Tomcat 9 application runtime container \(neo-java-web 4.x\) provides implementation for the following set of Java Specification Requests \(JSRs\):


<table>
<tr>
<th valign="top">

Specification Version



</th>
<th valign="top">

JSR



</th>
</tr>
<tr>
<td valign="top">

Servlet 4.0



</td>
<td valign="top">

[JSR - 369](https://jcp.org/aboutJava/communityprocess/final/jsr369/index.html)



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

The following subset of APIs of SAP BTP services are available within Java Web Tomcat 9: document service APIs, mail service APIs, connectivity service APIs \(destination configuration and authentication header provider\), SAP HANA service and SAP ASE service JDBC APIs, and security APIs.



<a name="loio41b1ee9f59ad4e9b88bfedae360d421e__section_mhk_xkj_srb"/>

## Migrating to Java Web Tomcat 9 \(from Another Runtime\)

Redeploy \(see [Deploying and Updating Java Applications](deploying-and-updating-java-applications-e5dfbc6.md)\) and restart the application afterwards \(see [restart command](../50-administration-and-ops-neo/restart-7c0f7a1.md) or [Start and Stop Applications](../50-administration-and-ops-neo/start-and-stop-applications-7612f03.md)\).

If you have questions or problems, create a ticket in component *BC-NEO-RT-JAV*.

