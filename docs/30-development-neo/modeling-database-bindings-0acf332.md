<!-- loio0acf332377474191b46f4aba5af4806d -->

# Modeling Database Bindings

By using а database binding, the Java applications connects to a database set up in your current subaccount or provided by another subaccount part of the same global account. This connection is modeled within your solution by setting it up during the deployment operation.

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**

> ### Note:  
> Ensure the following prerequisites:
> 
> -   You have a database that is set up in your subaccount or there is a database provided to you by another subaccount.
> -   You have valid credentials for that database. In case that you do not have valid credentials for the database, default credentials will be generated for you.

You can create a database binding to one of the following:

-   The `<DEFAULT>` data source of your Java application
-   A named data source of your Java application by using the parameter `binding-name` that is added to the database binding resource required in the `requires` section of the `com.sap.java` and `java.tomcat` module types.

    For specification of the named database binding parameter, see [MTA Module Types, Resource Types, and Parameters for Applications in the Neo Environment](mta-module-types-resource-types-and-parameters-for-applications-in-the-neo-environment-f1caa87.md).


> ### Note:  
> You cannot have a database binding to the `<DEFAULT>` data source together with a database binding to a named data source, but you can have more than one database binding to named data sources.

The following rules apply:


<table>
<tr>
<th valign="top">

Does a Binding Already Exist?

</th>
<th valign="top">

Are User Credentials Provided?

</th>
<th valign="top">

Action

</th>
</tr>
<tr>
<td valign="top">

No

</td>
<td valign="top">

Yes

</td>
<td valign="top">

Creates a new database binding using the provided credentials

</td>
</tr>
<tr>
<td valign="top">

No

</td>
<td valign="top">

No

</td>
<td valign="top">

Creates a new database binding with generated credentials

</td>
</tr>
<tr>
<td valign="top">

Yes

</td>
<td valign="top">

Yes

</td>
<td valign="top">

Creates a new database binding using the provided credentials

</td>
</tr>
<tr>
<td valign="top">

Yes

</td>
<td valign="top">

No

</td>
<td valign="top">

Uses the old database binding

</td>
</tr>
</table>

Each database binding is modeled as a Multitarget Application \(MTA\) resource, which is required by a Java application module.

For specification of the database binding resource, see [MTA Module Types, Resource Types, and Parameters for Applications in the Neo Environment](mta-module-types-resource-types-and-parameters-for-applications-in-the-neo-environment-f1caa87.md).

First, you have to model the deployment descriptor that will contain the Java application module and the database binding resource and then you have to create an extension descriptor that will hold sensitive data, such as credentials.

> ### Note:  
> Make sure that you always use an extension descriptor when you have sensitive data within your solution.



<a name="loio0acf332377474191b46f4aba5af4806d__section_jkz_bkq_p1b"/>

## Modeling a Database Binding to a Database within Your Subaccount



### **Database Binding to the `<DEFAULT>` Data Source**

For the example below, we assume that you have the following:

-   Database alias `tst`
-   Database credentials `myuser` and `mypassword`

> ### Example:  
> **MTA Deployment Descriptor**
> 
> ```
> 
> _schema-version: '3.1'
> parameters:
>   hcp-deployer-version: '1.1.0'
> ID: com.example.basic.dbbinding
> version: 0.1.0
> modules:
>   - name: example-java
>     type: com.sap.java
>     parameters:
>        name: exampleapp
>        jvm-arguments: -server
>        java-version: JRE 7
>        runtime: neo-java-web
>        runtime-version: 1
>     requires:
>      - name: dbbinding
> resources:
>   - name: dbbinding
>     type: com.sap.hcp.persistence
>     parameters:
>       id: tst
> ```

In the example above you can see the following:

-   The Java application module requires the database binding resource
-   The database binding resource does not specify any credentials

> ### Example:  
> **MTA Extension Descriptor**
> 
> ```
> _schema-version: '3.1'
> ID: com.example.basic.dbbinding.config
> extends: com.example.basic.dbbinding
> parameters:
>   title: Database binding example
>   description: This is an example of the database binding resource
> resources:
>   - name: dbbinding
>     parameters:
>       user-id: myuser
>       password : mypassword
> ```

In the example above, the extension descriptor adds the `user-id` and `password` parameters to the resource dbbinding, which is modeled in the deployment descriptor.



### **Named Database Bindings to Specified Data Sources**

For the example below, we assume that you have the following:

-   Database aliases `tst` and `abc`
-   Database credentials `myuser` and `mypassword`

> ### Example:  
> **MTA Deployment Descriptor**
> 
> ```
> 
> _schema-version: '3.1'
> parameters:
>   hcp-deployer-version: '1.1.0'
> ID: com.example.basic.dbbinding
> version: 0.1.0
> modules:
>   - name: example-java
>     type: com.sap.java
>     parameters:
>        name: exampleapp
>        jvm-arguments: -server
>        java-version: JRE 7
>        runtime: neo-java-web
>        runtime-version: 1
>     requires:
>       - name: firstdbbinding
>         parameters:
>           binding-name: tstbinding
>       - name: seconddbbinding
>         parameters:
>           binding-name: abcbinding
> resources:
>   - name: fisrtdbbinding
>     type: com.sap.hcp.persistence
>     parameters:
>       id: tst
>   - name: seconddbbinding
>     type: com.sap.hcp.persistence
>     parameters:
>       id: abc
> ```

In the example above you can see the following:

-   The Java application module requires the database binding resources
-   The `binding-name` parameters are added to each database binding under the `requires` section
-   The database binding resources do not specify any credentials

> ### Example:  
> **MTA Extension Descriptor**
> 
> ```
> _schema-version: '3.1'
> ID: com.example.basic.dbbinding.config
> extends: com.example.basic.dbbinding
> parameters:
>   title: Named Database bindings example
>   description: This is an example of the database binding resources
> resources:
>   - name: firstdbbinding
>     parameters:
>       user-id: myuser
>       password : mypassword
>   - name: seconddbbinding
>     parameters:
>       user-id: myuser
>       password : mypassword
> ```

In the example above, the extension descriptor adds the `user-id` and `password` parameters to each resource, which is modeled in the deployment descriptor.



<a name="loio0acf332377474191b46f4aba5af4806d__section_whs_bkq_p1b"/>

## Modeling a Database Binding to a Database that is Provided by Another Subaccount



### **Database Binding to the `<DEFAULT>` Data Source**

For the example below, we assume that you have the following:

-   Database alias `tst`, which is provided by another subaccount

    > ### Note:  
    > The provider subaccount must belong to the same global account to which your subaccount belongs.

    The provider subaccount is `abcd`

    Database credentials `myuser` and `mypassword`


> ### Example:  
> **MTA Deployment Descriptor**
> 
> ```
> _schema-version: '3.1'
> parameters:
>   hcp-deployer-version: '1.1.0'
> ID: com.example.basic.dbbinding
> version: 0.1.0
> modules:
>   - name: example-java
>     type: com.sap.java
>     parameters:
>        name: exampleapp
>        jvm-arguments: -server
>        java-version: JRE 7
>        runtime: neo-java-web
>        runtime-version: 1
>     requires:
>      - name: dbbinding
> resources:
>   - name: dbbinding
>     type: com.sap.hcp.persistence
>     parameters:
>       id: tst
>       account: abcd
> ```

In the example above, you can see the following:

-   The Java application module requires the database binding resource
-   The database binding resource does not specify any credentials
-   The provider subaccount `abcd` is specified as a resource parameter

> ### Example:  
> **MTA Extension Descriptor**
> 
> ```
> _schema-version: '3.1'
> ID: com.example.basic.dbbinding.config
> extends: com.example.basic.dbbinding
> parameters:
>   title: Database binding example
>   description: This is an example of the database binding resource
> resources:
>   - name: dbbinding
>     parameters:
>       user-id: myuser
>       password : mypassword
> ```

In the example above, the MTA extension descriptor adds the `user-id` and `password` parameters to the resource `dbbinding`, which is modeled in the MTA deployment descriptor. After you deploy your solution, you can open its tile in the cockpit and check if the database binding is created.



### **Named Database Bindings to Specified Data Sources**

For the example below, we assume that you have the following:

-   Database aliases `tst` and `abc`, which are provided by another subaccount

    > ### Note:  
    > The provider subaccount must belong to the same global account to which your subaccount belongs.

    The provider subaccounts are `abcd` and `test`

    Database credentials `myuser` and `mypassword`


> ### Example:  
> **MTA Deployment Descriptor**
> 
> ```
> _schema-version: '3.1'
> parameters:
>   hcp-deployer-version: '1.1.0'
> ID: com.example.basic.dbbinding
> version: 0.1.0
> modules:
>   - name: example-java
>     type: com.sap.java
>     parameters:
>        name: exampleapp
>        jvm-arguments: -server
>        java-version: JRE 7
>        runtime: neo-java-web
>        runtime-version: 1
>     requires:
>       - name: firstdbbinding
>         parameters:
>           binding-name: tstbinding
>       - name: seconddbbinding
>         parameters:
>           binding-name: abcbinding
> resources:
>   - name: firstdbbinding
>     type: com.sap.hcp.persistence
>     parameters:
>       id: tst
>       account: abcd
>   - name: seconddbbinding
>     type: com.sap.hcp.persistence
>     parameters:
>       id: abc
>       account: test
> ```

In the example above, you can see the following:

-   The Java application module requires the database binding resources
-   The `binding-name` parameters are added to each database binding under the `requires` section
-   The database binding resources do not specify any credentials
-   The provider subaccounts `abcd` and `test` are specified as resource parameters

> ### Example:  
> **MTA Extension Descriptor**
> 
> ```
> _schema-version: '3.1'
> ID: com.example.basic.dbbinding.config
> extends: com.example.basic.dbbinding
> parameters:
>   title: Named database bindings example
>   description: This is an example of the database binding resources
> resources:
>   - name: firstdbbinding
>     parameters:
>       user-id: myuser
>       password : mypassword
>   - name: seconddbbinding
>     parameters:
>       user-id: myuser
>       password : mypassword
> ```

In the example above, the MTA extension descriptor adds the `user-id` and `password` parameters to each resource, which is modeled in the MTA deployment descriptor. After you deploy your solution, you can open its tile in the cockpit and check if the database bindings are created.



> ### Note:  
> When you delete a database binding, the credentials that you used are not removed from the database. Delete them manually, if you want to do so.

**Related Information**  


 <?sap-ot O2O class="- topic/link " href="c4f0d850b6ba46089a76d53ab805c9e6.xml" text="" desc="" xtrc="link:1" xtrf="file:/home/builder/src/dita-all/jjq1673438782153/loio9fe952ba277c471bbad80cd40548bb84_en-US/src/content/localization/en-us/0acf332377474191b46f4aba5af4806d.xml" output-class="" outputTopicFile="file:/home/builder/tp.net.sf.dita-ot/2.3/plugins/com.elovirta.dita.markdown_1.3.0/xsl/dita2markdownImpl.xsl" ?> 

[Operating Solutions](operating-solutions-2abf7d4.md "You can deploy, update, monitor, and delete a solution.")

[The Multitarget Application Model v.2](http://go.sap.com/documents/2016/06/e2f618e4-757c-0010-82c7-eda71af511fa.html)

[The Multitarget Application Model v.3](https://www.sap.com/documents/2021/09/66d96898-fa7d-0010-bca6-c68f7e60039b.html)

