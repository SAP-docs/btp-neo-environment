<!-- loioef90452321f84b43af8d14d4012aefe0 -->

# Defining MTA Deployment Descriptors for the Neo Environment

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of the following technology portfolios: application development; process automation; integration; data, analytics, and enterprise planning; artificial intelligence. The platform offers users the ability to turn data into business value, compose end-to-end business processes, connect entire IT landscapes, and personalize, build and extend SAP applications. This reduces the overall total cost of ownership maintaining SAP landscapes and third-party software across end-to-end business processes.") :arrow_upper_right:.**

The Multitarget Application \(MTA\) deployment descriptor is a YAML file that defines the relations between you as a provider of а deployable artifact and the SAP BTP as a deployer tool.

Using the YAML data serialization language, you describe the MTA in an MTA deployment descriptor \(`mtad.yaml`\) file containing the following:

-   Modules and module types that represent Neo environment applications and content, which form the MTA and are deployed on the platform
-   Resources and resource types that are not part of an MTA, but are required by the modules at runtime or at deployment time
-   Dependencies between modules and resources
-   Technical configuration parameters, such as URLs, and application configuration parameters, such as environment variables.

See the following examples of a basic MTA deployment descriptor that is defined in an `mtad.yaml` file:

> ### Example:  
> ```
> _schema-version: '3.1'
> 
> parameters:
>   hcp-deployer-version: '1.1.0'
>   
> ID: com.example.descriptor
> version: 0.1.0
> 
> modules:
>   - name: example-java-app
>     type: com.sap.java
>     requires:
>       - name: db-binding
>     parameters:
>        name: examplejavaapp
>        jvm-arguments: -server
>        java-version: JRE 7
>        runtime: neo-java-web
>        runtime-version: 1
> resources:
>   - name: db-binding
>     type: com.sap.hcp.persistence
>     parameters:
>       id: fx7
>       user-id:
>       password:
> ```

The example above instructs the SAP BTP to:

-   Deploy a Java application
-   Create a database binding for that Java application

> ### Note:  
> -   The format and available options in the MTA deployment descriptor could change with the newer versions of the MTA specification. Always specify the schema version when defining an MTA deployment descriptor, so that the SAP BTP is aware against which specific MTA specification version you are deploying.
> -   The example above is incomplete. In its case, you have to create an MTA extension descriptor containing the database user and password.
> -   As of `_schema version` `3.1`, you have the option to input missing values that are required by the Multitarget Application, which afterwards act as the latest provided MTA extension descriptor. During deployment using the cockpit the SAP BTP detects the missing values, and opens a dialog where you can enter them. This option can be useful when you need to extend already provided MTAs with new data.
> 
>     For example, you can choose to provide credentials manually instead of storing and providing them in an MTA extension descriptor file. Also, you can manually input subaccount-relevant parameter values specific to the provider or consumer subaccount in the provider-consumer scenario. For more information, see the *Supported Metadata Options* subsection of [MTA Module Types, Resource Types, and Parameters for Applications in the Neo Environment](mta-module-types-resource-types-and-parameters-for-applications-in-the-neo-environment-f1caa87.md).

Since the Neo environment supports a different set of module types, resource types, and configuration parameters, the deployment of an MTA archive can be further configured by using MTA extension descriptors. This allows administrators to adapt a deployment to a target or use case specific requirements, like setting URLs, memory allocation parameters, and so on. For more information, see the official specification documents [The Multitarget Application Model v.2](https://help.sap.com/doc/multitarget-application-modelv2/Cloud/en-US/The%20Multitarget%20Application%20Model.pdf) and [The Multitarget Application Model v.3](https://help.sap.com/doc/multitarget-application-modelv3/Cloud/en-US/The%20Multitarget%20Application%20M%D0%BEdel.pdf).

**Related Information**  


[Defining MTA Extension Descriptors](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/50df803465324d36851c79fd07e8972c.html "") :arrow_upper_right:

[Defining Multitarget Application Archives](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/33a0e0eb1e4a47b3af52596b87fd2cef.html "You package the MTA deployment descriptor and module binaries in an MTA archive. You can manually do so as described below, or alternatively use the Cloud MTA Build tool.") :arrow_upper_right:

[MTA Module Types, Resource Types, and Parameters for Applications in the Neo Environment](mta-module-types-resource-types-and-parameters-for-applications-in-the-neo-environment-f1caa87.md)

[The Multitarget Application Model v.2](https://help.sap.com/doc/multitarget-application-modelv2/Cloud/en-US/The%20Multitarget%20Application%20Model.pdf)

[The Multitarget Application Model v.3](https://help.sap.com/doc/multitarget-application-modelv3/Cloud/en-US/The%20Multitarget%20Application%20M%D0%BEdel.pdf)

