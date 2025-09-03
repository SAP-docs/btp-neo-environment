<!-- loioabded969628240259d486c4b29b3948c -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Deploy on the Cloud with the Cockpit

The cockpit allows you to deploy Java applications as WAR files and supports a number of deployment options for configuring the application.



## Context

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/docs/btp/sap-business-technology-platform/sap-business-technology-platform?version=Cloud) .**



## Procedure

1.  Log on to the cockpit and select an account.

2.  Choose *Java Applications* in the navigation area.

3.  Choose *Deploy Application*.

4.  Select the WAR file that you want to deploy, for example, in directory `<SDK_location>/tools/samples/deploy_war`.

5.  Use the application name that the cockpit proposes to you. It's the same name as for the WAR file. Alternatively, enter an application name. Note that application names must start with a letter, can contain lowercase letters and numbers only, and must not exceed 30 characters.

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

6.  Optionally specify additional parameters to configure the application. If omitted, default values are assigned.

    For more information about the deploy parameters, see the [deploy](../50-administration-and-ops-neo/deploy-937db4f.md) command documentation.

7.  Choose *Deploy* to deploy the WAR file to the cloud platform.

    > ### Note:  
    > Make sure that the subaccount size hasn't reached the allowed 100-GB quota for Java applications.
    > 
    > If the used space exceeds 80% of the subaccount size quota, the *Used space:* progress bar shows a <span style="color:#d14900;"><span class="SAP-icons-V5"></span></span> \(Warning\) status. In such a case, you can still deploy Java applications until you reach the maximum subaccount size quota.
    > 
    > If the used space reaches the maximum subaccount size quota, the *Used space:* progress bar shows an <span style="color:#cc1919;"><span class="SAP-icons-V5"></span></span> \(Error\) status. In such a case, you can't deploy Java applications.

    -   The *Deploy Application* dialog box remains on the screen while the deployment is in progress. When the deployment is over, a confirmation appears that the application has been successfully deployed. Note that at this stage the application isn’t yet up and running.

    -   The *Used space:* progress bar is updated to show what percent of the subaccount size quota is used for Java applications.

    -   The size of the deployed Java application in megabytes is also included in the list of Java applications. If the size of the application is less than 0.1 MB, the value in the *Size* column shows *< 0.1 MB*.


8.  In the dialog box, choose one of the following options:

    -   *Start*: Start the application to activate its URL and make the application available to your end users.
    -   *Close*: Simply close the dialog box if you don't want to start the application immediately.




## Results

Your newly deployed application appears in the list of Java applications.

**Updating a deployed application**

You can update or redeploy the application whenever required. To do this operation, choose an application from the list of deployed Java applications. Then choose the *Update* button. You can update the application with a new WAR file or change the configuration parameters.

To change the name of a deployed application, deploy a new application under the desired name, and delete the application whose name you want to change.

**Related Information**  


[deploy](../50-administration-and-ops-neo/deploy-937db4f.md "Deploying an application publishes it to SAP BTP. Use the optional parameters to make some specific configurations of the deployed application.")

[Define Application Details \(Java Apps\)](../50-administration-and-ops-neo/define-application-details-java-apps-9b23270.md "You can view details about your currently selected Java application. By adding a suitable display name and a description, you can identify the application more easily.")

