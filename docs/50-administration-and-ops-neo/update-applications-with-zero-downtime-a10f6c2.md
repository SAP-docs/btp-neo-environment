<!-- loioa10f6c2071b443698eb7dfc411d0ed6d -->

# Update Applications with Zero Downtime

The platform allows you to update an application in a manner in which the application remains operable all the time and your users do not experience downtime.



## Prerequisites

-   You have application deployment permissions for the subaccount.
-   You have at least one application process that is not in use, see your compute unit quota.
-   You have downloaded and configured the SAP BTP console client. We recommend that you use the latest SDK.

    For more information, see [Set Up the Console Client](../30-development-neo/set-up-the-console-client-7613dee.md).




## Context

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**

Each application runs on one or more dedicated application processes. You can start one or many application processes at any given time, according to the compute unit quota that you have. Each process has a unique process ID that you can use to stop it. To update an application non-disruptively for users, you handle individual processes rather than the application as a whole. The procedure below describes the manual steps to execute a zero downtime update. Use it if you want to have more control on the respective steps, for example to have a different timeout for the different application processes before stopping them. For an automated execution of the same procedure, use the rolling-update command. For more information, see [rolling-update](rolling-update-3f5d412.md).



## Procedure

1.  Open the command prompt and navigate to the folder containing neo.bat/sh \(`<SDK installation folder>/tools`\).

2.  List the status of the application which shows all its processes with their attributes \(ID, status, last change date\) by executing *<neo status\>*. Identify and make a note of the application process IDs, which you will need to stop in the following steps. Application processes are listed chronologically by their last change date.

    ```
    neo status --host <host> --account <subaccount_name> --application <application_name> --user <e-mail_or_user>
    ```

3.  Deploy the new version of your application on SAP BTP by executing *<neo deploy\>* with the appropriate parameters.

    Note that to execute the update, you need to start one additional application process with the new version. Therefore, make sure you have configured a high enough number of maximum processes for the application \(at least one higher than the number of old processes that are running\). In case you have already reached the quota for your subaccount, stop one of the already running processes, before proceeding.

    ```
    neo deploy --host <host> --account <subaccount_name> --application <application_name> --source <file_location>
     --user <e-mail_or_user> --maximum-processes <number of maximum processes that can be started for the application> 
    ```

4.  Start a new application process which is running the new version of the application by executing *<neo start\>*.

    ```
    neo start --host <host> --account <subaccount_name> --application <application_name> --user <e-mail_or_user>
    ```

5.  Use soft shutdown for the application process running the old version of the application:

    1.  Execute *<neo disable\>* using the ID you identified in Step 2. This command stops the creation of new connections to the application from new end users, but keeps the already running ones alive.

        ```
        neo disable --host <host> --user <email_or_user> --application-process-id <ID>  
        ```

    2.  Wait for some time so that all working sessions finish. You can monitor user requests and used resources by configuring JMX checks, or, you can just wait for a given time period that should be enough for most of the sessions to finish.

    3.  Stop the application process by executing *<neo stop\>* using the *<application-process-id\>* parameter.

        ```
        neo stop --host <host> --user <email_or_user> --application-process-id <ID>
        ```


6.  \(Optional\) Make sure the application process is stopped by checking its status using the *<application-process-id\>* parameter.

    ```
    neo status --host <host> --user <email_or_user> --application-process-id <ID>
    ```

7.  If the application is running on more than one application processes, repeat steps 4 and 5 until all the processes running the old version are stopped and the corresponding number of processes running the new version are started.




For example, if your application runs on two application processes, you need to perform the following steps:

1.  List the application processes running the old version:

    application process\(old\); application process \(old\)

2.  Deploy the new version of the application. As you will need to start one additional application process later, make sure you have another available application process by specifying *\--maximum-processes 3*. Since the newly deployed version does not start automatically, the running application processes remain unchanged:

    application process \(old\); application process \(old\)

3.  Start a new application process that will use the newly deployed version:

    application process \(old\); application process \(old\); application process \(new\)

4.  Using soft shutdown, disable and stop one of the application processes running the old version so that you have one application process with the old version and one with the new version:

    application process \(new\); application process \(old\)

5.  Repeat steps 3 and 4 so that the remainng application process running the old version gets stopped and a new application process with the new application version is started instead.

    application process \(new\); application process \(new\)


**Related Information**  


[rolling-update](rolling-update-3f5d412.md "The rolling-update command performs update of an application without downtime in one go.")

[Perform Soft Shutdown](perform-soft-shutdown-17e8e96.md "Soft shutdown enables an operator to stop an application or application process in a way that no data is lost. Using soft shutdown gives sufficient time to finish serving end user requests or background jobs.")

[disable](disable-59fedc1.md "This command stops the creation of new connections to an application or application process, but keeps the already running sessions alive. You can check if an application or application process has been disabled by executing the status command.")

[deploy](deploy-937db4f.md "Deploying an application publishes it to SAP BTP. Use the optional parameters to make some specific configurations of the deployed application.")

[start](start-cc417d7.md "Starts a deployed application in order to make it available for customers. In case the application is already started, the command starts an additional application process if the quota for maximum allowed number of application processes is not exceeded.")

[status](status-d4f6592.md "You can check the current status of an application or application process. The command lists all application processes with their IDs, state, last change date sorted chronologically, and runtime information.")

[JMX Checks](https://help.sap.com/viewer/64f7d2b06c6b40a9b3097860c5930641/Cloud/en-US/ef5c05a713154945b347f87b54446c2b.html "Registering JMX checks allows alerting on any metric that is based on JMX MBean attribute.") :arrow_upper_right:

