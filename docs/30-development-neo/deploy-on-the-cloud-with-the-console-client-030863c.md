<!-- loio030863cd5d0d4dd3b742957970f8eec9 -->

# Deploy on the Cloud with the Console Client

Deploying an application publishes it to SAP BTP. During deploy, you can define various specifics of the deployed application using the deploy command optional parameters.



<a name="loio030863cd5d0d4dd3b742957970f8eec9__prereq_N10019_N10016_N10001"/>

## Prerequisites

-   You have downloaded and configured SAP BTP console client. For more information, see [Set Up the Console Client](set-up-the-console-client-7613dee.md)
-   Depending on your subaccount type, deploy the application on the respective region host. For more information, see [Regions](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/350356d1dc314d3199dca15bd2ab9b0e.html "You can deploy applications in different regions. Each region represents a geographical location (for example, Europe, US East) where applications, data, or services are hosted.") :arrow_upper_right:



## Context

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://launchpad.support.sap.com/#/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**



## Procedure

1.  In the opened command line console, execute `neo deploy` command with the appropriate parameters.

    You can define the parameters of commands directly in the command line as in the example below, or in the properties file. For more information, see [Using the Console Client](../50-administration-and-ops-neo/using-the-console-client-8900b22.md).

2.  Enter your password if requested.

3.  Press ENTER and deployment of your application will start. If deployment fails, check if you have defined the parameters correctly.

    > ### Note:  
    > The size of an application deployed on SAP BTP can be up to 1.5 GB. If the application is packaged as a WAR file, the size of the unzipped content is taken into account.




## Example

```
neo deploy --host <host> --account <subaccount_name> --application <application_name> --source samples/deploy_war/example.war --user <email_or_user>  
```



<a name="loio030863cd5d0d4dd3b742957970f8eec9__postreq_N1005A_N10016_N10001"/>

## Next Steps

To make your deployed application available for requests, you need to start it by executing the `neo start` command.

Then, you can manage the application lifecycle \(check the status; stop; restart; undeploy\) using dedicated console client commands.

**Related Information**  


[deploy](../50-administration-and-ops-neo/deploy-937db4f.md "Deploying an application publishes it to SAP BTP. Use the optional parameters to make some specific configurations of the deployed application.")

[start](../50-administration-and-ops-neo/start-cc417d7.md "Starts a deployed application in order to make it available for customers. In case the application is already started, the command starts an additional application process if the quota for maximum allowed number of application processes is not exceeded.")

[restart](../50-administration-and-ops-neo/restart-7c0f7a1.md "Use this command to restart your application or a single application process. The effect of the restart command is the same as executing the stop command first and when the application is stopped, starting it with the start command.")

[stop](../50-administration-and-ops-neo/stop-b5bfcbf.md "Use this command to stop your deployed and started application or application process.")

[status](../50-administration-and-ops-neo/status-d4f6592.md "You can check the current status of an application or application process. The command lists all application processes with their IDs, state, last change date sorted chronologically, and runtime information.")

[undeploy](../50-administration-and-ops-neo/undeploy-7e09b85.md "Undeploying an application removes it from SAP BTP. To undeploy an application, you have to stop it first.")

[Use Delta Deployment](use-delta-deployment-7a4aba2.md "By using the delta deployment option, you can apply changes in a deployed application faster without uploading the entire set of files tо SAP BTP.")

[Managing Applications in the Neo Console Client](../50-administration-and-ops-neo/managing-applications-in-the-neo-console-client-87cfe1b.md "If you are an application operator and need to deploy a new version of a productive application or perform maintenance, you can choose among several approaches.")

[Update Application Properties](../50-administration-and-ops-neo/update-application-properties-cadb1dd.md "You can update a property of an application running on SAP BTP without redeploying it.")

