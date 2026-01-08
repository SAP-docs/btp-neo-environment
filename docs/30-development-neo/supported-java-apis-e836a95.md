<!-- loioe836a95cbb571014b3c4c422837fcde4 -->

# Supported Java APIs

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/docs/btp/sap-business-technology-platform/sap-business-technology-platform?version=Cloud) .**





When you develop applications that run on SAP BTP, you can rely on certain Java EE standard APIs. These APIs are provided with the runtime of the platform. They are based on standards and are backward compatible as defined in the Java EE specifications. Currently, you can make use of the APIs listed below:

-   javax.activation
-   javax.annotation
-   javax.el
-   javax.mail
-   javax.persistence
-   javax.servlet
-   javax.servlet.jsp
-   javax.servlet.jsp.jstl
-   javax.websocket

You can also make use of the following third-party APIs:

-   org.slf4j.Logger
-   org.slf4j.LoggerFactory

If you are using the SAP BTP SDK for Java EE 6 WebProfile, you can have access to the following Java EE APIs as well:

-   javax.faces
-   javax.validation
-   javax.inject
-   javax.ejb
-   javax.interceptor
-   javax.transaction
-   javax.enterprise
-   javax.decorator

The table below summarizes the Java Request Specifications \(JSRs\) supported in the two SAP BTP SDKs for Java.


<table>
<tr>
<th valign="top">

Supported Java EE 6 Specification

</th>
<th valign="top">

SDK for Java Web

</th>
<th valign="top">

SDK for Java EE 6 WebProfile

</th>
</tr>
<tr>
<td valign="top">

Servlet 3.0

</td>
<td valign="top">

yes

</td>
<td valign="top">

yes

</td>
</tr>
<tr>
<td valign="top">

JavaServer Pages \(JSP\) 2.2

</td>
<td valign="top">

yes

</td>
<td valign="top">

yes

</td>
</tr>
<tr>
<td valign="top">

Expression Language \(EL\) 2.2

</td>
<td valign="top">

yes

</td>
<td valign="top">

yes

</td>
</tr>
<tr>
<td valign="top">

Debugging Support for Other Languages 1.0

</td>
<td valign="top">

yes

</td>
<td valign="top">

yes

</td>
</tr>
<tr>
<td valign="top">

Standard Tag Library for JavaServer Pages \(JSTL\) 1.2

</td>
<td valign="top">

yes

</td>
<td valign="top">

yes

</td>
</tr>
<tr>
<td valign="top">

Common Annotations for Java Platform 1.1

</td>
<td valign="top">

yes

</td>
<td valign="top">

yes

</td>
</tr>
<tr>
<td valign="top">

Java API for WebSocket

</td>
<td valign="top">

yes

</td>
<td valign="top">

yes

</td>
</tr>
<tr>
<td valign="top">

JavaServer Faces \(JSF\) 2.0

</td>
<td valign="top">

no

</td>
<td valign="top">

yes

</td>
</tr>
<tr>
<td valign="top">

Enterprise JavaBeans \(EJB\) Lite 3.1

</td>
<td valign="top">

no

</td>
<td valign="top">

yes

</td>
</tr>
<tr>
<td valign="top">

Java Transaction API \(JTA\) 1.1

</td>
<td valign="top">

no

</td>
<td valign="top">

yes

</td>
</tr>
<tr>
<td valign="top">

Java Persistence API \(JPA\) 2.0

</td>
<td valign="top">

no

</td>
<td valign="top">

yes

</td>
</tr>
<tr>
<td valign="top">

Dependency Injection for Java 1.0

</td>
<td valign="top">

no

</td>
<td valign="top">

yes

</td>
</tr>
<tr>
<td valign="top">

Contexts and Dependency Injection for Java EE platform 1.0

</td>
<td valign="top">

no

</td>
<td valign="top">

yes

</td>
</tr>
<tr>
<td valign="top">

Bean Validation 1.0

</td>
<td valign="top">

no

</td>
<td valign="top">

yes

</td>
</tr>
<tr>
<td valign="top">

Managed Beans 1.0

</td>
<td valign="top">

no

</td>
<td valign="top">

yes

</td>
</tr>
<tr>
<td valign="top">

Interceptors 1.1

</td>
<td valign="top">

no

</td>
<td valign="top">

yes

</td>
</tr>
</table>

The table below summarizes the Java Request Specifications \(JSRs\) supported in the SAP BTP SDK for Java Web Tomcat 8 .


<table>
<tr>
<th valign="top">

Supported Java EE 7 Specification

</th>
<th valign="top">

SDK for Java Web Tomcat 8

</th>
<th valign="top">

SDK for Java EE 7 Web Profile TomEE 7

</th>
</tr>
<tr>
<td valign="top">

Servlet 3.1

</td>
<td valign="top">

yes

</td>
<td valign="top">

yes

</td>
</tr>
<tr>
<td valign="top">

JavaServer Pages \(JSP\) 2.3

</td>
<td valign="top">

yes

</td>
<td valign="top">

yes

</td>
</tr>
<tr>
<td valign="top">

Expression Language \(EL\) 3.0

</td>
<td valign="top">

yes

</td>
<td valign="top">

yes

</td>
</tr>
<tr>
<td valign="top">

WebSocket 1.1

</td>
<td valign="top">

yes

</td>
<td valign="top">

yes

</td>
</tr>
<tr>
<td valign="top">

Common Annotations for Java Platform 1.2

</td>
<td valign="top">

yes

</td>
<td valign="top">

yes

</td>
</tr>
<tr>
<td valign="top">

Standard Tag Library for JavaServer Pages \(JSTL\) 1.2

</td>
<td valign="top">

yes

</td>
<td valign="top">

yes

</td>
</tr>
<tr>
<td valign="top">

Debugging Support for Other Languages 1.0

</td>
<td valign="top">

yes

</td>
<td valign="top">

yes

</td>
</tr>
<tr>
<td valign="top">

Java API for RESTful Web Services \(JAX-RS\) 2.0

</td>
<td valign="top">

no

</td>
<td valign="top">

yes

</td>
</tr>
<tr>
<td valign="top">

JavaServer Faces \(JSF\) 2.2

</td>
<td valign="top">

no

</td>
<td valign="top">

yes

</td>
</tr>
<tr>
<td valign="top">

Enterprise JavaBeans \(EJB\) Lite 3.2

</td>
<td valign="top">

no

</td>
<td valign="top">

yes

</td>
</tr>
<tr>
<td valign="top">

Java Transaction API \(JTA\) 1.2

</td>
<td valign="top">

no

</td>
<td valign="top">

yes

</td>
</tr>
<tr>
<td valign="top">

Java Persistence API \(JPA\) 2.1

</td>
<td valign="top">

no

</td>
<td valign="top">

yes

</td>
</tr>
<tr>
<td valign="top">

Dependency Injection for Java 1.0

</td>
<td valign="top">

no

</td>
<td valign="top">

yes

</td>
</tr>
<tr>
<td valign="top">

Contexts and Dependency Injection for Java EE platform 1.1

</td>
<td valign="top">

no

</td>
<td valign="top">

yes

</td>
</tr>
<tr>
<td valign="top">

Bean Validation 1.1

</td>
<td valign="top">

no

</td>
<td valign="top">

yes

</td>
</tr>
<tr>
<td valign="top">

Managed Beans 1.0

</td>
<td valign="top">

no

</td>
<td valign="top">

yes

</td>
</tr>
<tr>
<td valign="top">

Interceptors 1.2

</td>
<td valign="top">

no

</td>
<td valign="top">

yes

</td>
</tr>
</table>



In addition to the standard APIs, SAP BTP offers platform-specific services that define their own APIs that can be used from the SAP BTP SDK. The APIs of the platform-specific services are listed in the table below


<table>
<tr>
<th valign="top">

API

</th>
<th valign="top">

More Information

</th>
</tr>
<tr>
<td valign="top">

Security

</td>
<td valign="top">

[Securing Java Applications](../60-security-neo/securing-java-applications-e80af38.md) 

</td>
</tr>
<tr>
<td valign="top">

Connectivity

</td>
<td valign="top">

[Connectivity and Destination APIs](https://help.sap.com/viewer/b865ed651e414196b39f8922db2122c7/Cloud/en-US/e69bc863bb571014b358e2947e36d475.html "") :arrow_upper_right: 

</td>
</tr>
<tr>
<td valign="top">

Document

</td>
<td valign="top">

[Handling CMIS Metadata](https://help.sap.com/viewer/b0cc1109d03c4dc299c215871eed8c42/Cloud/en-US/e621d26bbb571014b632dd180fb9bc19.html "One benefit of Content Management Interoperability Services (CMIS) as compared to a file system is the extended handling of metadata.") :arrow_upper_right: 

</td>
</tr>
</table>

The SAP BTP SDK contains a platform API folder for compiling your Web applications. It contains the above content, that is, all standard and third-party API JARs \(for legal reasons provided "as is", that is, they also have non-API content on which you should not rely\) and the platform APIs of the SAP BTP services.

You can add additional \(pure Java\) application programming frameworks or libraries and use them in your applications. For example, you can include Spring Framework in the application \(in its application archive\) and use it in the application. In such cases, the application should handle all dependencies to such additional frameworks or libraries and you should take care for the whole assembly of such additional frameworks or libraries inside the application itself.

SAP BTP also provides numerous other capabilities and APIs that might be accessible for applications. However, you should rely only on the APIs listed above.

For more information, see [API Documentation](api-documentation-4570e92.md).

**Related Information**  


 <?sap-ot O2O class="- topic/link " href="fd6b72f17a11478e87fefe3f6ad2e30d.xml" text="" desc="" xtrc="link:1" xtrf="file:/home/builder/src/dita-all/jjq1673438782153/loio9fe952ba277c471bbad80cd40548bb84_en-US/src/content/localization/en-us/e836a95cbb571014b3c4c422837fcde4.xml" output-class="" outputTopicFile="file:/home/builder/tp.net.sf.dita-ot/2.3/plugins/com.elovirta.dita.markdown_1.3.0/xsl/dita2markdownImpl.xsl" ?> 

[Java EE 7 Web Profile TomEE 7](java-ee-7-web-profile-tomee-7-f177a15.md "The Java EE 7 Web Profile TomEE 7 provides implementation of the Java EE 7 Web Profile specification.")

