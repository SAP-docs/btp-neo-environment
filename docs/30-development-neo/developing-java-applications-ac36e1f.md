<!-- loioac36e1fc0f634c0caa99916b3bd6b446 -->

# Developing Java Applications

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**

You can develop applications for SAP BTP just like for any application server. Inside, you can embed the usage of the services provided by the platform.



<a name="loioac36e1fc0f634c0caa99916b3bd6b446__section_N1001C_N10011_N10001"/>

## Development Environment

SAP BTP development environment is designed and built to optimize the process of development and deployment.

For Java applications, you can choose between three types of SAP BTP SDK for Neo environment:

-   SDK for Java Web - provides support for some of the standard Java EE 7 APIs \(Servlet, JSP, EL, Websocket\)
-   SDK for Java Web Tomcat 8 - provides support for some of the standard Java EE 7 APIs \(Servlet, JSP, EL, Websocket\)
-   SDK for Java EE 7 Web Profile - certified to support Java EE 7 Web Profile APIs
-   SDK for Java Web Tomcat 9 - provides support for some of the standard Java EE 8 APIs \(Servlet, JSP, EL, Websocket\)

For more information, see [Development Environment](development-environment-7613405.md)



<a name="loioac36e1fc0f634c0caa99916b3bd6b446__section_N1003B_N10011_N10001"/>

## Use Java EE 7 Web Profile

SAP BTP is Java EE 7 Web Profile certified so you can extend the basic functionality of your application with Java EE 7 Web Profile technologies. If you are working with the SDK for Java EE 7 Web Profile, you can equip the basic application with additional Java EE features, such as EJB, CDI, JTA.



<a name="loioac36e1fc0f634c0caa99916b3bd6b446__section_N10048_N10011_N10001"/>

## Use Services and Utilities

Create a fully-fledged application benefiting from the capabilities and services provided by SAP BTP. In your application, you can choose to use:

-   [Authentication](../60-security-neo/securing-java-applications-e80af38.md) - by default, SAP BTP is configured to use SAP ID service as identity provider \(IdP\), as specified in SAML 2.0. You can configure trust to your custom IdP, to provide access to the cloud using your own user database.

-   [UI development toolkit for HTML5 \(SAPUI5\)](https://sapui5.hana.ondemand.com/sdk/#docs/guide/99ac68a5b1c3416ab5c84c99fefa250d.html) - use the platform's official UI framework.

-   [Connectivity Service](https://help.sap.com/viewer/b865ed651e414196b39f8922db2122c7/Cloud/en-US/e5c9867dbb571014957ef9d7a8846b1c.html "Connect your Java cloud applications to the Internet, make cloud-to-on-premise connections to SAP or non-SAP systems, or send and fetch e-mail.") :arrow_upper_right: - use it to connect Web applications to Internet, make on-demand to on-premise connections to Java and ABAP on-premise systems and configure destinations to send and fetch e-mail.

-   [Logging](https://help.sap.com/viewer/ee8e8a203e024bbb8c8c2d03fce527dc/Cloud/en-US/e6e8ccd3bb571014b6afdc54744eef4d.html) - implement a logging API if you want to have logs produced at runtime.

-   [Cloud Environment Variables](using-cloud-environment-variables-d553d78.md)- use system environment variables that identify the runtime environment of the application.




<a name="loioac36e1fc0f634c0caa99916b3bd6b446__section_N1007A_N10011_N10001"/>

## Deploy

First, deploy and test the ready application on the local runtime and then make it available on SAP BTP.

For more information, see [Deploying and Updating Java Applications](deploying-and-updating-java-applications-e5dfbc6.md)

You can speed up your development by applying and activating new changes on the already running application. Use the hot-update command.

For more information, see [hot-update](../50-administration-and-ops-neo/hot-update-7ae6493.md)



<a name="loioac36e1fc0f634c0caa99916b3bd6b446__section_N10087_N10011_N10001"/>

## Manage

Manage all applications deployed in your account from a single dedicated user interface - SAP BTP cockpit.



<a name="loioac36e1fc0f634c0caa99916b3bd6b446__section_N10094_N10011_N10001"/>

## Monitor

Configure checks and monitor the state of your applications.

For more information, see [Java: Application Operations](../50-administration-and-ops-neo/java-application-operations-76f6dcf.md)

