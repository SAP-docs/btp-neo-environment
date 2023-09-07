<!-- loioe64e0e1cbb571014bd7b881f4531ac38 -->

# Entity Classes

To declare a class as an entity and define how that entity maps to the relevant database table, you can either decorate the Java object with metadata using Java annotations or denote it as an entity in the XML descriptor.

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**

> ### Note:  
> The Java tools for Eclipse used in this page are no longer available. We are in the process of updating the content accordingly.

The Dali Java Persistence Tools, which are provided as part of the Eclipse IDE for Java EE Developers, allow you to use a JPA diagram editor to create, edit, and display entities and their relationships \(your application’s data model\) in a graphical environment.



## Example

The tutorial *Adding Application-Managed Persistence with JPA \(SDK for Java Web\)* defines the entity class `Person`, as shown in the following:

```

package com.sap.cloud.sample.persistence;
import javax.persistence.*;
@Entity
@Table(name = "T_PERSON")
@NamedQuery(name = "AllPersons", query = "select p from Person p")
public class Person {

	@Id
	@GeneratedValue
	private long id;
	@Basic
	private String FirstName;
	@Basic
	private String LastName;


```

-   The `Person` class has been annotated as an entity: @Entity.
-   The @Table annotation maps the entity to the database table `T_PERSON`.
-   The @NamedQuery annotation indicates that a static query has been created in the metadata. The name element of @NamedQuery gives the name of the query that will be used with the `createNamedQuery()` method, while the query element specifies the actual query.
-   The definition of the field serving as the unique identifier of the entity has been annotated with @Id, indicating it is the primary key in the database. Its value is generated automatically \(@GeneratedValue\).

**Related Information**  


[Tutorial: Adding Application-Managed Persistence with JPA \(SDK for Java Web\)](tutorial-adding-application-managed-persistence-with-jpa-sdk-for-java-web-e4aeacd.md#loioe4aeacd2bb5710148ee99255136d96a5 "Use JPA to apply application-managed persistence in a simple Java EE web application that manages a list of persons.")

[Dali Java Persistence Tools User Guide](http://www.eclipse.org/webtools/dali/docs/dali_user_guide_2.2.pdf)

