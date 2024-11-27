<!-- loio6ff15923ddd3401db65ee5fde26976eb -->

# Java Web Tomcat 10

Java Web Apache Tomcat 10 \(Java Web Tomcat 10\) is the next edition of the Java Web application runtime container that has all characteristics and features of its predecessor Java Web Tomcat 9.

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of the following technology portfolios: application development; process automation; integration; data, analytics, and enterprise planning; artificial intelligence. The platform offers users the ability to turn data into business value, compose end-to-end business processes, connect entire IT landscapes, and personalize, build and extend SAP applications. This reduces the overall total cost of ownership maintaining SAP landscapes and third-party software across end-to-end business processes.") :arrow_upper_right:.**

This container leverages Apache Tomcat 10.1 Web Container without modifications and also adds the already established set of SAP BTP services client APIs. It supports the Jakarta EE 10 APIs.

> ### Note:  
> The changes in the package names in the Jakarta EE 10 API from the Java EE API may require changes in the source code of your applications to be able to migrate to Java Web Tomcat 10 runtime. See [Migrating to Java Web Tomcat 10 \(from Another Runtime\)](java-web-tomcat-10-6ff1592.md#loio6ff15923ddd3401db65ee5fde26976eb__section_mhk_xkj_srb).

Java Web Tomcat 10 runtime is displayed as *neo-java-web runtime version 5.x* in the console client. See:

-   [Console Client for the Neo Environment](../50-administration-and-ops-neo/console-client-for-the-neo-environment-7613230.md)
-   [Choose Application Runtime Version](../50-administration-and-ops-neo/choose-application-runtime-version-13afe5c.md)
-   [Choose JRE Version](../50-administration-and-ops-neo/choose-jre-version-ee71c1a.md)

> ### Restriction:  
> HTTP2 protocol is not supported at SAP BTP.

> ### Note:  
> Applications that use HTTP Destination \(version 1\) API should adopt HTTP Destination \(version 2\) API.



<a name="loio6ff15923ddd3401db65ee5fde26976eb__section_drv_wtc_srb"/>

## Supported Java Versions

This runtime supports Java 17.



<a name="loio6ff15923ddd3401db65ee5fde26976eb__section_cq4_xtc_srb"/>

## Supported Jakarta EE Specifications

The Java Web Tomcat 10 application runtime container \(*neo-java-web 5.x*\) provides implementation for the following set of Jakarta EE specifications:

-   [Jakarta Servlet 6.0](https://jakarta.ee/specifications/servlet/6.0/)
-   [Jakarta JavaServer Pages \(JSP\) 3.1](https://jakarta.ee/specifications/pages/3.1/)
-   [Jakarta Expression Language \(EL\) 5.0](https://jakarta.ee/specifications/expression-language/5.0/)
-   [Jakarta Debugging Support for Other Languages 2.0](https://jakarta.ee/specifications/debugging/2.0/)
-   [Jakarta WebSocket 2.1](https://jakarta.ee/specifications/websocket/2.1/)



<a name="loio6ff15923ddd3401db65ee5fde26976eb__section_lft_sg3_vcc"/>

## Supported SAP BTP APIs

The following subset of APIs of SAP BTP services are available within Java Web Tomcat 10:

-   Document Service APIs
-   Connectivity Service APIs \(destination configuration and authentication header provider\)
-   SAP HANA service and SAP ASE service JDBC APIs
-   Security APIs



<a name="loio6ff15923ddd3401db65ee5fde26976eb__section_mhk_xkj_srb"/>

## Migrating to Java Web Tomcat 10 \(from Another Runtime\)

1.  If you application uses Java packages from the Jakarta EE specifications \(listed above\), in the source code change the imported package names from `javax.*` to `jakarta.*`. For example, change imports of `javax.servlet` to `jakarta.servlet`.
2.  Redeploy \(see [Deploying and Updating Java Applications](deploying-and-updating-java-applications-e5dfbc6.md)\) and restart the application afterwards \(see [restart command](../50-administration-and-ops-neo/restart-7c0f7a1.md) or [Start and Stop Applications](../50-administration-and-ops-neo/start-and-stop-applications-7612f03.md)\).

If you have questions or encounter problems, create a ticket in component *BC-NEO-RT-JAV*. See [Getting Support, Neo Environment](../70-getting-support-neo/getting-support-neo-environment-fc2bf6a.md).

