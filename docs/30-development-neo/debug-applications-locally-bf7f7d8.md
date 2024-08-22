<!-- loiobf7f7d8fa4d54a2ba6c96181b3be2ec4 -->

# Debug Applications Locally

In this section, you can learn how to debug a Web application locally.



## Prerequisites

-   You have developed an application. For more information, see [Using Samples](using-samples-937ce0d.md).

-   You have installed SAP BTP SDK for the Neo environment. See [Install the SAP BTP SDK for Neo Environment](install-the-sap-btp-sdk-for-neo-environment-7613843.md).




## Context

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of the following technology portfolios: application development; process automation; integration; data, analytics, and enterprise planning; artificial intelligence. The platform offers users the ability to turn data into business value, compose end-to-end business processes, connect entire IT landscapes, and personalize, build and extend SAP applications. This reduces the overall total cost of ownership maintaining SAP landscapes and third-party software across end-to-end business processes.") :arrow_upper_right:.**



## Procedure

1.  Deploy your application locally using the console client on the Neo environment. For more information, see [Deploy Locally with the Console Client](deploy-locally-with-the-console-client-937c833.md).

2.  Before starting the local server, enable remote debugging.

    -   For Microsoft Windows:

        Add the following text in the end of your `/<SDK installation folder>/server/bin/setenv.bat`:

        `set CATALINA_OPTS="-agentlib:jdwp=transport=dt_socket,address=<address>,server=y,suspend=n"`

        Where *address* is the debugger port, such as *5005* for up until Java SE 8 and *\*:5005* for Java SE 9 and later.

    -   For Linux, Mac OS X, or other Unix based OS:

        Add the following text in the end of your `/<SDK installation folder>/server/bin/setenv.sh`:

        `CATALINA_OPTS="-agentlib:jdwp=transport=dt_socket,address=<address>,server=y,suspend=n"`

        Where *address* is the debugger port, such as *5005* for up until Java SE 8 and *\*:5005* for Java SE 9 and later.


3.  3. Launch a remote debug session from within your IDE of choice by choosing *localhost* for host and the *address* you have provided previously for port.


**Related Information**  


[Debug Applications on the Cloud](debug-applications-on-the-cloud-10b63fe.md "In this section, you can learn how to debug a Web application on SAP BTP.")

