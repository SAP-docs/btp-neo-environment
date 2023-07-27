<!-- loiodeadcc45382c4b8bb369010813e07d5b -->

# Restart Applications with Zero Downtime

The platform allows you to restart an application so that the application remains operable all the time and your users do not experience downtime.



<a name="loiodeadcc45382c4b8bb369010813e07d5b__prereq_b1j_4ys_qsb"/>

## Prerequisites

-   You have application deployment permissions for the subaccount.

-   You have available quota for at least one application process. See your compute unit quota.

-   You have configured the maximum number of processes of your application to at least one more than the current number of running processes. Otherwise, you won't be able to start a new application process.

-   You have downloaded and configured the SAP BTP console client. We recommend that you use the latest SDK.

    For more information, see [Set Up the Console Client](../30-development-neo/set-up-the-console-client-7613dee.md).




## Context

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://launchpad.support.sap.com/#/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**

Each application runs on one or more dedicated application processes. You can start one or many application processes at any given time, according to the compute unit quota that you have. Each process has a unique process ID that you can use to stop it. To restart an application non-disruptively for users, you handle individual processes rather than the application as a whole.

The procedure below describes the manual steps to execute a zero downtime restart.



## Procedure

1.  Open the command prompt and navigate to the folder containing neo.bat/sh \(`<SDK installation folder>/tools`\).

2.  List the status of the application which shows all its processes with their attributes \(ID, status, last change date\) by executing *<neo status\>*. Identify and make a note of the application process IDs, which you will need to stop in the following steps. Application processes are listed chronologically by their last change date.

    ```
    neo status --host <host> --account <subaccount_name> --application <application_name> --user <e-mail_or_user>
    ```

3.  Start a new application process of the application by executing *<neo start\>*.

    ```
    neo start --host <host> --account <subaccount_name> --application <application_name> --user <e-mail_or_user>
    ```

4.  Perform a soft shutdown for one of the old application processes:

    1.  Execute *<neo disable\>* using the ID you identified in Step 2. This command stops the creation of new connections to the application from new end users, but keeps the already running ones alive.

        ```
        neo disable --host <host> --user <email_or_user> --application-process-id <ID>  
        ```

    2.  Wait for some time so that all working sessions finish. You can monitor user requests and used resources by configuring JMX checks, or, you can just wait for a given time period that should be enough for most of the sessions to finish.

    3.  Stop the application process by executing *<neo stop\>* using the *<application-process-id\>* parameter.

        ```
        neo stop --host <host> --user <email_or_user> --application-process-id <ID>
        ```


5.  \(Optional\) Make sure the application process is stopped by checking its status using the *<application-process-id\>* parameter.

    ```
    neo status --host <host> --user <email_or_user> --application-process-id <ID>
    ```

6.  If the application is running on more than one application processes, repeat steps 3 and 4 until all the processes are stopped and the corresponding number of processes are started.




## Example

For example, if your application runs on two application processes, you need to perform the following steps:

1.  List the application processes:

    application process\(old\); application process \(old\)

2.  Start a new application process:

    application process \(old\); application process \(old\); application process \(new\)

3.  Using soft shutdown, disable and stop one of the old application processes so that you have the newly started application process and the other old application process:

    application process \(new\); application process \(old\)

4.  Repeat steps 2 and 3 so that the last remaining old application process gets stopped and a new application process is started instead:

    application process \(new\); application process \(new\)


**Related Information**  


[Perform Soft Shutdown](perform-soft-shutdown-17e8e96.md "Soft shutdown enables an operator to stop an application or application process in a way that no data is lost. Using soft shutdown gives sufficient time to finish serving end user requests or background jobs.")

[disable](disable-59fedc1.md "This command stops the creation of new connections to an application or application process, but keeps the already running sessions alive. You can check if an application or application process has been disabled by executing the status command.")

[start](start-cc417d7.md "Starts a deployed application in order to make it available for customers. In case the application is already started, the command starts an additional application process if the quota for maximum allowed number of application processes is not exceeded.")

[status](status-d4f6592.md "You can check the current status of an application or application process. The command lists all application processes with their IDs, state, last change date sorted chronologically, and runtime information.")

[JMX Checks](https://help.sap.com/viewer/64f7d2b06c6b40a9b3097860c5930641/Cloud/en-US/ef5c05a713154945b347f87b54446c2b.html "Registering JMX checks allows alerting on any metric that is based on JMX MBean attribute.") :arrow_upper_right:

