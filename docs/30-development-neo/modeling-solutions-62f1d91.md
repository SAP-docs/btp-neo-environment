<!-- loio62f1d913659b4fd2812364f96e0b7fa9 -->

# Modeling Solutions

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://launchpad.support.sap.com/#/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**

In the context of SAP BTP, a solution is comprised of various application types and configurations, designed to serve a certain scenario or task flow. Typically the comprised parts of the solution are interconnected and have a common lifecycle. They are explicitly deployed, updated, deleted, configured, and monitored together.

A solution allows you to easily manage complex deployable artifacts. You can compose a solution by yourself, or you can acquire one from a third-party vendor. Furthermore, you can use the solutions to deploy artifacts that are comprised by entities external to SAP BTP, such as SAP SuccessFactors entities. This allows you to have a common management and lifecycle of artifacts spread across various SAP platforms and systems.

The following entities are required for creating a solution:

-   A Multitarget Application \(MTA\) archive, which contains all required application types and configurations as well as a deployment descriptor file. It is intended to be used as a generic artifact that can be deployed and managed on several SAP BTP subaccounts. For example, you can reuse one MTA archive on your development and productive subaccounts.
-   \(Optionally\) An МТА extension descriptor file that contains a deployment-specific data. It is intended to be used as a specific data source for a given SAP BTP subaccount. For example, you can have different extension descriptors for your development and productive subaccounts. Alternatively, you can also provide this data manually during the solution deployment.

You model the supported entities according to the MTA specification so that they can be deployed as a solution.

**Related Information**  


[Modeling Java Applications](modeling-java-applications-83d08d6.md "The SAP BTP allows you to deploy Java applications that run either on the proprietary SAP Java Web or the Java Web Tomcat runtime containers. These Java applications are com.sap.java and the java.tomcat.")

[Modeling Database Bindings](modeling-database-bindings-0acf332.md "By using а database binding, the Java applications connects to a database set up in your current subaccount or provided by another subaccount part of the same global account. This connection is modeled within your solution by setting it up during the deployment operation.")

[Modeling HTML5 Applications](modeling-html5-applications-0e8e6a0.md "You can deploy HTML5 applications to the SAP BTP by modeling it as a part of a Multitarget Application.")

[Modeling Destinations](modeling-destinations-37bddb4.md "You can connect your applications to another source by describing the source connection properties in a destination. Later on, you can access that destination from your application.")

[Modeling SAP SuccessFactors Extensions](modeling-sap-successfactors-extensions-ec35793.md "You can connect your SAP SuccessFactors system to your SAP Business Technology Platform(SAP BTP) subaccount. After you do so, you can define a solution that extends it. In more complex scenarios, you can even provide a solution that can be consumed by another SAP BTP subaccount and extend the subscribers SAP SuccessFactors system.")



[Create a Hello World Multitarget Application](create-a-hello-world-multitarget-application-4b108e8.md "To learn how to create a Hello World Multitarget Application see our Create a Hello World Multitarget Application tutorial.")

