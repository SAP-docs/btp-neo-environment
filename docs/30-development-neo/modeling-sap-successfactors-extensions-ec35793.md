<!-- loioec3579359e86435cb343a7874e01acd8 -->

# Modeling SAP SuccessFactors Extensions

You can connect your SAP SuccessFactors system to your SAP Business Technology Platform\(SAP BTP\) subaccount. After you do so, you can define a solution that extends it. In more complex scenarios, you can even provide a solution that can be consumed by another SAP BTP subaccount and extend the subscribers SAP SuccessFactors system.

> ### Caution:  
> The legacy home page is in deprecation. It's no longer available for most customers.

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**

> ### Note:  
> Make sure that:
> 
> -   You have onboarded an SAP SuccessFactors company in your SAP BTP subaccount. If you are providing a solution that is consumed by another subaccount in the SAP BTP, the subscriber subaccount is responsible for onboarding the SAP SuccessFactors company. See [Configuring the Subaccount in SAP BTP for SAP SuccessFactors](../40-extensions-neo/configuring-the-subaccount-in-sap-btp-for-sap-successfactors-4f31621.md).
> -   You have a database and valid credentials.

In the example below, you will create a standard SAP SuccessFactors extension. The “Benefits” sample Java application provided by SAP is used. It is located at [https://github.com/SAP/cloud-sfsf-benefits-ext](https://github.com/SAP/cloud-sfsf-benefits-ext).

> ### Note:  
> If you intend to provide this solution for consumption by other subaccounts:
> 
> -   The sample “Benefits” Java Application will be deployed to your subaccount, but the SAP SuccessFactors artifacts will be deployed to the subscriber subaccounts and their SAP SuccessFactors systems.
> -   You can define an additional МТА extension descriptor for your subscribers, so that they can add their own specific data.

As a result, their solution is going to have:

-   The sample “Benefits” Java application
-   A database binding for the sample “Benefits” Java application
-   The SAP SuccessFactorstile and SAP SuccessFactors role are going to be deployed to the SAP SuccessFactors company
-   Connectivity for the sample “Benefits” Java application to an SAP SuccessFactors system

> ### Note:  
> For the example below, we assume that you have the following:
> 
> -   Database alias `tst`
> -   Database credentials `myuser` and `mypassword`

You have to model the sample “Benefits” Java application as a module into the MTA deployment descriptor. You also have to define an SAP SuccessFactors Role module and a database binding resource.

> ### Caution:  
> The *technical-user* property results in the *systemUser* property in the destination that is created. The *systemUser* property is deprecated and will be removed soon. We recommend that you work on behalf of specific \(named\) users instead of working with a technical user.
> 
> See [OAuth SAML Bearer Assertion Authentication](https://help.sap.com/viewer/cca91383641e40ffbe03bdc78f00f681/Cloud/en-US/c69ea6aacd714ad2ae8ceb5fc3ceea56.html "Create and configure an OAuth SAML Bearer Assertion destination for an application in the Cloud Foundry environment.") :arrow_upper_right:.

> ### Example:  
> ```
> _schema-version: '3.1'
> parameters:
>   hcp-deployer-version: '1.1.0'
> ID: com.example.basic.sfsf
> version: 0.1.0
> modules:
>   - name: benefits-app
>     type: com.sap.java
>     parameters:
>        name: benefits
>        jvm-arguments: -server
>        java-version: JRE 7
>        runtime: neo-java-web
>        runtime-version: 1
>        sfsf-idp-access: true
>        sfsf-connections:
>          - type: default
>            additional-properties:
>               nameIdFormat: 'urn:oasis:names:tc:SAML:1.1:nameid-format:unspecified'
>          - type: technical-user
>            technical-user-id: SFSFAdmin
>        sfsf-outbound-connections:
>          - type: OAuth2SAMLBearerAssertion
>            name: BenefitsOutboundConnection
>            subject-name-id: mail
>            subject-name-id-format: EMAIL_ADDRESS
>            assertion-attributes-mapping:
>               firstname: firstname
>               lastname: lastname
>               email: email
>        role-provider: sfsf
>        sfsf-home-page-tiles:
>          resource: resources/benefits-tiles.json
>     requires:
>      - name: dbbinding
>      - name: benefits-roles 
>   - name: benefits-roles
>     type: com.sap.hcp.sfsf-roles
> resources:
>   - name: dbbinding
>     type: com.sap.hcp.persistence
>     parameters:
>       id: tst
> ```

In the example above, you can see the following:

-   The sample “Benefits” Java application module requires both database binding resource and the SAP SuccessFactors Roles module.
-   The SAP SuccessFactors tile is defined as a parameter of the sample “Benefits” Java application and points to a `JSON` file within the Multitarget Application archive
-   SAP SuccessFactors provider is defined as a parameter of the sample “Benefits” Java application
-   The sample “Benefits” Java application is going to use the SAP SuccessFactors IDP for authentication
-   The sample “Benefits” Java application is going to use the default connectivity options when accessing the SAP SuccessFactors system

Both the SAP SuccessFactors roles and tiles require additional files to be added to the Multitarget Application archive. The deployment descriptor contains only the modeling of those entities, but their actual content is external to the MTA deployment descriptor, in the same way as the sample “Benefits” Java application `.war` archive.

You also have to create a `JSON` file `benefits-tiles.json` that contains the SAP SuccessFactors tiles.

> ### Example:  
> ```
> 
> [
>     {
>         "name" : "SAP Corporate Benefits",
>         "path" : "com.sap.hana.cloud.samples.benefits",
>         "size" : 3,
>         "padding" : false,
>         "roles" : ["Corporate Benefits Admin"],
>         "metadata" : [
>             {
>                 "title" : "SAP Corporate Benefits",
>                 "description" : "SAP Corporate Benefits home page tile",
>                 "locale" : "en_US"
>             }
>         ]
>     }
> ]
> ```

In the example above, you can see an example of an SAP SuccessFactors tile for the sample “Benefits” Java application.

Next you have to create a `JSON` file `benefits-roles.json` that contains the SAP SuccessFactors roles.

> ### Example:  
> ```
> [
>     {
>         "roleDesc": "SAP Corporate Benefits Administrator",
>         "roleName": "Corporate Benefits Admin",
>         "permissions": []
>     }
> ]
> ```

In the example above, you can see an example of an SAP SuccessFactors role for the sample “Benefits” Java application.

Afterward, you have to create your `MANIFEST.MF` file and define the Java application, roles, and tiles.

> ### Example:  
> ```
> Manifest-Version: 1.0
> Created-By: SAP SE
> 
> Name: resources/benefits-roles.json
> Content-Type: application/json
> MTA-Module: benefits-roles
> 
> Name: com.sap.hana.cloud.samples.benefits.war
> Content-Type: application/zip
> MTA-Module: benefits-app
> 
> 
> ```

In the example above, you can see the following:

-   Entry that links your SAP SuccessFactors roles with the MTA deployment descriptor
-   Entry that links your “Benefits” sample Java application with the MTA deployment descriptor

Now you can create your Multitarget Application archive by following the JAR file specification. The archive structure has to be as follows:

> ### Example:  
> ```
> /com.sap.hana.cloud.samples.benefits.war
> /META-INF 
> /META-INF/mtad.yaml
> /META-INF/MANIFEST.MF
> /resources/benefits-roles.json
> /resources/benefits-tiles.json 
> ```

Start by creating an MTA extension descriptor that holds the security-sensitive data, such as credentials.

> ### Note:  
> Make sure that you always use an extension descriptor when you have sensitive data within your solution.

> ### Example:  
> ```
> _schema-version: '3.1'
> ID: com.example.basic.sfsf.config
> extends: com.example.basic.sfsf
> parameters:
>   title: SuccessFactors example
>   description: This is an example of the sample Benefits Java Application for SuccessFactors
> resources:
>   - name: dbbinding
>     parameters:
>       user-id: myuser
>       password : mypassword
> ```

In the example above, the extension descriptor adds the `user-id` and `password` parameters to the resource dbbinding, which is modeled in the deployment descriptor.

After you deploy your solution, you can open its tile in the cockpit and check if the SAP SuccessFactors extension solution is deployed.

**Related Information**  




[Operating Solutions](operating-solutions-2abf7d4.md "You can deploy, update, monitor, and delete a solution.")

[The Multitarget Application Model v.2](http://go.sap.com/documents/2016/06/e2f618e4-757c-0010-82c7-eda71af511fa.html)

[The Multitarget Application Model v.3](https://www.sap.com/documents/2021/09/66d96898-fa7d-0010-bca6-c68f7e60039b.html)

[JAR file specification](http://docs.oracle.com/javase/7/docs/technotes/guides/jar/jar.html)

