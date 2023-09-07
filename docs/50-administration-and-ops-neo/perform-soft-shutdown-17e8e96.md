<!-- loio17e8e9622e63434a880f322f75db3e8e -->

# Perform Soft Shutdown

Soft shutdown enables an operator to stop an application or application process in a way that no data is lost. Using soft shutdown gives sufficient time to finish serving end user requests or background jobs.



## Prerequisites

You have application deployment permissions for the subaccount.



## Context

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**

Using soft shutdown, an operator can restart the application \(for example, in order to update it\) in a way that end users are not disturbed. First, the application process is disabled. This means that requests by users that already have open connections to this process will be processed, but new requests will not reach this application process anymore. After the application process is disabled and remaining sessions processed, it can be stopped by the operator.

<a name="task_wxl_w4g_nn"/>

<!-- task\_wxl\_w4g\_nn -->

## Cockpit



## Context

You can disable application processes in the *Processes* panel on the application dashboard or the *State* panel on the process dashboard.



<a name="task_wxl_w4g_nn__steps_w2n_cc5_kn"/>

## Procedure

1.  Log on to the cockpit, select an subaccount and choose *Applications* \> *Java Applications* in the navigation area.

2.  Select an application in the application list.

3.  In the *Processes* panel, choose ![](images/Disable_Icon_5a8e636.png) \(*Disable process*\) in the relevant row. The process state changes to *Started \(disabled\)*.

    > ### Note:  
    > You can also select the process and disable it from the process dashboard.

4.  Wait for some time so that all working sessions finish and then stop the process.


**Related Information**  


[Start and Stop Applications](start-and-stop-applications-7612f03.md "You can directly start, stop, and undeploy applications, as well as start, stop, and disable individual application processes.")

<a name="task_rn4_5sx_4n"/>

<!-- task\_rn4\_5sx\_4n -->

## Console Client



<a name="task_rn4_5sx_4n__steps_x44_5sx_4n"/>

## Procedure

1.  Open the command prompt and navigate to the folder containing neo.bat/sh `(<SDK installation folder>/tools)`.

2.  Disable processing of requests from new users to the application by executing *<neo disable\>* with the appropriate parameters. If you want to stop requests to a specific application process only and not to the whole application, add the *<--application-process-id\>* parameter.

    ```
    neo disable --host <host> --user <e-mail_or_user> --application-process-id <ID>
    ```

    If you disable the entire application, or all processes of the application, then new users requesting the application will not be able to access it and will get an error.

3.  Wait for some time so that all working sessions finish.

    You can monitor user requests and used resources by configuring JMX checks, or, you can just wait for a given time period that should be enough for most of the sessions to finish.

4.  Stop the application by executing *<neo stop\>* with the appropriate parameters. If you want to terminate a specific application process only and not the whole application, add the *<--application-process-id \>*parameter.

    ```
    neo stop --host <host> --user <e-mail_or_user> --application-process-id <ID> 
    ```


**Related Information**  


[disable](disable-59fedc1.md "This command stops the creation of new connections to an application or application process, but keeps the already running sessions alive. You can check if an application or application process has been disabled by executing the status command.")

[JMX Checks](https://help.sap.com/viewer/64f7d2b06c6b40a9b3097860c5930641/Cloud/en-US/ef5c05a713154945b347f87b54446c2b.html "Registering JMX checks allows alerting on any metric that is based on JMX MBean attribute.") :arrow_upper_right:

