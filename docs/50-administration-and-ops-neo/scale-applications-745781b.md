<!-- loio745781b3ddb24c8a9670aff28cf09e36 -->

# Scale Applications

Each application is started on a dedicated SAP BTP Runtime. One application can be started on one or many application processes, according to the compute unit quota that you have.



## Prerequisites

-   You have downloaded and configured SAP BTP console client. For more information, see [Set Up the Console Client](../30-development-neo/set-up-the-console-client-7613dee.md).
-   Your application can run on more than one application processes



## Context

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/docs/btp/sap-business-technology-platform/sap-business-technology-platform?version=Cloud) .**

Scaling an application ensures its ability to handle more requests, if necessary. Scalability also provides failover capabilities - if one application process crashes, the application will continue to work. First, when deploying the application, you need to define the minimum and maximum number of application processes. Then, you can scale the application up and down by starting and stopping additional application processes. In addition, you can also choose the compute unit size, which provides a certain central processing unit \(CPU\), main memory and disk space.



## Procedure

1.  Open the command prompt and navigate to the folder containing neo.bat/sh \(`<SDK installation folder>/tools`\).

2.  Deploy the application, specifying *\--minimum-processes* and *\--maximum-processes*. The *\--minimum-processes* parameter defines the number of processes on which the application is started initially. Make sure it is at least 2.

    ```
    neo deploy myapp.properties --minimum-processes 2 --maximum-processes 5 
    ```

3.  Start the application. It will be started on 2 application processes.

    ```
    neo start myapp.properties 
    ```

4.  You can now scale the application up by executing the start command again. Each new execution starts another application process. You can repeat the start until you reach the maximum number of application process you defined within the quota you have purchased.

    ```
    neo start myapp.properties 
    ```

5.  If for some reason you need to scale the application down, you can stop individual application processes by using soft shutdown. Each application process has a unique process ID that you can use to disable and stop the process.

    1.  List all application processes with their attributes \(ID, status, last change date\) by executing *neo status* and identify the application process you want to stop.

        ```
        neo status myapp.properties 
        ```

    2.  Execute *neo disable* for the application process you want to stop.

        ```
        neo disable myapp.properties --application-process-id <ID>
        ```

    3.  Wait for some time so that all working sessions finish.

    4.  Stop the application process by executing *neo stop* with the appropriate parameters.

        ```
        neo stop myapp.properties --application-process-id <ID>
        ```





## Next Steps

You can also scale your application vertically by choosing the compute unit size on which it will run after the deploy. You can choose the compute unit size by specifying the `--size` parameter when deploying the application.

For example, if you have an enterprise account and have purchased a package with Premium edition compute units, then you can run your application on a Premium compute unit size, by executing

```
neo deploy --size prem myapp.properties
```

**Related Information**  


[Compute Units](../30-development-neo/compute-units-7612fba.md)

[deploy](deploy-937db4f.md "Deploying an application publishes it to SAP BTP. Use the optional parameters to make some specific configurations of the deployed application.")

[status](status-d4f6592.md "You can check the current status of an application or application process. The command lists all application processes with their IDs, state, last change date sorted chronologically, and runtime information.")

[Perform Soft Shutdown](perform-soft-shutdown-17e8e96.md "Soft shutdown enables an operator to stop an application or application process in a way that no data is lost. Using soft shutdown gives sufficient time to finish serving end user requests or background jobs.")

