<!-- loio76143786711e1014839a8273b0e91070 -->

# Update the SAP BTP SDK for Neo Environment

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**

> ### Note:  
> The Java tools for Eclipse used in this page are no longer available. We are in the process of updating the content accordingly.



<a name="loio76143786711e1014839a8273b0e91070__section_99A0605EE5EA428BA9426BFFE0BBED42"/>

## Context

If you have already installed an SAP BTP SDK for Neo environment package, you only need to update it regularly. To update your SDK, follow the steps below.



<a name="loio76143786711e1014839a8273b0e91070__section_60CF91400ADD4107B680D1FF955D9489"/>

## Procedure

1.  Download the new SAP BTP SDK for Neo environment version from [https://tools.hana.ondemand.com/\#cloud](https://tools.hana.ondemand.com/#cloud)
2.  Unzip the SDK to a new directory on your local file system. Do not install the new SDK version to a directory that already contains SDK.
3.  Go to the *Servers* tab view.
4.  Stop and delete all local servers.
5.  Choose *Window* \> *Preferences* \> *Server* \> *Runtime Environment*.

    For each previously added local runtime:

    1.  Select the corresponding entry in the table.
    2.  Choose the *Edit* button.
    3.  Locate the new SDK version:

        -   For `Java Web`: Select option *Use Java Web SDK from the following location* and then choose the *Browse* button and find the folder where you have unpacked the SDK ZIP file.
        -   For `Java Web Tomcat 7`: Choose the *Browse* button and find the folder where you have unpacked the SDK ZIP file or use the *Download and Install* button to get the latest version.
        -   For `Java Web Tomcat 8`: Choose the *Browse* button and find the folder where you have unpacked the SDK ZIP file or use the *Download and Install* button to get the latest version.
        -   For `Java EE 6 Web Profile`: Select option *Use Java EE 6 Web Profile SDK from the following location* and then choose the *Browse* button and find the folder where you have unpacked the SDK ZIP file.

        > ### Note:  
        > Again, if the SAP BTP SDK for Neo environment version is higher and not supported by the version of your SAP BTP Tools for Java, a message appears prompting you to update your SAP BTP Tools for Java. You can check for updates \(recommended\) or ignore the message.

    4.  Choose *Finish*.

6.  After editing all local runtimes, choose *OK*.

**Related Information**  


[Install the SAP BTP SDK for Neo Environment](install-the-sap-btp-sdk-for-neo-environment-7613843.md)

[Application Runtime Container](application-runtime-container-7613bd2.md)

[sdk-upgrade](../50-administration-and-ops-neo/sdk-upgrade-44dc673.md "")

