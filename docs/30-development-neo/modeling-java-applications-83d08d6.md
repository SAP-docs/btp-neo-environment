<!-- loio83d08d6de57542d98554db291041a013 -->

# Modeling Java Applications

The SAP BTP allows you to deploy Java applications that run either on the proprietary SAP Java Web or the Java Web Tomcat runtime containers. These Java applications are `com.sap.java` and the `java.tomcat`.

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of the following technology portfolios: application development; process automation; integration; data, analytics, and enterprise planning; artificial intelligence. The platform offers users the ability to turn data into business value, compose end-to-end business processes, connect entire IT landscapes, and personalize, build and extend SAP applications. This reduces the overall total cost of ownership maintaining SAP landscapes and third-party software across end-to-end business processes.") :arrow_upper_right:.**

When you model a Java application in the МТА deployment descriptor, you can specify a set of properties related to this application. For a complete list of the supported properties, see [MTA Module Types, Resource Types, and Parameters for Applications in the Neo Environment](mta-module-types-resource-types-and-parameters-for-applications-in-the-neo-environment-f1caa87.md).

If a Java application is a part of your solution, the following rules apply during deployment:

-   The Java application is deployed and started at the end of the deployment
-   If a Java application with the same name already exists in your subaccount, it is replaced with the newer Java application
-   An existing Java application is updated only if its binaries or configuration in the MTA deployment descriptor have been changed
-   When updating an already existing application, its parameters get overridden by the ones defined in the new MTA deployment descriptor. Parameters not defined in the descriptor are copied from the already existing application.
-   You can also update a Java application using a rolling update. For more information, see [MTA Module Types, Resource Types, and Parameters for Applications in the Neo Environment](mta-module-types-resource-types-and-parameters-for-applications-in-the-neo-environment-f1caa87.md).
-   You can deploy one Java application that is distributed in two or more `war` files in the MTA archive. They have to be described accordingly in the `MANIFEST.MF` file, and the archive names should differ.

> ### Note:  
> Consider the following:
> 
> -   You have available resources to deploy a Java application to your subaccount
> -   You have created the Java application `.war` archive
> -   You have a database and valid credentials

The Java аpplications are modeled as a Multitarget Application \(MTA\) specification modules.

For specification of the Java аpplication module, see [MTA Module Types, Resource Types, and Parameters for Applications in the Neo Environment](mta-module-types-resource-types-and-parameters-for-applications-in-the-neo-environment-f1caa87.md).

For the examples below, we assume that you have the following:

-   Database alias `tst`
-   Database credentials `myuser` and `mypassword`

> ### Example:  
> **MTA Deployment Descriptor for `com.sap.java`**
> 
> ```
> _schema-version: '3.1'
> parameters:
>   hcp-deployer-version: '1.1.0'
> ID: com.example.basic.javaapp
> version: 0.1.0
> modules:
>   - name: example-java
>     type: com.sap.java
>     parameters:
>        name: exampleapp
>        jvm-arguments: -server
>        java-version: JRE 7
>        runtime-version: 1 
>     requires:
>      - name: dbbinding
> resources:
>   - name: dbbinding
>     type: com.sap.hcp.persistence
>     parameters:
>       id: tst
> ```

> ### Example:  
> **MTA Deployment Descriptor for `java.tomcat`**
> 
> ```
> _schema-version: '3.1'
> parameters:
>   hcp-deployer-version: '1.1.0'
> ID: com.example.basic.javaapp
> version: 0.1.0
> modules:
>   - name: example-java
>     type: java.tomcat
>     parameters:
>        name: exampleapp
>        jvm-arguments: -server
>        java-version: JRE 8
>        runtime-version: 3 
>     requires:
>      - name: dbbinding
> resources:
>   - name: dbbinding
>     type: com.sap.hcp.persistence
>     parameters:
>       id: tst
> ```

In the examples above you see the required application module properties such as the required Java version, runtime, description, and so on.

You also have to create an MTA extension descriptor that will hold sensitive data, such as credentials.

> ### Note:  
> Always enter the security-sensitive data of your Solution in an MTA extension descriptor.

> ### Example:  
> **MTA Extension Descriptor**
> 
> ```
> _schema-version: '3.1'
> ID: com.example.basic.javaapp.config
> extends: com.example.basic.javaapp
> parameters:
>   title: Java Application Example
>   description: This is an example of the Java Application module
> resources:
>   - name: dbbinding
>     parameters:
>       user-id: myuser
>       password : mypassword
> ```

In the example above, the extension descriptor adds the `user-id` and `password` parameters to the resource, which is modeled in the deployment descriptor.

After you deploy your solution, you can open its tile in the cockpit and check if the Java application is deployed.

**Related Information**  


[Operating Solutions](operating-solutions-2abf7d4.md "You can deploy, update, monitor, and delete a solution.")

[The Multitarget Application Model v.2](https://help.sap.com/doc/multitarget-application-modelv2/Cloud/en-US/The%20Multitarget%20Application%20Model.pdf)

[The Multitarget Application Model v.3](https://help.sap.com/doc/multitarget-application-modelv3/Cloud/en-US/The%20Multitarget%20Application%20M%D0%BEdel.pdf)

