<!-- loio1806ffa1e06d4faaa65671a3e8c8c46b -->

# Modeling Application-Level Destinations

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**



Application-level destinations apply only within a given application, compared to subaccount-level destinations that apply to the whole subaccount. You can use them to connect your application to resources outside the SAP BTP, applications not part of your subaccount, applications from your subaccount and even to your own application.



<a name="loio1806ffa1e06d4faaa65671a3e8c8c46b__section_esv_gqk_nz"/>

## Destinations to External Resources

Destinations to external resources lead to services or applications external to and not accessible by the current Multitarget Application \(MTA\) archive. For example, it can be an application running in another subaccount.

Application-level destinations to external resources are modeled as items within the `destinations` parameter of the `com.sap.java` module type. This means that the lifecycle of such a destination is bound to the lifecycle of the corresponding application.

For a list of the available destination parameters, see [MTA Module Types, Resource Types, and Parameters for Applications in the Neo Environment](mta-module-types-resource-types-and-parameters-for-applications-in-the-neo-environment-f1caa87.md), and the design documents [The Multitarget Application Model v.2](https://www.sap.com/documents/2016/06/e2f618e4-757c-0010-82c7-eda71af511fa.html) and [The Multitarget Application Model v.3](https://www.sap.com/documents/2021/09/66d96898-fa7d-0010-bca6-c68f7e60039b.html).

> ### Remember:  
> Note the following special cases when it comes to deploying a destination:
> 
> -   If you need more than one destination, you have to model each subaccount-level destination in a separate module.
> -   Use the property `force-overwrite` to choose a redeployment approach for an existing destination. Place the property at destination level, and use the value `true` to have the destination forcefully overwritten, or `false` to leave it unchanged, which is also the default behavior.
> -   You cannot define a destination in the `web.xml` file of the Java application, if that specific destination points to the application itself, and has a URL automatically resolved by the SAP BTP. You have to manually resolve the destination in the application code.

The following shows how to create an application-level destination to an external resource:

> ### Example:  
> ```
> modules:
>   - name: abc
>     type: com.sap.java
>     parameters:
>       name: networking
>       ...
>       destinations:
>         - name: ExampleHttpDestination
>           type: HTTP
>           url: http://www.examplewebsite.com
>           proxy-type: Internet
>           authentication: BasicAuthentication
>           user: myuser
>           password: mypassword
> ```

In the example above, you can see the following:

-   The `com.sap.java` module defines the Java application that has to be deployed.
-   The `destinations` parameter defines the destinations that have to be created.

As a result, the example above creates an application-level destination within your subaccount with credentials, which are still located in the MTA deployment descriptor.

If you want to provide your solution for consumption by another subaccount, you can create that destination into the subscriber subaccount. To do this, you can use the `owner` option.

> ### Example:  
> **Deployment Descriptor**
> 
> ```
> modules:
>   - name: abc
>     type: com.sap.java
>     parameters:
>       name: networking
>       requires:
>         - name: data-storage
>       ...
>       destinations:
>         - name: ExampleDestination
>           type: HTTP
>           url: http://www.examplewebsite.com
>           proxy-type: Internet
>           authentication: BasicAuthentication
>           user: ~{data-storage/user}
>           password: ~{data-storage/password}
>           owner: consumer
>       ...
> resources:
>  - name: data-storage
>    properties:
>      user:
>      password:
>      ...
> ```
> 
> **Extension Descriptor**
> 
> ```
> ...
> resources:
>   - name: data-storage
>     properties:
>       user: myuser
>       password : mypassword
>       ...
> ```

In the example above, you can see the following:

-   The `ExampleDestination` destination will be deployed to the subscriber subaccount.

    > ### Note:  
    > The `owner` option indicates that the destination has to be deployed to the subscriber subaccount.

-   The untyped resource `data-storage` contains the sensitive parameters, which are deployed using the MTA extension descriptor.

    > ### Note:  
    > Be aware of the following:
    > 
    > -   The reference syntax `~{source/value}` is used to link the destinations `user` and `password` options.
    > -   The `data-storage` resource is of `untyped` type.
    > 
    > For more information, see [MTA Module Types, Resource Types, and Parameters for Applications in the Neo Environment](mta-module-types-resource-types-and-parameters-for-applications-in-the-neo-environment-f1caa87.md)


The example above creates the destination within the subscribers subaccount, but the credentials for that destination are still provided separately by you. If the consumer of your solution has to provide the credentials for the destination, you have to use `consumer-optional` metadata.

> ### Note:  
> Note that metadata is available in an MTA archive with schema version `3.1` and higher.

> ### Example:  
> **Deployment Descriptor**
> 
> ```
> modules:
>   - name: abc
>     type: com.sap.java
>     parameters:
>       name: networking
>       requires:
>         - name: data-storage
>       ...
>       destinations:
>         - name: ExampleDestination
>           type: HTTP
>           url: http://www.examplewebsite.com
>           proxy-type: Internet
>           authentication: BasicAuthentication
>           user: ~{data-storage/user}
>           password: ~{data-storage/password}
>           owner: consumer
>       ...
>  
> resources:
>   - name: data-storage
>     properties:
>       user:
>       password:
>     properties-metadata:
>       user:
>         optional: true
>         consumer-optional: false
>       password:
>         optional: true
>         consumer-optional: false
>     ...
> ```
> 
> **Provider Extension Descriptor**
> 
> ```
> ...
> # no credentials provided
> ...
> ```
> 
> **Subscriber Extension Descriptor**
> 
> ```
> resources:
>   - name: data-storage
>     properties:
>       user: subscriberuser
>       password: subscriberpassword
>     ...
> ```

In the example above the `consumer-optional` metadata is used to enforce the consumer of your solution to provide the required credentials. In this case, the MTA extension descriptor of the consumer provides the required credentials instead of the provider MTA extension descriptor.

> ### Note:  
> The `consumer-optional` metadata is used together with the `optional` option.
> 
> If you do not use the `consumer-optional` metadata when you deploy the solution to your subaccount, the operation will fail due to missing data.



<a name="loio1806ffa1e06d4faaa65671a3e8c8c46b__section_mzn_3vk_nz"/>

## Destinations to Internal Applications

The application-level destination to an internal application is an `HTTP` type destination, which can point to the same or different Java application deployed with the same solution. It is modeled as a `com.sap.java` or `java.tomcat` module.

> ### Note:  
> -   If you need more than one destination, you have to model each subaccount-level destination in a separate module.
> -   To overwrite an already existing destination, you have to use the `force-overwrite` option. For more information, see [MTA Module Types, Resource Types, and Parameters for Applications in the Neo Environment](mta-module-types-resource-types-and-parameters-for-applications-in-the-neo-environment-f1caa87.md).

The following example creates a frontend Java application that has a destination directed at a backend Java application, which is deployed within the same solution. In this case, the URL of the source Java application is not described, but instead left to be resolved to its default value during deployment by the SAP BTP.

For additional options of what can be resolved automatically by the SAP BTP during deployment see [MTA Module Types, Resource Types, and Parameters for Applications in the Neo Environment](mta-module-types-resource-types-and-parameters-for-applications-in-the-neo-environment-f1caa87.md).

> ### Example:  
> ```
> - name: abc
>   type: com.sap.java
>   provides:
>     - name: abc
>       properties:
>         application-url: ${default-url}
>   parameters:
>     name: javaapp1
>     ...
> - name: abc-ui
>   type: com.sap.java
>   requires:
>     - name: abc
>   parameters:
>     name: javaapp2
>     ...
>     destinations:
>       - name: JavaAppBackend
>         type: HTTP
>         url: ~{abc/application-url}
>         proxy-type: Internet
>         authentication: AppToAppSSO
> ```

In the example above, you can see the following:

-   The Java `abc` module provides the URL as an `application-url` property.

    > ### Note:  
    > The naming of the `applicaiton-url` property is mandatory. For more details, see [MTA Module Types, Resource Types, and Parameters for Applications in the Neo Environment](mta-module-types-resource-types-and-parameters-for-applications-in-the-neo-environment-f1caa87.md).

-   The value of the `application-url` property is a placeholder. For more details about the `${default-url}` placeholder, see [MTA Module Types, Resource Types, and Parameters for Applications in the Neo Environment](mta-module-types-resource-types-and-parameters-for-applications-in-the-neo-environment-f1caa87.md)
-   The destination `JavaAppBackend` is an entry of the destinations parameter of the `com.sap.java` module.
-   The module `abc-ui` requires the module abc. By requiring the `abc` module, the `abc-ui` module gains access to all provided properties of that module, namely the `application-url` property. Later on, the destination module can use a reference to read the provided properties. For more details, see [MTA Module Types, Resource Types, and Parameters for Applications in the Neo Environment](mta-module-types-resource-types-and-parameters-for-applications-in-the-neo-environment-f1caa87.md).
-   The destination is using the reference to read the value of the `application-url` property.

> ### Note:  
> Ensure that your applications do not have circular dependencies, that is, that the `application-url` property or one Java Application does not refer to the `application-url` property of another Java Application module.

