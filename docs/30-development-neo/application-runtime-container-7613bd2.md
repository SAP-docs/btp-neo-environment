<!-- loio7613bd28711e1014839a8273b0e91070 -->

# Application Runtime Container

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**



SAP BTP applications run on a modular and lightweight application runtime container where they can use the platform services APIs and Java EE APIs according to standard patterns.

Depending on the runtime type and corresponding SDK you are using, SAP BTP provides the following profiles of the application runtime container:


<table>
<tr>
<th valign="top">

Runtime Profile



</th>
<th valign="top">

Provides Support for



</th>
<th valign="top">

Supported Java/JRE Versions



</th>
<th valign="top">

Use



</th>
</tr>
<tr>
<td valign="top">

[Java EE 7 Web Profile TomEE 7](java-ee-7-web-profile-tomee-7-f177a15.md)



</td>
<td valign="top">

Java EE 7 Web Profile APIs



</td>
<td valign="top">

8



</td>
<td valign="top">

If you need an application runtime container together with all containers defined by the Java EE 7 Web Profile specification.



</td>
</tr>
<tr>
<td valign="top">

[Java Web Tomcat 9](java-web-tomcat-9-41b1ee9.md)



</td>
<td valign="top">

Some of the standard Java EE 7 APIs \(Servlet, JSP, EL, Websocket\)



</td>
<td valign="top">

8 \(default\)

17 \(in runtime version 4.16 or higher\)

11 \(in runtime version 4.15 or lower\)



</td>
<td valign="top">

If you need a simplified Java Web application runtime container based on Apache Tomcat 9.



</td>
</tr>
<tr>
<td valign="top">

[Java Web Tomcat 8 \(Deprecated\)](java-web-tomcat-8-deprecated-fd6b72f.md)



</td>
<td valign="top">

Some of the standard Java EE 7 APIs \(Servlet, JSP, EL, Websocket\)



</td>
<td valign="top">

8



</td>
<td valign="top">

If you need a simplified Java Web application runtime container based on Apache Tomcat 8.



</td>
</tr>
</table>

For the complete list of supported APIs, see [Supported Java APIs](supported-java-apis-e836a95.md)



<a name="loio7613bd28711e1014839a8273b0e91070__section_ajy_b2k_ctb"/>

## Keeping Your Application Runtimes Up-to-date

> ### Tip:  
> We recommend that you restart your Java applications at least once every three months. This ensures you always use the latest updates available for your runtime, with the latest security and other fixes.
> 
> You can view an application's runtime status in your subaccount's application area in the cockpit \(*Applications* \> *Java Applications* \> *Monitoring* \> *Processes*\).
> 
> -   See [Check the Process Status](../50-administration-and-ops-neo/check-the-process-status-499992d.md) for more information how to check the runtime status
> -   See [Start and Stop Applications](../50-administration-and-ops-neo/start-and-stop-applications-7612f03.md) for more information how to start and stop applications.

