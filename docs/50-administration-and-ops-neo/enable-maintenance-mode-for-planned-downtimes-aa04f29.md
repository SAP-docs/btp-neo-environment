<!-- loioaa04f29a908f4db7b7666c12552ddd53 -->

# Enable Maintenance Mode for Planned Downtimes

An operator can start and stop planned application downtime, during which a customized maintenance page for that application is shown to end users.



## Prerequisites

To redirect an application, you need a maintenance application. A maintenance application replaces your application for a temporary period and can be as simple as a static page or have more complex logic. You need to provide the maintenance application yourself and ensure that it meets the following conditions:

-   It is a Java application.
-   It is deployed in the same subaccount as your application.
-   It has been started, that is, it is up and running.
-   It must not be in maintenance itself.
-   Its context path must be the same as the context path of the original application.



## Context

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/docs/btp/sap-business-technology-platform/sap-business-technology-platform?version=Cloud) .**

> ### Note:  
> Not applicable to *hanatrial.ondemand.com*.

<a name="task_xw4_xrx_4n"/>

<!-- task\_xw4\_xrx\_4n -->

## Cockpit



## Context

You can enable the maintenance mode for an application from the overview page for the application. An application can be put into maintenance mode only if it is not being used as a maintenance application itself and is running \(*Started* state\).



<a name="task_xw4_xrx_4n__steps_cmq_xrx_4n"/>

## Procedure

1.  Log on to the cockpit, select a subaccount and choose *Applications* \> *Java Applications* in the navigation area.

2.  Click the application's name in the list to open the application overview page and in the *Application Maintenance* section choose ![](images/Maintenance_On_Icon_8bbf58a.png) \(*Start Maintenance*\).

3.  In the dialog box, select the application that will serve as the maintenance application and choose *Set Selected Application*. In the application list, the application’s state is now shown as *Started \(In Maintenance\)*.

    From this point on, new connections will be redirected to the maintenance application. All active connections will still be handled until the application is stopped.

4.  Optional: To view the details in the *Application Maintenance* section, select your application in the list.

    The following details confirm that your application is in maintenance mode:

    -   ![](images/In_Maintenance_Icon_2e1da1e.png)*In Maintenance*
    -   A link to the assigned maintenance application: Click the link to open the overview page for this application.




## Results

Note that HTTP requests from already active sessions are redirected to the original application, if able. This approach makes sure that end users can complete their work without noticing the application downtime. Only new HTTP requests are redirected to the maintenance application.

The temporary redirect to the maintenance application remains effective until you take your application out of maintenance. To disable the maintenance mode, choose ![](images/Maintenance_Off_Icon_c3f0dd0.png) \(*Switch maintenance mode off*\). Before doing so, you should ensure that your application is up and running to avoid end users experiencing HTTP errors.

<a name="task_y4m_vwg_nn"/>

<!-- task\_y4m\_vwg\_nn -->

## Console Client



<a name="task_y4m_vwg_nn__steps_etp_wwg_nn"/>

## Procedure

1.  Open the command prompt and navigate to the folder containing neo.bat/sh \(`<SDK installation folder>/tools`\).

2.  Start the planned application downtime by executing *<neo start-maintenance\>* in the command line. This stops traffic to the application and registers a maintenance page application. All active connections will be still handled until the application is stopped.

    ```
    neo start-maintenance --host <host> --account <subaccount_name> --application <application_name> --user <e-mail_or_user> 
    --maintenance-application <maintenance application name> 
    ```

    If you want to have access to an application during maintenance, use the `--direct-access-code` parameter. For more information, see [start-maintenance](start-maintenance-f42be92.md).

3.  Perform the planned maintenance, update, or configuration of your application:

    1.  Before stopping the application, wait for the working sessions to finish. You can wait for a given time period that should be enough for most of the sessions to finish, or configure JMX checks to monitor user requests and used resources. For more information, see [Configure JMX Checks for Java Applications from the Console Client](https://help.sap.com/viewer/64f7d2b06c6b40a9b3097860c5930641/Cloud/en-US/21d734fa88f44298a8a9cb1f759f8fb9.html "Configure a JMX check from the console client to monitor your Java application.") :arrow_upper_right:

    2.  Stop the application by executing:

        ```
        neo stop --host <host> --account <subaccount_name> --application <application_name> --user <email_or_user> 
        ```

    3.  Deploy the new version of your application by executing:

        ```
        neo deploy --host <host> --account <subaccount_name> --application <application_name> --source <file_location>
         --user <e-mail_or_user> 
        ```

    4.  Start the new version of the application by executing:

        ```
        neo start --host <host> --account <subaccount_name> --application <application_name> --source <file_location>
         --user <e-mail_or_user> 
        ```


4.  Stop the planned application downtime by executing *<neo stop-maintenance\>* in the command line. This resumes traffic to the application and the maintenance page application stops handling incoming requests.

    ```
    neo stop-maintenance --host <host> --account <subaccount_name> --application <application_name>  --user <e-mail_or_user>
    ```


**Related Information**  


[start-maintenance](start-maintenance-f42be92.md "This command starts the planned downtime of an application, during which it no longer receives requests and a custom maintenance page for that application is shown to the user. All active connections will still be handled until the application is stopped.")

[stop-maintenance](stop-maintenance-3fbd6fe.md "This command stops the planned downtime of an application, starts traffic to it and deregisters the maintenance application page.")

[deploy](deploy-937db4f.md "Deploying an application publishes it to SAP BTP. Use the optional parameters to make some specific configurations of the deployed application.")

[start](start-cc417d7.md "Starts a deployed application in order to make it available for customers. In case the application is already started, the command starts an additional application process if the quota for maximum allowed number of application processes is not exceeded.")

