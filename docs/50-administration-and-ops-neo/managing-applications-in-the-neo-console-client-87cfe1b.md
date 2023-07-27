<!-- loio87cfe1b6ed6d478098c1e8170e8302c1 -->

# Managing Applications in the Neo Console Client

If you are an application operator and need to deploy a new version of a productive application or perform maintenance, you can choose among several approaches.

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://launchpad.support.sap.com/#/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**



> ### Note:  
> In all cases, first test your update in a non-productive environment. The newly deployed version of the application overwrites the old one and you cannot revert to it automatically. You have to redeploy the old version to revert the changes, if necessary.

SAP BTP provides the following approaches for updating an application:



## Zero Downtime

**Description**: Rolling update with soft shutdown

**Use**: When your new application version is backward compatible with the old version - that is, the new version of the application can work in parallel with the already running old application version.

**Steps**: Deploy a new version of the application and disable and enable processes in a rolling manner. For an automated execution of the same procedure, use the rolling-update command.

See [Update Applications with Zero Downtime](update-applications-with-zero-downtime-a10f6c2.md) and [rolling-update](rolling-update-3f5d412.md).



## Planned Downtime \(Maintenance Mode\)

**Description**: Shows a custom maintenance page to end users. The application is automatically disabled.

**Use**: When the new version is backward incompatible - that is, running the old and the new version in parallel may lead to inconsistent data or erroneous output.

**Steps**: Enable maintenance mode to redirect new connections to the maintenance application. Deploy and start the new application version and then disable maintenance mode.

See [Enable Maintenance Mode for Planned Downtimes](enable-maintenance-mode-for-planned-downtimes-aa04f29.md).



## Soft Shutdown

**Description**: Supports zero downtime and planned downtime scenarios. Disabled applications/processes stop accepting new connections from users, but continue to serve already running connections.

**Use**: As part of the zero downtime scenario or to gracefully shut down your application during a planned downtime \(without maintenance mode\).

**Steps**: Disable the application \(console client only\) or individual processes \(console client or cockpit\) in order to shut down the application or processes gracefully.

See [Perform Soft Shutdown](perform-soft-shutdown-17e8e96.md).

**Related Information**  


[Deploying and Updating Java Applications](../30-development-neo/deploying-and-updating-java-applications-e5dfbc6.md "The Java application lifecycle management (Java ALM) service for SAP BTP lets you deploy and update Java applications via console client commands, the SAP BTP cockpit, or the Java ALM REST API.")

