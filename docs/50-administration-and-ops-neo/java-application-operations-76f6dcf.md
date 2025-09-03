<!-- loio76f6dcfab9ec481dae0843873271d66c -->

# Java: Application Operations

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/docs/btp/sap-business-technology-platform/sap-business-technology-platform?version=Cloud) .**

After you have developed and deployed your Java application on SAP BTP, you can configure and operate it using the cockpit, the console client, or the Eclipse IDE.



<a name="loio76f6dcfab9ec481dae0843873271d66c__configure_applications"/>

## Configuring Applications


<table>
<tr>
<td valign="top">

Cockpit

</td>
<td valign="top">

[View Subaccount Usage Analytics](view-subaccount-usage-analytics-8f4d9db.md)

[View Runtime Information](view-runtime-information-343663e.md)

</td>
<td valign="top">



</td>
</tr>
<tr>
<td valign="top">

Console Client

</td>
<td valign="top">

[Update Application Properties](update-application-properties-cadb1dd.md)

[Choose Application Runtime Version](choose-application-runtime-version-13afe5c.md)

[Choose JRE Version](choose-jre-version-ee71c1a.md)

[Enable and Configure Gzip Response Compression](enable-and-configure-gzip-response-compression-390594a.md)

[Configure VM Arguments](configure-vm-arguments-b82d392.md)

[Scale Applications](scale-applications-745781b.md)

</td>
<td valign="top">

Specify various configurations using commands.

</td>
</tr>
</table>



<a name="loio76f6dcfab9ec481dae0843873271d66c__manage_applications"/>

## Managing the Lifecycle of Deployed Applications

> ### Recommendation:  
> We recommend that you:
> 
> -   Update your Java applications according to the instructions in [Update Applications with Zero Downtime](update-applications-with-zero-downtime-a10f6c2.md).
> 
> -   Restart your Java applications according to the instructions in [Restart Applications with Zero Downtime](restart-applications-with-zero-downtime-deadcc4.md).
> 
>     If you are not able to start an application process, please do not try to stop any of the currently running processes. First, please make sure that you can start a new application process before stopping any of the running processes.
> 
> 
> Here are the benefits of updating a Java application with the `rolling-update` command and restarting a Java application by handling each of its processes separately:
> 
> -   They both allow your application to remain operable all the time.
> 
> -   They both protect you against unexpected issues with the application or the platform.


<table>
<tr>
<td valign="top">

Cockpit

</td>
<td valign="top">

[Define Application Details \(Java Apps\)](define-application-details-java-apps-9b23270.md)

[Start and Stop Applications](start-and-stop-applications-7612f03.md)

[Check the Process Status](check-the-process-status-499992d.md)

[View Subaccount Usage Analytics](view-subaccount-usage-analytics-8f4d9db.md)

</td>
<td valign="top">

Start, stop, and undeploy applications, as well as start, stop, and disable individual application processes.

</td>
</tr>
<tr>
<td valign="top">

Console Client

</td>
<td valign="top">

[start](start-cc417d7.md); [stop](stop-b5bfcbf.md); [restart](restart-7c0f7a1.md)

[enable](enable-13a70e0.md); [disable](disable-59fedc1.md); [undeploy](undeploy-7e09b85.md)

</td>
<td valign="top">

Manage the lifecycle of a deployed application or individual application processes by executing the respective command.

</td>
</tr>
<tr>
<td valign="top">

Lifecycle Management API

</td>
<td valign="top">

[Start an Application](../30-development-neo/java-alm-api-fc944d1.md#loio2d3be560df574092909ed8171ec197ec)

[Stop an Application](../30-development-neo/java-alm-api-fc944d1.md#loio38829d2c139c47b3a1c1d64e6ce6d4f8)

</td>
<td valign="top">

Start and stop applications using the Lifecycle Management API.

</td>
</tr>
</table>



<a name="loio76f6dcfab9ec481dae0843873271d66c__monitoring"/>

## Monitoring


<table>
<tr>
<td valign="top">

Cockpit, Console Client, Monitoring API

</td>
<td valign="top">

[Monitoring Java Applications](https://help.sap.com/viewer/64f7d2b06c6b40a9b3097860c5930641/Cloud/en-US/cf4b2953c2534c0a9b491abf5a4847d7.html "") :arrow_upper_right:

[Monitoring HTML5 Applications](https://help.sap.com/viewer/64f7d2b06c6b40a9b3097860c5930641/Cloud/en-US/e05f98a541ba4464bc963d06dd8a91fc.html "To monitor your HTML5 application, create custom checks for it by specifying your own metrics. Furthermore, configure alert notifications for any changes to the states of the configured checks.") :arrow_upper_right:

[Monitoring Database Systems](https://help.sap.com/viewer/64f7d2b06c6b40a9b3097860c5930641/Cloud/en-US/d5c5c6a37c944ce78fcccf2b84243d8a.html "You can monitor your database system by viewing its metrics in the SAP BTP cockpit, by retrieving them with the Metrics REST API, or by receiving alerts for them. Furthermore, when you use an SAP HANA database system, you can also configure monitoring for its SAP HANA XS applications.") :arrow_upper_right:

</td>
<td valign="top">

View the current metrics or the metrics history.

Configure checks for an application.

Use the Metrics REST API to get the state or the metric details of an application.

</td>
</tr>
</table>



<a name="loio76f6dcfab9ec481dae0843873271d66c__profiling"/>

## Profiling


<table>
<tr>
<td valign="top">

Eclipse IDE

</td>
<td valign="top">

[Profiling Applications](profiling-applications-8967d19.md) 

</td>
<td valign="top">

Analyze resource-related problems in your application.

</td>
</tr>
</table>



<a name="loio76f6dcfab9ec481dae0843873271d66c__logging"/>

## Logging


<table>
<tr>
<td valign="top">

Cockpit

</td>
<td valign="top">

[Using Logs in the Cockpit for Java Applications](https://help.sap.com/viewer/f88a032109f0429caea276fc6e3a95f9/Cloud/en-US/2555df65182c4b09a25e56fa3b57b0a8.html "You can view the logs and change the log settings of any Java application deployed in your subaccount. The cockpit provides the following types of logs for a Java application: default traces, HTTP access logs, garbage collection logs, and Java Connector (JCo) logs.") :arrow_upper_right: 

</td>
<td valign="top">

View the logs and change the log settings of any applications deployed in your subaccount.

</td>
</tr>
<tr>
<td valign="top">

Console Client

</td>
<td valign="top">

[Using Logs in the Console Client](https://help.sap.com/viewer/f88a032109f0429caea276fc6e3a95f9/Cloud/en-US/e4fd83c5bb5710149b1e94f127f108e4.html "") :arrow_upper_right: 

</td>
<td valign="top">

Manage some of the logging configurations of a started application.

</td>
</tr>
</table>



<a name="loio76f6dcfab9ec481dae0843873271d66c__update_applications"/>

## Updating Productive Applications


<table>
<tr>
<td valign="top">

Cockpit

</td>
<td valign="top">

[Enable Maintenance Mode for Planned Downtimes](enable-maintenance-mode-for-planned-downtimes-aa04f29.md)

[Perform Soft Shutdown](perform-soft-shutdown-17e8e96.md)

</td>
<td valign="top">

Supports zero downtime and planned downtime scenarios. Disable the application or individual processes in order to shut down the application or processes gracefully.

</td>
</tr>
<tr>
<td valign="top">

Console Client

</td>
<td valign="top">

[Update Applications with Zero Downtime](update-applications-with-zero-downtime-a10f6c2.md)

[Enable Maintenance Mode for Planned Downtimes](enable-maintenance-mode-for-planned-downtimes-aa04f29.md)

[Perform Soft Shutdown](perform-soft-shutdown-17e8e96.md)

</td>
<td valign="top">

Deploy a new version of a productive application or perform maintenance.

</td>
</tr>
</table>

**Related Information**  


[Deploying and Updating Java Applications](../30-development-neo/deploying-and-updating-java-applications-e5dfbc6.md "The Java application lifecycle management (Java ALM) service for SAP BTP lets you deploy and update Java applications via console client commands, the SAP BTP cockpit, or the Java ALM REST API.")

