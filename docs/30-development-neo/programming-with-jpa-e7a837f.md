<!-- loioe7a837f4bb5710149251a99bcf22430b -->

# Programming with JPA

Program with JPA in the Neo environment, whose container-managed persistence and application-managed persistence differ in terms of the management and life cycle of the entity manager.

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/docs/btp/sap-business-technology-platform/sap-business-technology-platform?version=Cloud) .**

The main features of each scenario are shown in the table below. We recommend that you use container-managed persistence \(Java EE 6 Web Profile runtime\), which is the model most commonly used by Web applications.


<table>
<tr>
<th valign="top">

JPA Scenario

</th>
<th valign="top">

SDK for Java Web

</th>
<th valign="top">

SDK for Java EE 6 Web Profile

</th>
</tr>
<tr>
<td valign="top" rowspan="2">

**Container-managed persistence**

</td>
<td valign="top" rowspan="2">

Not supported

</td>
<td valign="top">

JTA transactions

</td>
</tr>
<tr>
<td valign="top">

Entity manager injection using the `@PersistenceContext` annotation

</td>
</tr>
<tr>
<td valign="top" rowspan="3">

**Application-managed persistence**

</td>
<td valign="top" align="center" colspan="2">

Resource-local transactions

</td>
</tr>
<tr>
<td valign="top">

Not supported

</td>
<td valign="top">

Injection of the entity manager factory using the `@PersistenceUnit` annotation

</td>
</tr>
<tr>
<td valign="top" align="center" colspan="2">

Manual creation of the entity manager factory using `javax.persistence.Persistence. createEntityManagerFactory` 

</td>
</tr>
</table>



<a name="loioe7a837f4bb5710149251a99bcf22430b__section_33A5174B872A4DD9B133CC3D0BFAEBD8"/>

## EclipseLink

Download the latest version of EclipseLink. EclipseLink versions 2.5 and later contain the SAP HANA database platform.

The following JAR files are required:


<table>
<tr>
<th valign="top">

JPA Scenario

</th>
<th valign="top">

SDK

</th>
<th valign="top">

EclipseLink JARs

</th>
</tr>
<tr>
<td valign="top">

**Container-managed persistence**

</td>
<td valign="top">

Java EE 6 Web Profile

</td>
<td valign="top">

`eclipselink\jlib\eclipselink.jar`

Required only for EclipseLink versions 2.5 and later.

</td>
</tr>
<tr>
<td valign="top" rowspan="2">

**Application-managed persistence**

</td>
<td valign="top">

Java Web

</td>
<td valign="top">

-   `eclipselink\jlib\eclipselink.jar`
-   `eclipselink\jlib\jpa\javax.persistence_2.*.jar`



</td>
</tr>
<tr>
<td valign="top">

Java EE 6 Web Profile

</td>
<td valign="top">

`eclipselink\jlib\eclipselink.jar`

</td>
</tr>
</table>

The EclipseLink download is available from [http://www.eclipse.org/eclipselink/downloads](http://www.eclipse.org/eclipselink/downloads). Click *EclipseLink 2.5.x Installer Zip*, then download the archive and extract it to your local file system. For the Java Web scenario, we recommend that you copy the two files \(see above\) to a separate directory in your local file system.

For details about importing the files into your Web application project and specifying the JPA implementation library EclipseLink, see the tutorial [Tutorial: Adding Application-Managed Persistence with JPA \(SDK for Java Web\)](tutorial-adding-application-managed-persistence-with-jpa-sdk-for-java-web-e4aeacd.md#loioe4aeacd2bb5710148ee99255136d96a5).

**Related Information**  


[Special Settings for EclipseLink Versions Earlier than 2.5](special-settings-for-eclipselink-versions-earlier-than-2-5-f90799f.md "EclipseLink versions prior to 2.5 do not include the SAP HANA database platform. To deploy applications on the SAP HANA database, you need to specify it as the target database and, for application-managed persistence, import the corresponding JAR file into your project.")

[Persistence Units](persistence-units-e7beab5.md "A JPA model contains a persistence configuration file, persistence.xml, which describes the defined persistence units. A persistence unit in turn defines all entity classes managed by the entity managers in your application and includes the metadata for mapping the entity classes to the database entities.")

[Using Container-Managed Persistence](using-container-managed-persistence-76132ca.md "Container-managed entity managers are the model most commonly used by Web applications. Container-managed entity managers require JTA transactions and are generally used with stateless session beans and transaction-scoped persistence contexts, which are threadsafe.")

[Using Application-Managed Persistence](using-application-managed-persistence-e658f24.md "Application-managed entity managers are created manually using the EntityManagerFactory interface. Application-managed entity managers require resource-local transactions and non-JTA data sources, which you must declare as JNDI resource references.")

[Entity Classes](entity-classes-e64e0e1.md "To declare a class as an entity and define how that entity maps to the relevant database table, you can either decorate the Java object with metadata using Java annotations or denote it as an entity in the XML descriptor.")

