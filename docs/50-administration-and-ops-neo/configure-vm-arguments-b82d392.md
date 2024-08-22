<!-- loiob82d3929218a42558146c58d2f68121e -->

# Configure VM Arguments

Using SAP BTP console client, you can configure the JRE by specifying custom VM arguments.



## Prerequisites

You have downloaded and configured the console client.

For more information, see [Set Up the Console Client](../30-development-neo/set-up-the-console-client-7613dee.md).



## Context

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of the following technology portfolios: application development; process automation; integration; data, analytics, and enterprise planning; artificial intelligence. The platform offers users the ability to turn data into business value, compose end-to-end business processes, connect entire IT landscapes, and personalize, build and extend SAP applications. This reduces the overall total cost of ownership maintaining SAP landscapes and third-party software across end-to-end business processes.") :arrow_upper_right:.**

You can configure the following arguments:

-   System properties - they will be used when starting the application process. For example *\{\{-D<key\>=<value\>\}\}* 
-   Memory arguments - use them to define custom memory settings of your compute units. The supported memory settings are:

    *\-Xms<size\>*- set initial Java heap size

    *\-Xmx<size\>* - set maximum Java heap size

    *\-XX:PermSize* - set initial Java Permanent Generation size

    *\-XX:MaxPermSize* - set maximum Java Permanent Generation size


> ### Note:  
> We recommend that you use the default memory settings. Change them only if necessary and note that this may impact the application performance or its ability to start.



## Procedure

1.  Open the command prompt and navigate to the folder containing neo.bat/sh \(`<SDK installation folder>/tools`\).

2.  Deploy the application, specifying your desired configurations. For example, if you want to specify a currency and maximum heap size 1 GiB, then execute the deploy with the following parameters:

    ```
    neo deploy myapp.properties --vm-arguments "-Dcurrency=EUR -Xmx1024m"
    ```

    > ### Note:  
    > If you are deploying using the properties file, note that you have to use double quotation marks twice: `vm-arguments=""-Dcurrency=EUR -Xmx1024m""`.

    This will set the system properties *\-Dcurrency=EUR* and the memory argument *\-Xmx1024m*.

    To specify a value that contains spaces \(for example, *\-Dname=John Doe*\), note that you have to use single quotation marks for this parameter when deploying.

    ```
    neo deploy myapp.properties --vm-arguments "-Dcurrency=EUR '-Dname=John Doe' -Xmx1024m"
    ```


**Related Information**  


[Console Client for the Neo Environment](console-client-for-the-neo-environment-7613230.md)

[deploy](deploy-937db4f.md "Deploying an application publishes it to SAP BTP. Use the optional parameters to make some specific configurations of the deployed application.")

