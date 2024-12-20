<!-- loiobb8f82705c6442fc9022bbe7cbd09809 -->

# Defining MTA Extension Descriptors in the Neo Environment

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of the following technology portfolios: application development; process automation; integration; data, analytics, and enterprise planning; artificial intelligence. The platform offers users the ability to turn data into business value, compose end-to-end business processes, connect entire IT landscapes, and personalize, build and extend SAP applications. This reduces the overall total cost of ownership maintaining SAP landscapes and third-party software across end-to-end business processes.") :arrow_upper_right:.**

The Multitarget Application \(МТА\) extension descriptor is a YAML file that contains data complementary to the deployment descriptor. The data can be environment or deployment specific, for example, credentials depending on the user who performs the deployment. The MTA extension descriptor is a YAML file that has a similar structure to the deployment descriptor, following the Multitarget Application Model structure with several limitations and differences. Normally, the extension descriptor extends the deployment descriptor but it is possible to extend another extension descriptor, making an extension descriptors chain. It can add or overwrite existing data if necessary.

Several extension descriptors can be additionally used after the initial deployment.

> ### Note:  
> The format and available options within the extension descriptor may change with newer versions of the MTA specification. You must always specify the schema version option when defining an extension descriptor to inform the SAP BTP which MTA specification version should be used. Furthermore, the schema version used within the extension descriptor and the deployment descriptor should always be the same.

In the examples below, we have a deployment descriptor, which has already been defined, and several extension descriptors.

> ### Note:  
> Each extension descriptor is defined in a separate file with an extension `.mtaext`.

Deployment descriptor:

> ### Example:  
> ```
> _schema-version: '3.1'
> parameters:
>   hcp-deployer-version: '1.0'
> ID: com.example.extension
> version: 0.1.0
> 
> resources:
>   - name: data-storage
>     properties:
>       existing-data: value
> ```

The example above instructs SAP BTP to:

-   Validate the extension descriptor against the MTA specification version `3.1`
-   Extend the `com.example.extension` deployment descriptor

The following is a basic example of an extension descriptor that adds data and overwrites data to another extension descriptor:

> ### Example:  
> ```
> _schema-version: '3.1'
> ID: com.example.extension.first
> extends: com.example.extension
> 
> resources:
>   - name: data-storage
>     properties:
>       existing-data: new-value
>       non-existing-data: value
> ```

The above instructs SAP BTP to:

-   Extend the deployment descriptor by its ID `com.example.extension`
-   Validate the extension descriptor against the MTA specification version 3.1
-   Overwrite the data for the `existing-data` property
-   Add new data called `non-existing-data` to the `data-storage` properties

The following is an example of another extension descriptor that extends the extension descriptor from the previous example:

> ### Example:  
> ```
> _schema-version: '3.1'
> ID: com.example.extension.second
> extends: com.example.extension.first
> 
> resources:
>   - name: data-storage
>     properties:
>       second-non-existing-data: value
> ```

The example above instructs the SAP BTP to:

-   Extend the first extension descriptor by its ID
-   Add new data called `second-non-existing-data` to the `data-storage` properties

-   The examples above are incomplete. To deploy a solution, you have to create a deployment descriptor and an MTA archive.



**What is possible to do with an extension descriptor?**

You can do the following using an extension descriptor:

-   Add new data in properties and parameters on module level, resource level, provided section level and required section level

-   Overwrite an existing data \(in depth\) in modules, resources, parameters, properties, provides, requires sections. This depends on the parameter or property metadata overwritable. See [Metadata for Properties and Parameters](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/fca2cedcb79649e7a8f51234faea1142.html "It is possible to declare metadata for parameters and properties defined in the MTA deployment description, for example, using the "parameters-metadata:" or "properties-metadata:" keys, respectively; the mapping is based on the keys defined for a parameter or property.") :arrow_upper_right:.

-   As of schema version 3.xx parameters and properties are overwritable and optional by default. If you want to make a certain parameter or property non-overwritable or required, you need to add specific metadata. See [Metadata for Properties and Parameters](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/fca2cedcb79649e7a8f51234faea1142.html "It is possible to declare metadata for parameters and properties defined in the MTA deployment description, for example, using the "parameters-metadata:" or "properties-metadata:" keys, respectively; the mapping is based on the keys defined for a parameter or property.") :arrow_upper_right:.

You cannot use an extension descriptor to:

-   Add new entities such as modules or resources
-   Change module or resource type
-   Alter read-only \(system\) parameters
-   Add new provided or required dependencies
-   Change the processing order of modules and resources with `deployed-after` and `processed-after` parameters

**Related Information**  


[Defining MTA Deployment Descriptors for the Neo Environment](defining-mta-deployment-descriptors-for-the-neo-environment-ef90452.md)

[Defining Multitarget Application Archives](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/33a0e0eb1e4a47b3af52596b87fd2cef.html "You package the MTA deployment descriptor and module binaries in an MTA archive. You can manually do so as described below, or alternatively use the Cloud MTA Build tool.") :arrow_upper_right:

[MTA Module Types, Resource Types, and Parameters for Applications in the Neo Environment](mta-module-types-resource-types-and-parameters-for-applications-in-the-neo-environment-f1caa87.md)

[The Multitarget Application Model v.2](https://help.sap.com/doc/multitarget-application-modelv2/Cloud/en-US/The%20Multitarget%20Application%20Model.pdf)

[The Multitarget Application Model v.3](https://help.sap.com/doc/multitarget-application-modelv3/Cloud/en-US/The%20Multitarget%20Application%20M%D0%BEdel.pdf)

