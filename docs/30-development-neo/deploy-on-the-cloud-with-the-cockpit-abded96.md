<!-- loioabded969628240259d486c4b29b3948c -->

# Deploy on the Cloud with the Cockpit

The cockpit allows you to deploy Java applications as WAR files and supports a number of deployment options for configuring the application.



## Context

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**



## Procedure

1.  Log on to the cockpit and select an account.

2.  Choose *Java Applications* in the navigation area.

3.  Choose *Deploy Application*.

4.  Select the WAR file that you want to deploy, for example, in directory `<SDK_location>/tools/samples/deploy_war`.

5.  Use the application name that the cockpit proposes to you. It is the same name as for the WAR file. Alternatively, enter an application name. Note that application names must start with a letter, can contain lowercase letters and numbers only, and must not exceed 30 characters.

    You can also assign a display name and a description to a Java application.

    > ### Note:  
    > When the sum of the characters of the subaccount technical name and the application name exceeds 30, the default application URL is truncated. This means that parts of the subaccount name and the application name will be missing from the application URL:
    > 
    > > ### Example:  
    > > Subaccount name: mycompanyextensionspoc
    > > 
    > > Application name: myappsimplesimplereq
    > > 
    > > Application URL: `https://myappsimplemycompanyextensions.us1.hana.ondemand.com`

6.  Optionally specify additional parameters to configure the application. If omitted, default values will be assigned.

    For more information about the deploy parameters, see the [deploy](../50-administration-and-ops-neo/deploy-937db4f.md) command documentation.

7.  Choose *Deploy* to deploy the WAR file to the cloud platform.

    The *Deploy Application* dialog box remains on the screen while the deployment is in progress. When the deployment is over, a confirmation appears that the application has been successfully deployed. Note that at this stage the application is not yet up and running.

8.  In the dialog box, choose one of the following options:

    -   *Start*: Start the application to activate its URL and make the application available to your end users.
    -   *Close*: Simply close the dialog box if you do not want to start the application immediately.




## Results

Your newly deployed application appears in the list of Java applications.

**Updating a deployed application**

You can update or redeploy the application whenever required. To do this, choose *Update application* to open the same dialog box as in update mode. You can update the application with a new WAR file or change the configuration parameters.

To change the name of a deployed application, deploy a new application under the desired name, and delete the application whose name you want to change.

**Related Information**  


[deploy](../50-administration-and-ops-neo/deploy-937db4f.md "Deploying an application publishes it to SAP BTP. Use the optional parameters to make some specific configurations of the deployed application.")

[Define Application Details \(Java Apps\)](../50-administration-and-ops-neo/define-application-details-java-apps-9b23270.md "You can view details about your currently selected Java application. By adding a suitable display name and a description, you can identify the application more easily.")

