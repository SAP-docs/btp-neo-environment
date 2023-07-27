<!-- loio13afe5ca6e38485d8e6523f610c0ed29 -->

# Choose Application Runtime Version

Applications deployed on SAP BTP are always started on the latest version of the application runtime container. This version contains all released fixes, critical patches and enhancements and is respectively the recommended option for applications. In some special cases, you can choose the version of the runtime container your application uses by specifying it with the parameter *<--runtime-version\>* when deploying your application. To change this version, you need to redeploy the application without specifying this parameter.



## Prerequisites

You have downloaded and configured SAP BTP console client. For more information, see [Set Up the Console Client](../30-development-neo/set-up-the-console-client-7613dee.md).



## Context

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://launchpad.support.sap.com/#/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**

If you want to choose the version of the application runtime container, follow the procedure.



## Procedure

1.  Open the command prompt and navigate to the folder containing neo.bat/sh \(<SDK installation folder\>/tools\).

2.  In the console client command line, execute the *<list-runtime-versions\>* command to display all recommended versions. We recommend that you choose the latest available version.

3.  Redeploy your application with parameter *<--runtime-version\>* set to the selected version number.

    ```
    neo deploy --account <subaccount_name> --application <application_name> --source <file_location> --user <email_or_user>
     --runtime-version <your_chosen_version >
    ```

4.  Restart your application using the *<restart\>* command.

    If you want to return the default behavior when the application is always started on the latest version of the application runtime, redeploy your application without specifying the *<--runtime-version\>* parameter.

    > ### Caution:  
    > By selecting an older version of the application runtime, you do not have the latest released fixes and critical patches as well as enhancements, which may affect the smooth operation and supportability of your application. Consider updating the selected version periodically. Plan the updates to the latest version of the application runtime and apply in your test environment first. Older application runtime versions will be deprecated and expire. Refer to the *<list-runtime-versions\>* command for information.


**Related Information**  


[deploy](deploy-937db4f.md "Deploying an application publishes it to SAP BTP. Use the optional parameters to make some specific configurations of the deployed application.")

[start](start-cc417d7.md "Starts a deployed application in order to make it available for customers. In case the application is already started, the command starts an additional application process if the quota for maximum allowed number of application processes is not exceeded.")

[View Runtime Information](view-runtime-information-343663e.md "View information about the application runtime. SAP BTP provides a set of runtimes. You can choose the application runtime during application deployment.")

