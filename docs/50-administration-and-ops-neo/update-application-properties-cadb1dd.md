<!-- loiocadb1dd3cda3464b8a5315a08cbb0566 -->

# Update Application Properties

You can update a property of an application running on SAP BTP without redeploying it.



## Context

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of the following technology portfolios: application development; process automation; integration; data, analytics, and enterprise planning; artificial intelligence. The platform offers users the ability to turn data into business value, compose end-to-end business processes, connect entire IT landscapes, and personalize, build and extend SAP applications. This reduces the overall total cost of ownership maintaining SAP landscapes and third-party software across end-to-end business processes.") :arrow_upper_right:.**

Application properties are configured during deployment with a set of deploy parameters in the SAP BTP console client. If you want to change any of these properties \(Java version, runtime version, compression, VM arguments, compute unit size, URI encoding, minimum and maximum application processes\) without the need to redeploy the application binaries, use the `set-application-property` command. Execute the command separately for each property that you want to set.



## Procedure

1.  Open the command prompt and navigate to the folder containing neo.bat/sh \(<SDK installation folder\>/tools\).

2.  Execute `set-application-property` specifying the new value of one property that you want to change. For example, to change the compute unit size to premium, execute:

    ```
    neo set-application-property myapp.properties --compute-unit prem
    ```

3.  For the change to take effect, restart your application using the `restart` command.


**Related Information**  


[set-application-property](set-application-property-113e957.md "Use this command to change the value of a single property of a deployed application without the need to redeploy it. Execute the command separately for each property that you want to set. For the changes to take effect, restart the application.")

[deploy](deploy-937db4f.md "Deploying an application publishes it to SAP BTP. Use the optional parameters to make some specific configurations of the deployed application.")

[restart](restart-7c0f7a1.md "Use this command to restart your application or a single application process. The effect of the restart command is the same as executing the stop command first and when the application is stopped, starting it with the start command.")

[Deploy on the Cloud with the Cockpit](../30-development-neo/deploy-on-the-cloud-with-the-cockpit-abded96.md "The cockpit allows you to deploy Java applications as WAR files and supports a number of deployment options for configuring the application.")

