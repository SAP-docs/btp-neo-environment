<!-- loiodb766190d976101498a8bf1a9cf5f277 -->

# Profile Applications Locally

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of the following technology portfolios: application development; process automation; integration; data, analytics, and enterprise planning; artificial intelligence. The platform offers users the ability to turn data into business value, compose end-to-end business processes, connect entire IT landscapes, and personalize, build and extend SAP applications. This reduces the overall total cost of ownership maintaining SAP landscapes and third-party software across end-to-end business processes.") :arrow_upper_right:.**



<a name="loiodb766190d976101498a8bf1a9cf5f277__section_6FFD362969644FAAA34D0C8A5303F82C"/>

## Overview

After you have created a Web application and verified that it is functionally correct, you may want to inspect its runtime behavior by profiling the application. This helps you to:

-   Check and optimize memory usage
-   Identify frequently called operations \(bottlenecks and hotspots\)
-   Identify slow performance

> ### Note:  
> You can use IDE of your choice for developing the application. If you want to use SAP JVM Profiler for profiling the application locally, you must use Eclipse IDE.



<a name="loiodb766190d976101498a8bf1a9cf5f277__section_10A9137E26384B649BFCEE47BB0B20AA"/>

## Prerequisites

-   You have developed and deployed a Web application locally. For more information, see [Deploy Locally with the Console Client](../30-development-neo/deploy-locally-with-the-console-client-937c833.md).
-   You have installed the SAP JVM Tools for Eclipse. For more information, see [Install the SAP JVM Tools in Eclipse](../30-development-neo/install-the-sap-jvm-tools-in-eclipse-4e97452.md).
-   You have installed SAP JVM. For more information, see [\(Optional\) Install SAP JVM](../30-development-neo/optional-install-sap-jvm-76137f4.md).



<a name="loiodb766190d976101498a8bf1a9cf5f277__section_01BE1106BEE04D29847A6C9CE032AB08"/>

## Procedure

1.  Run your Web application locally. See [Deploy Locally with the Console Client](../30-development-neo/deploy-locally-with-the-console-client-937c833.md).
2.  Go to Eclipse IDE and open the *Profiling* perspective.
3.  In the *Profile* tab, choose *VM Explorer*. It will list all SAP JVM virtual machines running locally.
4.  Double click the virtual machine of your local server.
5.  The *Profiling* perspective is opened.
6.  Choose the type of analysis you want to perform.



<a name="loiodb766190d976101498a8bf1a9cf5f277__section_ACCBDA9DE6AB412191CDCEA83F2060C2"/>

## Result

You have successfully started a profiling run of a locally deployed Web application. You can now trigger your work load, create snapshots of the profiling data and analyze the profiling results.



## Next Steps

When you have finished with your profiling session, you can stop it by disconnecting the profiling session from the *Profile* view.



<a name="loiodb766190d976101498a8bf1a9cf5f277__section_B531C3E4E0034FD0BA8F7808589073AC"/>

## Related Information

Refer to the SAP JVM Profiler documentation for details about the available analysis options. The documentation is available as part of the SAP JVM Profiler plugin in the Eclipse IDE and can be found via *Help* \> *Help Contents* \> *SAP JVM Profiler*.

