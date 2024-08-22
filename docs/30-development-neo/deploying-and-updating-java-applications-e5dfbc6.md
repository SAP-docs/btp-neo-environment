<!-- loioe5dfbc6cbb5710149279f67fb43d4e5d -->

# Deploying and Updating Java Applications

The Java application lifecycle management \(Java ALM\) service for SAP BTP lets you deploy and update Java applications via console client commands, the SAP BTP cockpit, or the Java ALM REST API.

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of the following technology portfolios: application development; process automation; integration; data, analytics, and enterprise planning; artificial intelligence. The platform offers users the ability to turn data into business value, compose end-to-end business processes, connect entire IT landscapes, and personalize, build and extend SAP applications. This reduces the overall total cost of ownership maintaining SAP landscapes and third-party software across end-to-end business processes.") :arrow_upper_right:.**


<table>
<tr>
<th valign="top">

Content

</th>
</tr>
<tr>
<td valign="top">

[Features](deploying-and-updating-java-applications-e5dfbc6.md#loioe5dfbc6cbb5710149279f67fb43d4e5d__features)

[Deploying Applications](deploying-and-updating-java-applications-e5dfbc6.md#loioe5dfbc6cbb5710149279f67fb43d4e5d__deploying)

[Updating Application Properties](deploying-and-updating-java-applications-e5dfbc6.md#loioe5dfbc6cbb5710149279f67fb43d4e5d__update_properties)

[Updating During Development](deploying-and-updating-java-applications-e5dfbc6.md#loioe5dfbc6cbb5710149279f67fb43d4e5d__update_during_dev)

[Updating Productive Applications](deploying-and-updating-java-applications-e5dfbc6.md#loioe5dfbc6cbb5710149279f67fb43d4e5d__update_prod_apps)

</td>
</tr>
</table>



<a name="loioe5dfbc6cbb5710149279f67fb43d4e5d__features"/>

## Features

The Java ALM service provides you with the following main features:

-   Deploy and undeploy Java applications

-   Start and stop Java applications

-   Obtain the status of a Java application


In addition, there are also a number of complementary features:

-   Perform rolling update

    You can update a Java application without downtime in one go.

-   Perform hot update

    You can redeploy and update the binaries of a Java application started on one process faster than the normal deploy and restart. Use this command to apply and activate your changes during development and not for updating productive applications.

-   Deploy a Java application with a copy operation

    You can deploy a Java application by copying an already existing and deployed Java application. This feature allows you to deploy quickly the application multiple times in separate locations.

-   Enable and disable Java application processes

    You can enable new connection requests to a disabled Java application or Java application process.

    You can stop the creation of new connections to a Java application or Java application process, but keep the already running sessions alive.

-   Enable maintenance mode for Java applications

    You can start the planned downtime of a Java application. During the maintenance mode, the application no longer receives requests and a custom maintenance page for that application is shown to the user.

    During the maintenance period, you can also gain temporary access to your Java application for testing and administration purposes.

    See [Enable Maintenance Mode for Planned Downtimes](../50-administration-and-ops-neo/enable-maintenance-mode-for-planned-downtimes-aa04f29.md).




<a name="loioe5dfbc6cbb5710149279f67fb43d4e5d__deploying"/>

## Deploying Applications

After you have created your Java application, you need to deploy and run it on SAP BTP. We recommend that you first deploy and test your application on the local runtime before deploying it on the cloud. Use the tool that best fits your scenario:


<table>
<tr>
<td valign="top">

Console Client

</td>
<td valign="top">

[Deploy Locally with the Console Client](deploy-locally-with-the-console-client-937c833.md)

[Deploy on the Cloud with the Console Client](deploy-on-the-cloud-with-the-console-client-030863c.md)

</td>
<td valign="top">

You want to deploy an application in the form of one or more WAR files.

Command: `deploy`

</td>
</tr>
<tr>
<td valign="top">

Cockpit

</td>
<td valign="top">

[Deploy on the Cloud with the Cockpit](deploy-on-the-cloud-with-the-cockpit-abded96.md)

</td>
<td valign="top">

You want to deploy an application in the form of a WAR file.

</td>
</tr>
<tr>
<td valign="top">

Java ALM REST API

</td>
<td valign="top">

[Deploy an Application](java-alm-api-fc944d1.md#loio83729f7df7074de3a795d61ae8844c0e) 

</td>
<td valign="top">

You want to deploy an application in the form of one or more WAR files.

</td>
</tr>
</table>



<a name="loioe5dfbc6cbb5710149279f67fb43d4e5d__update_properties"/>

## Updating Application Properties

Application properties are configured during deployment with a set of parameters. To update these properties, use one of the following approaches:


<table>
<tr>
<td valign="top">

Console Client

</td>
<td valign="top">

[deploy](../50-administration-and-ops-neo/deploy-937db4f.md) 

</td>
<td valign="top">

Deploy the application with new WAR file\(s\) and make changes to the configuration parameters.

Command: `deploy`

</td>
</tr>
<tr>
<td valign="top">

Console Client

</td>
<td valign="top">

[set-application-property](../50-administration-and-ops-neo/set-application-property-113e957.md) 

</td>
<td valign="top">

Change some of the application properties you defined during deployment without redeploying the application binaries.

Command: `set-application-property` 

</td>
</tr>
<tr>
<td valign="top">

Cockpit

</td>
<td valign="top">

[Deploy on the Cloud with the Cockpit](deploy-on-the-cloud-with-the-cockpit-abded96.md)

</td>
<td valign="top">

Update the application with a new WAR file or make changes to the configuration parameters.

</td>
</tr>
</table>



<a name="loioe5dfbc6cbb5710149279f67fb43d4e5d__update_during_dev"/>

## Updating During Development

If you want to quickly see your changes while developing an application, use the following approaches:


<table>
<tr>
<td valign="top">

Console Client

</td>
<td valign="top">

[hot-update](../50-administration-and-ops-neo/hot-update-7ae6493.md)

</td>
<td valign="top">

Apply and activate changes. Use the command to speed up development and not for updating productive applications.

Command: `hot-update` 

</td>
</tr>
<tr>
<td valign="top">

Console Client

</td>
<td valign="top">

[Use Delta Deployment](use-delta-deployment-7a4aba2.md)

[deploy](../50-administration-and-ops-neo/deploy-937db4f.md)

[hot-update](../50-administration-and-ops-neo/hot-update-7ae6493.md)

</td>
<td valign="top">

Apply changes in a deployed application without uploading the entire set of files.

Command: `deploy` or `hot-update`

Parameter: `--delta` 

</td>
</tr>
</table>



<a name="loioe5dfbc6cbb5710149279f67fb43d4e5d__update_prod_apps"/>

## Updating Productive Applications

If you are an application operator and need to deploy a new version of a productive application or perform maintenance, you can choose among several approaches:


<table>
<tr>
<td valign="top">

Zero Downtime

</td>
<td valign="top">

[Update Applications with Zero Downtime](../50-administration-and-ops-neo/update-applications-with-zero-downtime-a10f6c2.md)

[rolling-update](../50-administration-and-ops-neo/rolling-update-3f5d412.md)

</td>
<td valign="top">

Use when the new application version is backward compatible with the old version. Deploy a new version of the application and disable and enable processes in a rolling manner, or, do it at one go with the `rolling-update` command.

</td>
</tr>
<tr>
<td valign="top">

Planned Downtime

\(Maintenance Mode\)

</td>
<td valign="top">

[Enable Maintenance Mode for Planned Downtimes](../50-administration-and-ops-neo/enable-maintenance-mode-for-planned-downtimes-aa04f29.md) 

</td>
<td valign="top">

Use when the new application version is backward incompatible. Enable maintenance mode for the time of the planned downtime.

</td>
</tr>
<tr>
<td valign="top">

Soft Shutdown

</td>
<td valign="top">

[Perform Soft Shutdown](../50-administration-and-ops-neo/perform-soft-shutdown-17e8e96.md) 

</td>
<td valign="top">

Supports zero downtime and planned downtime scenarios. Disable the application or individual processes in order to shut down the application or processes gracefully.

</td>
</tr>
</table>

**Related Information**  


[Prerequisites and Restrictions](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/e6ddaefcbb571014b70fa01fc6a3f818.html "Find a list of the product prerequisites and restrictions for SAP BTP.") :arrow_upper_right:

[Java: Application Operations](../50-administration-and-ops-neo/java-application-operations-76f6dcf.md "")

