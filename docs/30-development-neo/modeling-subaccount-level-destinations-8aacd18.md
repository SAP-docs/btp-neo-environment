<!-- loio8aacd18309394730bb6a0fdd5e937bc2 -->

# Modeling Subaccount-Level Destinations

Subaccount-level destinations are not linked to a particular application, but instead can be used by all applications. For example, the subaccount-level destination can be used by an HTML5 application to connect to a source Java application.

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**

> ### Note:  
> If you modify a subaccount-level destination, you will affect all applications that use it. The subaccount-level destination has a lifecycle that is independent from the applications that use it.



<a name="loio8aacd18309394730bb6a0fdd5e937bc2__section_trt_jpj_yy"/>

## Destinations to External Resources

Destinations to external resources lead to services or applications that are not part of the current Multitarget Application \(MTA\) archive and you do not have direct access to them. For example, it might be an application running in another subaccount or outside SAP BTP.

When you want to describe subaccount-level destinations to external resources, the modeling is as a module of type `com.sap.hcp.destination`. In this type of destination relations, first you declare that a module requires the dependency using a `requires` element, and then you provide the dependency details as module type parameters. The subaccount-level destination has a lifecycle that is independent from the applications that use it. Note that if you need your Java application to have more than one destination, you have to model each subaccount-level destination in a separate module.

For a list of the available destination parameters, see [MTA Module Types, Resource Types, and Parameters for Applications in the Neo Environment](mta-module-types-resource-types-and-parameters-for-applications-in-the-neo-environment-f1caa87.md), and the design documents [The Multitarget Application Model v.2](https://www.sap.com/documents/2016/06/e2f618e4-757c-0010-82c7-eda71af511fa.html) and [The Multitarget Application Model v.3](https://www.sap.com/documents/2021/09/66d96898-fa7d-0010-bca6-c68f7e60039b.html).

> ### Remember:  
> Note the following important cases when it comes to deploying a destination:
> 
> -   If you need more than one destination, you have to model each subaccount-level destination in a separate module.
> -   Use the property `force-overwrite` to choose a redeployment approach for an existing destination. Place the property at destination level, and use the value `true` to have the destination forcefully overwritten, or `false` to leave it unchanged, which is also the default behavior.
> -   If you want a destination to be created before the application that requires it, use a `required` dependency to instruct SAP BTP to define the deploy order. For example, if you have a Java application with a destination defined in its `web.xml` file, you have to use the `required` dependency so that the destination is resolved correctly when the Java application starts.

The following shows how to create a subaccount-level destination:

> ### Example:  
> ```
> modules:
>   - name: nwl
>     type: com.sap.java
>     requires:
>       - name: examplewebsite-connection
>     parameters:
>       name: networkinglunch
>       ...
>   
>   - name: examplewebsite-connection
>     type: com.sap.hcp.destination
>     parameters:
>       name: ExampleWebsite
>       type: HTTP
>       description: Connection to ExampleWebsite
>       url: http://www.examplewebsite.com
>       proxy-type: Internet
>       authentication: BasicAuthentication
>       user: myuser
>       password: mypassword
>    ...
> ```

In the example above, the module type `com.sap.hcp.destination` is used to define the subaccount-level destination. The Java module `nwl` requires it because the destination is created before starting the Java application. The required section has to ensure proper ordering.

The example above will result in a subаccount-level destination created within the consumer subaccount with credentials that are still placed into the MTA extension descriptor. If you are providing your solution for consumption by another subaccount, you might want to create that destination into the subscriber subaccount. To do this, you have to use the `owner` option.

> ### Example:  
> **MTA Deployment Descriptor**
> 
> ```
> _schema-version: '3.1'
> parameters:
>   hcp-deployer-version: '1.1.0'
> ID: com.example.basic.destination.subaccount
> version: 0.1.0
> modules:
>   - name: nwl
>     type: com.sap.java
>     requires:
>       - name: examplewebsite-connection
>     parameters:
>       name: networkinglunch
>   - name: examplewebsite-connection
>     type: com.sap.hcp.destination
>     requires:
>       - name: data-storage
>     parameters:
>       name: ExampleWebsite
>       type: HTTP
>       description: Connection to ExampleWebsite
>       url: http://www.examplewebsite.com
>       proxy-type: Internet
>       authentication: BasicAuthentication
>       user: ~{data-storage/user}
>       password: ~{data-storage/password}
>       owner: consumer
> resources:
>   - name: data-storage
>     properties:
>       user:
>       password:
> ```
> 
> **MTA Extension Descriptor**
> 
> ```
> _schema-version: '3.1'
> parameters:
>   hcp-deployer-version: '1.1.0'
> ID: com.example.basic.destination.subaccount.config
> extends: com.example.basic.destination.subaccount
> version: 0.1.0
> modules:
> resources:
>   - name: data-storage
>     properties:
>       user: myuser
>       password: mypassword
> ```

In the example above, the `examplewebsite-connection` destination is deployed to the subscriber subaccount. The untyped resource `data-storage` contains the sensitive parameters, which are deployed using the MTA extension descriptor.

> ### Note:  
> -   The reference syntax `${source/value}` is used to link the destinations `user`and `password` options.
> -   The `data-storage` resource is of `untyped` type.
> 
> For more information, see [MTA Module Types, Resource Types, and Parameters for Applications in the Neo Environment](mta-module-types-resource-types-and-parameters-for-applications-in-the-neo-environment-f1caa87.md)

In the example above, you create the destination within the subscriber subaccount, but the credentials for that destination are still provided by you. If the consumer of your solution has to provide the credentials for the destination, you have to use the `consumer-optional` metadata element.

> ### Note:  
> Note that using metadata is available in an MTA archive with schema version `3.1` and higher.

> ### Example:  
> **MTA Deployment Descriptor**
> 
> ```
> _schema-version: '3.1'
> parameters:
>   hcp-deployer-version: '1.1.0'
> ID: com.example.basic.destination.subaccount
> version: 0.1.0
> modules:
>   - name: nwl
>     type: com.sap.java
>     requires:
>       - name: examplewebsite-connection
>     parameters:
>       name: networkinglunch
>   - name: examplewebsite-connection
>     type: com.sap.hcp.destination
>     requires:
>       - name: data-storage
>     parameters:
>       name: ExampleWebsite
>       type: HTTP
>       description: Connection to ExampleWebsite
>       url: http://www.examplewebsite.com
>       proxy-type: Internet
>       authentication: BasicAuthentication
>       user: ~{data-storage/user}
>       password: ~{data-storage/password}
>       owner: consumer
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
> ```
> 
> **MTA Extension Descriptor of the Provider**
> 
> ```
> _schema-version: '3.1'
> ID: com.example.basic.destination.subaccount.config
> extends: com.example.basic.destination.subaccount
> parameters:
>   title: Subaccount Destination Example
>   description: This is an example of the sample Subaccount Destination
> 
> ```
> 
> **MTA Extension Descriptor of the Subscriber**
> 
> ```
> _schema-version: '3.1'
> ID: com.example.basic.destination.subaccount.config.subscriber
> extends: com.example.basic.destination.subaccount.config
> resources:
>   - name: data-storage
>     properties:
>       user: subscriberuser
>       password: subscriberpassword
> ```

In the example above, the `consumer-optional` metadata is used to enforce the subscriber to provide credentials. The provider's extension descriptor does not provide the credentials, but the consumer's one.

> ### Note:  
> -   The `consumer-optional` metadata is used together with the `optional` option.
> -   If you do not use the `consumer-optional` metadata when you deploy the solution to your subaccount, the operation will fail due to missing data.



<a name="loio8aacd18309394730bb6a0fdd5e937bc2__section_omn_c5j_nz"/>

## Destinations to Internal Applications

The subaccount-level destination to an internal application is a destination of type `HTTP` that points to a Java application, which in turn is part of the current MTA and will be deployed with the same solution. It is modeled as a `com.sap.hcp.destination` module type.

> ### Note:  
> -   If you need more than one destination, you have to model each subaccount-level destination in a separate module.
> -   To overwrite an already existing destination, you have to use the `force-overwrite` option. For more information, see [MTA Module Types, Resource Types, and Parameters for Applications in the Neo Environment](mta-module-types-resource-types-and-parameters-for-applications-in-the-neo-environment-f1caa87.md).

In the following example, an HTML5 application, which uses a subaccount-level destination to an internal resource, connects to a Java application as a backend. The destination uses the URL of the Java application as its URL target:

> ### Example:  
> ```
> - name: abc
>   type: com.sap.java
>   provides:
>     - name: abc
>       properties:
>         application-url: ${default-url}
>   parameters:
>     name: networkinglunch
>     ...
>  
> - name: abc-destination
>   type: com.sap.hcp.destination
>   requires:
>     - name: abc
>   parameters:
>     name: NetworkingLunchBackend
>     type: HTTP
>     url: ~{abc/application-url}
>     proxy-type: Internet
>     authentication: AppToAppSSO
>  
> - name: abc-ui
>   type: com.sap.hcp.html5
>   requires:
>     - name: abc-destination
>   parameters:
>     name: networkingui
> ```

In the example above, you can see the following:

-   The Java module type `abc``application-url` property, whose value is a placeholder. For more information about the `${default-url}` placeholder, see [MTA Module Types, Resource Types, and Parameters for Applications in the Neo Environment](mta-module-types-resource-types-and-parameters-for-applications-in-the-neo-environment-f1caa87.md).
-   The destination `abc-destination` is a module of type `com.sap.hcp.destination` and requires the Java application module.

    By requiring the Java application module, the destination can access all provided properties of that module \(namely the `application-url` property\). Later on, the destination module can use a reference to read the provided properties.

-   The destination module uses the reference to read the value of the `application-url` property.
-   The HTML5 module requires the destination module, because the destination has to be created prior to deploying the HTML5 application. The required section will ensure the proper ordering.

    For more information about the relation between HTML5 applications and destinations, see [Assign Destinations for HTML5 Applications](../50-administration-and-ops-neo/assign-destinations-for-html5-applications-bec79c9.md).


> ### Note:  
> Ensure that your applications do not have circular dependencies, that is, that the `application-url` provides its property or one Java application does not refer to the `application-url` property of another Java application module.

