<!-- loio937c833b72bb101490cf767db0e91070 -->

# Deploy Locally with the Console Client

The console client allows you to install a server runtime in a local folder and use it to deploy your application.



## Context

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**



<a name="loio937c833b72bb101490cf767db0e91070__steps_yrq_gfx_sj"/>

## Procedure

1.  Open the folder `<SDK installation folder>/tools`.

2.  Open the command window, enter the following command, and press [ENTER\]:

    ```
    neo install-local
    ```

    This installs a server runtime in the default local server directory `<SDK installation folder>/server`. To use an alternative directory, enter the command together with the following optional command argument:

    ```
    --location <local server directory>
    ```

3.  To start the local server, enter the following command and press [ENTER\]:

    ```
    neo start-local
    ```

    This starts a local server instance in the default local server directory `<SDK installation folder>/server`. Again, use the following optional command argument to specify another directory:

    ```
    --location <local server directory>
    ```

4.  To deploy your application, enter the following command as shown in the example below and press [ENTER\]:

    ```
    neo deploy-local --source hello-world.war
    ```

    This deploys the WAR file on the local server instance. If necessary, specify another directory as in step 3.

5.  To check your application is running, open a browser and enter the URL, for example:

     `http://localhost:8080/hello-world` 

    > ### Note:  
    > The HTTP port is normally 8080. However, the exact port configurations used for your local server, including the HTTP port, are displayed on the console screen when you install and start the local server.

6.  To stop the local server instance, enter the following command from the `<SDK installation folder>/tools` folder and press [ENTER\]:

    ```
    neo stop-local
    ```


**Related Information**  


[install-local](../50-administration-and-ops-neo/install-local-8527947.md "This command installs a server runtime in a local folder, by default <SDK installation folder>/server.")

[start-local](../50-administration-and-ops-neo/start-local-cd54325.md "This command starts a local server instance.")

[deploy-local](../50-administration-and-ops-neo/deploy-local-8fdc143.md "This command deploys WAR files on a local server instance.")

[stop-local](../50-administration-and-ops-neo/stop-local-ee02d4d.md "This command stops a local server instance.")

