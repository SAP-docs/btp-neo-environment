<!-- loio1c3c8d4b5dd34caba087fadd5fba99a1 -->

# Migrating from Java Web Tomcat 8 to Java Web Tomcat 9

Migrate an application running on the deprecated Java runtime Java Web Tomcat 8 to Java Web Tomcat 9.



The Java Web Tomcat 8 runtime is deprecated following the [official announcement](https://tomcat.apache.org/tomcat-85-eol.html) of Apache Tomcat 8.5 end of life. After the end of 2023, we stop providing updates and security patches to it.



<a name="loio1c3c8d4b5dd34caba087fadd5fba99a1__section_d5g_xmf_r4b"/>

## Migration Steps

1.  Generally, you don't need to change the application itself. The only exception is if you're using Cross-Site Request Forgery \(CSRF\) custom header protection based on `com.sap.core.js.csrf.RestCsrfPreventionFilter`. In such case, you need to switch to `org.apache.catalina.filters.RestCsrfPreventionFilter`.

    > ### Tip:  
    > Check the `web.xml` file of the application to see if it uses custom header protection filter.

    For more information, see [Using Custom Header Protection](../60-security-neo/using-custom-header-protection-3756f3f.md).

2.  Redeploy it \(see [Deploying and Updating Java Applications](deploying-and-updating-java-applications-e5dfbc6.md)\).

    > ### Tip:  
    > You can use the following steps in the SAP BTP cockpit:
    > 
    > 1.  Navigate to your application \(*cockpit* \> *<your global account\>* \> *<your subaccount\>* \> *Applications* \> *Java* section\).
    > 2.  Choose the *Update* button for your application.
    > 3.  In the dialog that appears, provide the application WAR file.
    > 4.  In the runtime dropdown menu, choose the option *Java Web Tomcat 9*.

3.  Restart it \(see [Start and Stop Applications](../50-administration-and-ops-neo/start-and-stop-applications-7612f03.md) or [restart](../50-administration-and-ops-neo/restart-7c0f7a1.md) console command\).

    > ### Tip:  
    > For productive applications, we recommend using [Update Applications with Zero Downtime](../50-administration-and-ops-neo/update-applications-with-zero-downtime-a10f6c2.md) or [rolling-update](../50-administration-and-ops-neo/rolling-update-3f5d412.md), both of which are performed only from command line.
    > 
    > In both cases, pass the optional parameter `--runtime-version 4` in the `deploy` command or the `rolling-update` command respectively. This parameter performs the update of the runtime.


**Related Information**  


[Java Web Tomcat 8 \(Deprecated\)](java-web-tomcat-8-deprecated-fd6b72f.md "Java Web Apache Tomcat 8 (Java Web Tomcat 8) is the next edition of the Java Web application runtime container that has all characteristics and features of its predecessor Java Web Tomcat 7.")

[Java Web Tomcat 9](java-web-tomcat-9-41b1ee9.md "Java Web Apache Tomcat 9 (Java Web Tomcat 9) is the next edition of the Java Web application runtime container that has all characteristics and features of its predecessor Java Web Tomcat 8.")

