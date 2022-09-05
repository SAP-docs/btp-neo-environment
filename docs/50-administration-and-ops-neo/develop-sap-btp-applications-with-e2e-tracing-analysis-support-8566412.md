<!-- loio85664123381146fab8542455cb2322cf -->

# Develop SAP BTP Applications with E2E Tracing Analysis Support

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**

**HTML5 Applications**

The E2E tracing is supported by default for HTML5 applications. To enable automatic upload of your business transaction started by an HTML5 application to SAP Solution Manager or FRUN, proceed as described in [E2E Trace Involving SAP BTP, Neo Environment](https://wiki.scn.sap.com/wiki/display/TechOps/E2E+Trace+involving+SAP+Cloud+Platform).

**Java Applications**

The E2E Tracing for Java applications in SAP BTP is supported. For outgoing connections to other systems, for example other Java applications in SAP BTP or on-premise systems, you must use the Connectivity Service to ensure the correct forwarding of the `SAP-PASSPORT` for all outgoing connections depending on the runtime environment.

For more information, see the corresponding sections:


<table>
<tr>
<th valign="top">

Runtime



</th>
<th valign="top">

Information Location



</th>
</tr>
<tr>
<td valign="top">

Java EE 6 Web Profile



</td>
<td valign="top">

[Preparing Managed Systems - SAP NetWeaver Consuming the Connectivity Service \(Java\)](https://help.sap.com/viewer/cca91383641e40ffbe03bdc78f00f681/Cloud/en-US/e5c9867dbb571014957ef9d7a8846b1c.html)



</td>
</tr>
<tr>
<td valign="top">

Java Web Tomcat 7

Java Web Tomcat 8

Java EE 7 Web Profile TomEE 7



</td>
<td valign="top">

[Implementing Statistics Gathering for Java Applications](implementing-statistics-gathering-for-java-applications-05a0710.md)



</td>
</tr>
</table>

