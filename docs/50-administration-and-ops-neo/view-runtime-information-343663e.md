<!-- loio343663e8f3e34573ac292106861a8590 -->

# View Runtime Information

View information about the application runtime. SAP BTP provides a set of runtimes. You can choose the application runtime during application deployment.



## Context

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**

The runtime is assigned either by default or explicitly set when an application is deployed. If a version is not specified during deployment, the major runtime version is determined automatically based on the SDK that is used to deploy the application. By default, applications are deployed with the latest minor version of the respective major version.

You are strongly advised to use the default version, since this contains all released fixes and critical patches, including security patches. Override this behavior only in exceptional cases by explicitly setting the version, but note that this is not recommended practice.



## Procedure

1.  In the cockpit, choose *Java Applications* in the navigation area and then select the relevant application in the list.

    The *Runtime* panel provides the following information:

    -   The application runtime name and version
    -   For user-defined runtimes:
        -   The major and minor versions, for example, 1.35.
        -   The date until when the specified runtime version is recommended for use, or whether it is no longer recommended or has expired \(also indicated by a runtime version status icon\).


2.  To view the actual runtime versions used by the individual processes \(requires that the application is running\), click the relevant application's name in the list to go the application overview page.

3.  Choose *Monitoring* \> *Processes* in the navigation area and select a process.

    The *Runtime* section at process level provides the following information:

    -   The exact runtime version on which the process has been started \(major, minor, micro, and nano versions\).
    -   The date until when this runtime version is recommended for use, or whether it is no longer recommended or has expired \(also indicated by a runtime version status icon\).


**Related Information**  


[Application Runtime Container](../30-development-neo/application-runtime-container-7613bd2.md)

[Choose Application Runtime Version](choose-application-runtime-version-13afe5c.md "Applications deployed on SAP BTP are always started on the latest version of the application runtime container. This version contains all released fixes, critical patches and enhancements and is respectively the recommended option for applications. In some special cases, you can choose the version of the runtime container your application uses by specifying it with the parameter --runtime-version when deploying your application. To change this version, you need to redeploy the application without specifying this parameter.")

