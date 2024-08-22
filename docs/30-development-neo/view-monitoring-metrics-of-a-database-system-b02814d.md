<!-- loiob02814df3acf42d3b41c18c99ad35c27 -->

# View Monitoring Metrics of a Database System

In the cockpit, you can view the current metrics of a selected database system to get information about its health state. You can also view the metrics history of a productive database to examine the performance trends of your database over different intervals of time or investigate the reasons that have led to problems with it. You can view the metrics for all types of databases.



<a name="loiob02814df3acf42d3b41c18c99ad35c27__prereq_ff4_hnt_jdb"/>

## Prerequisites

The *readMonitoringData* scope is assigned to the used platform role for the subaccount. For more information, see [Platform Scopes](../50-administration-and-ops-neo/platform-scopes-f226074.md).



## Context

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of the following technology portfolios: application development; process automation; integration; data, analytics, and enterprise planning; artificial intelligence. The platform offers users the ability to turn data into business value, compose end-to-end business processes, connect entire IT landscapes, and personalize, build and extend SAP applications. This reduces the overall total cost of ownership maintaining SAP landscapes and third-party software across end-to-end business processes.") :arrow_upper_right:.**

> ### Note:  
> You can also retrieve the current metrics of a database system with the Metrics API.

**Default Metrics of a Database System**


<table>
<tr>
<th valign="top">

Metric

</th>
<th valign="top">

Value

</th>
<th valign="top">

Execution Frequency

</th>
</tr>
<tr>
<td valign="top">

CPU Load

</td>
<td valign="top">

The percentage of the CPU that is used on average over the last minute.

</td>
<td valign="top">

This metric is updated every minute.

An alert is triggered when 2 consecutive checks with an interval of 1 minute aren’t in an OK state.

</td>
</tr>
<tr>
<td valign="top">

Disk I/O

</td>
<td valign="top">

The number of bytes per second that are currently being read or written to the disc. from the navigation area or from the

</td>
<td valign="top">

This metric is updated every minute.

An alert is triggered when 5 consecutive checks with an interval of 1 minute aren’t in an OK state.

</td>
</tr>
<tr>
<td valign="top">

Network Ping

</td>
<td valign="top">

The percentage of packets that are lost to the database host.

</td>
<td valign="top">

This metric is updated every minute.

An alert is triggered when 2 consecutive checks with an interval of 1 minute aren’t in an OK state.

</td>
</tr>
<tr>
<td valign="top">

OS Memory Usage

</td>
<td valign="top">

from the navigation area or from theThe percentage of the operating system memory that is currently being used.

</td>
<td valign="top">

This metric is updated every minute.

An alert is triggered when 2 consecutive checks with an interval of 1 minute aren’t in an OK state.

</td>
</tr>
<tr>
<td valign="top">

Used Disc Space

</td>
<td valign="top">

The percentage of the local discs of the operating system that is currently being used.

> ### Note:  
> If this metric is in a critical state, try restarting the database system. If the restart doesn’t work, check the troubleshooting documentation. See the *Related Information* section.



</td>
<td valign="top">

This metric is updated every minute.

An alert is triggered when 5 consecutive checks with an interval of 1 minute aren’t in an OK state.

</td>
</tr>
</table>

**Default Metrics of an SAP HANA System**


<table>
<tr>
<th valign="top">

Metric

</th>
<th valign="top">

Value

</th>
<th valign="top">

Execution Frequency

</th>
</tr>
<tr>
<td valign="top">

HANA DB Availability

</td>
<td valign="top">

-   *OK* - the database is reachable from our central admin component via JDBC.

-   *Critical* - either the database is down or overloaded, or there's a network issue.




</td>
<td valign="top">

This metric is updated every minute.

An alert is triggered when 3 consecutive checks with an interval of 1 minute aren’t in an OK state.

</td>
</tr>
<tr>
<td valign="top">

HANA DB Alerting Availability

</td>
<td valign="top">

-   *OK* - alerts can be retrieved from the SAP HANA system.

-   *Critical* - alerts can’t be retrieved as there’s no connection to the database. This also implies that any other visible metric may be outdated.


This metric depends on the HANA DB Availability metric.

</td>
<td valign="top">

This metric is updated every minute.

An alert is triggered when 3 consecutive checks with an interval of 1 minute aren’t in an OK state.

</td>
</tr>
<tr>
<td valign="top">

HANA DB Compile Server

</td>
<td valign="top">

-   *OK* - the compiler server is running on the SAP HANA system.

-   *Critical* - the compile server crashed or was otherwise stopped. The service should recover automatically. If this doesn’t work, a restart of the system might be necessary.




</td>
<td valign="top">

This metric is updated every 10 minutes.

An alert is triggered when 3 consecutive checks with an interval of 1 minute aren’t in an OK state.

</td>
</tr>
<tr>
<td valign="top">

HANA DB Backup Volumes Availability

</td>
<td valign="top">

-   *OK* - the backup volumes are available.

-   *Critical* - the backup volumes aren’t available.




</td>
<td valign="top">

This metric is updated every 15 minutes.

An alert is triggered when 3 consecutive checks with an interval of 1 minute aren’t in an OK state.

</td>
</tr>
<tr>
<td valign="top">

HANA DB Data Backup Age

</td>
<td valign="top">

-   *OK* - the age of the last data backup is below the critical threshold.

-   *Critical* - the age of the last data backup is above the critical threshold.




</td>
<td valign="top">

This metric is updated every 24 hours.

An alert is triggered when 3 consecutive checks with an interval of 1 minute aren’t in an OK state.

</td>
</tr>
<tr>
<td valign="top">

HANA DB Data Backup Exists

</td>
<td valign="top">

-   *OK* - the data backup exists.

-   *Critical* - no data backup exists.




</td>
<td valign="top">

This metric is updated every 24 hours.

An alert is triggered when 3 consecutive checks with an interval of 1 minute aren’t in an OK state.

</td>
</tr>
<tr>
<td valign="top">

HANA DB Data Backup Successful

</td>
<td valign="top">

-   *OK* - the last data backup was successful.

-   *Critical* - the last data backup wasn’t successful.




</td>
<td valign="top">

This metric is updated every 24 hours.

An alert is triggered when 3 consecutive checks with an interval of 1 minute aren’t in an OK state.

</td>
</tr>
<tr>
<td valign="top">

HANA DB Log Backup Successful

</td>
<td valign="top">

-   *OK* - the last log backup was successful.

-   *Critical* - the last log backup failed.




</td>
<td valign="top">

This metric is updated every 10 minutes.

An alert is triggered when 3 consecutive checks with an interval of 1 minute aren’t in an OK state.

</td>
</tr>
<tr>
<td valign="top">

HANA DB Service Memory Usage

</td>
<td valign="top">

-   *OK* - no server is running out of memory.

-   *Critical* - a service is causing an out of memory error. See SAP Note [1900257](https://me.sap.com/notes/1900257).




</td>
<td valign="top">

This metric is updated every 5 minutes.

An alert is triggered when 3 consecutive checks with an interval of 1 minute aren’t in an OK state.

</td>
</tr>
<tr>
<td valign="top">

HANA XS Availability

</td>
<td valign="top">

-   *OK* - XSEngine accepts HTTPS connections.

-   *Critical* - XSEngine doesn’t accept HTTPS connections.




</td>
<td valign="top">

This metric is updated every minute.

An alert is triggered when 3 consecutive checks with an interval of 1 minute aren’t in an OK state.

</td>
</tr>
<tr>
<td valign="top">

HANA Dump Files Count

</td>
<td valign="top">

-   *OK* - Up to 10 dump files exist.

-   *Warning* - More than 10 dump files exist.

-   *Critical* - More than 20 dump files exist. Try to analyze the dump files.


> ### Note:  
> If you’re still having issues, check the troubleshooting documentation. See the *Related Information* section.



</td>
<td valign="top">

The metric is updated every hour.

An alert is triggered when a check isn't in an OK state.

</td>
</tr>
<tr>
<td valign="top">

HANA Tenant Databases Unused Memory

</td>
<td valign="top">

-   *OK* - More than 10% of the total free memory is available to the tenant databases, including fragmented memory. Nameserver reservation is excluded.

-   *Warning* - 10% or less of the total free memory can be used by the tenant databases.
-   *Critical* - 2% or less of the total free memory can be used by the tenant databases.



</td>
<td valign="top">

The metric is updated every hour.

</td>
</tr>
</table>

**Default Metrics of an SAP ASE System**


<table>
<tr>
<th valign="top">

Metric

</th>
<th valign="top">

Value

</th>
<th valign="top">

Execution Frequency

</th>
</tr>
<tr>
<td valign="top">

Sybase ASE Availability

</td>
<td valign="top">

-   *OK* - the database is reachable from our central admin component via JDBC.

-   *Critical* - either the database is down or overloaded, or there's a network issue.




</td>
<td valign="top">

This metric is updated every minute.

An alert is triggered when 3 consecutive checks with an interval of 1 minute aren’t in an OK state.

</td>
</tr>
<tr>
<td valign="top">

Sybase ASE Long Running Trans

</td>
<td valign="top">

-   *OK* - a transaction is running for up to an hour.

-   *Warning* - a transaction is running for more than an hour.

-   *Critical* - a transaction is running for more than 13 hours.




</td>
<td valign="top">

This metric is updated every 2 minutes.

An alert is triggered when a consecutive check with an interval of 1 minute isn’t in an OK state.

</td>
</tr>
<tr>
<td valign="top">

Sybase ASE HADR Fm State

</td>
<td valign="top">

FaultManager is a component for highly available \(HA\) SAP ASE systems that triggers a failover in case the primary node isn’t working.

-   *OK* - FaultManager for a system that is set up as an HA system is running properly.

-   *Critical* - FaultManager isn’t working properly and the failover doesn’t work.




</td>
<td valign="top">

This metric is updated every 2 minutes.

An alert is triggered when a consecutive check with an interval of 1 minute isn’t in an OK state.

</td>
</tr>
<tr>
<td valign="top">

Sybase ASE HADR Latency

</td>
<td valign="top">

-   *OK* - the latency for the HA replication path is less than or equal to 10 minutes.

-   *Warning* - the latency is greater than 10 minutes.

-   *Critical* - the latency is greater than 20 minutes. A high latency might lead to data loss if there’s a failover.




</td>
<td valign="top">

This metric is updated every 2 minutes.

An alert is triggered when a consecutive check with an interval of 1 minute isn’t in an OK state.

</td>
</tr>
<tr>
<td valign="top">

Sybase ASE HADR Primary State

</td>
<td valign="top">

-   *OK* - the primary host of a system that is set up as HA system is running fine.

-   *Critical* - the primary host isn’t running properly.




</td>
<td valign="top">

This metric is updated every 2 minutes.

An alert is triggered when a consecutive check with an interval of 1 minute isn’t in an OK state.

</td>
</tr>
<tr>
<td valign="top">

Sybase ASE HADR Standby State

</td>
<td valign="top">

-   *OK* - the secondary or standby host of a system that is set up as HA system is running properly.

-   *Critical* - the secondary or standby host isn’t running properly.




</td>
<td valign="top">

This metric is updated every 2 minutes.

An alert is triggered when a consecutive check with an interval of 1 minute isn’t in an OK state.

</td>
</tr>
<tr>
<td valign="top">

Sybase ASE Procedure Cache Usage

</td>
<td valign="top">

-   *OK* - procedure cache usage is below 80%.

-   *Warning* - procedure cache usage is more than 80% but less than 89%.
-   *Critical* - procedure cache usage is more than 90%.



</td>
<td valign="top">

This metric is updated every 2 minutes. An alert is is triggered when a consecutive check with an interval of 1 minute isn't in an OK state.

</td>
</tr>
</table>



## Procedure

1.  Open the subaccount in the SAP BTP cockpit.

2.  Navigate to the *Database Systems* page either by choosing *SAP HANA / SAP ASE* \> *Database Systems**Overview* page.

    All database systems available in the selected subaccount are listed with their details, including the database version and state, and the number of associated databases.

3.  Choose the entry for the relevant database system in the list.

4.  Choose *Monitoring* from the navigation area to get detailed information about the current state and the history of metrics for the selected database system.

    When you open the checks history, you can view graphic representations for each of the different checks, and zoom in to see additional details. If you zoom in a graphic horizontally, all other graphics also zoom in to the same level of detail. Press [Shift\] and drag to pan a graphic. Zoom out to the initial size by double-clicking.

    You can select different periods for each check. Depending on the interval you select, data is aggregated as follows:

    -   Last 12 or 24 hours - data is collected every minute.
    -   Last 7 days - data is aggregated from the average values for each 10 minutes.
    -   Last 30 days - data is aggregated from the average values for each hour.

    You can also select a custom time interval for viewing check history.


**Related Information**  


[SAP BTP Cockpit](https://help.sap.com/viewer/ea72206b834e4ace9cd834feed6c0e09/Cloud/en-US/19d7119265474dd18ec16fad2a0b28c1.html)

[Metrics REST API for Database Systems](https://help.sap.com/viewer/64f7d2b06c6b40a9b3097860c5930641/Cloud/en-US/9f883c61f23b432f89bb108644e819ad.html "Use the REST API to get metrics for your database systems that are running in the Neo environment.") :arrow_upper_right:

