<!-- loiof2260746ed8e446fafdeaaa8ab43e307 -->

# Platform Scopes



> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**




<table>
<tr>
<th valign="top">

Category



</th>
<th valign="top">

ID



</th>
<th valign="top">

Scope Name



</th>
<th valign="top">

Description



</th>
</tr>
<tr>
<td valign="top" rowspan="8">

Account Management



</td>
<td valign="top">

readAccount



</td>
<td valign="top">

View Accounts



</td>
<td valign="top">

Enables you to view a list of all subaccounts available to you and access them.



</td>
</tr>
<tr>
<td valign="top">

manageAccount



</td>
<td valign="top">

Manage Accounts



</td>
<td valign="top">

Enables you to edit and delete subaccounts.



</td>
</tr>
<tr>
<td valign="top">

readQuota \(obsolete\)



</td>
<td valign="top">

View Quota



</td>
<td valign="top">

Enables you to view the purchased quotas in use and how they are distributed between individual subaccounts.



</td>
</tr>
<tr>
<td valign="top">

manageQuota \(obsolete\)

Only global account administrators can manage quota.



</td>
<td valign="top">

Manage Quota



</td>
<td valign="top">

Enables you to distribute free quota and reassign quota between individual subaccounts.



</td>
</tr>
<tr>
<td valign="top">

readCustomPlatformRoles



</td>
<td valign="top">

View Custom Platform Roles



</td>
<td valign="top">

Enables you to list self-defined platform roles.



</td>
</tr>
<tr>
<td valign="top">

manageCustomPlatformRoles



</td>
<td valign="top">

Manage Custom Platform Roles



</td>
<td valign="top">

Enables you to define your own platform roles.



</td>
</tr>
<tr>
<td valign="top">

manageAccountNotifications



</td>
<td valign="top">

Manage Account Notifications



</td>
<td valign="top">

Enables you to further process a notification, for example, you can assign it to yourself or set the status to complete.



</td>
</tr>
<tr>
<td valign="top">

readAccountNotifications



</td>
<td valign="top">

Read Account Notifications



</td>
<td valign="top">

Enables you to read notifications for a subaccount.



</td>
</tr>
<tr>
<td valign="top" rowspan="2">

Agent Activation for Dyntrace Service



</td>
<td valign="top">

readDynatraceIntegration



</td>
<td valign="top">

Manage Dynatrace Integration



</td>
<td valign="top">

Enables you to view the configuration settings of the Agent Activation for Dynatrace service in your subaccount.



</td>
</tr>
<tr>
<td valign="top">

manageDynatraceIntegration



</td>
<td valign="top">

Read Dynatrace Integration



</td>
<td valign="top">

Enables you to update and delete the configuration settings of the Agent Activation for Dynatrace service in your subaccount.



</td>
</tr>
<tr>
<td valign="top" rowspan="4">

Authorization Management



</td>
<td valign="top">

readApplicationRoles



</td>
<td valign="top">

View Application Roles



</td>
<td valign="top">

Enables you to list all user roles available for a Java application.



</td>
</tr>
<tr>
<td valign="top">

manageApplicationRoles



</td>
<td valign="top">

Manage Application Roles



</td>
<td valign="top">

Enables you to assign user roles for a Java application and create new roles.



</td>
</tr>
<tr>
<td valign="top">

readAuthorizationSettings



</td>
<td valign="top">

View Authorization Settings



</td>
<td valign="top">

Enables you to view all kinds of role, group, and user mappings on account and subscription level.

> ### Note:  
> Assigning this scope to a role requires to assign the readAccount and readSubscriptions scopes as well.



</td>
</tr>
<tr>
<td valign="top">

manageAuthorizationSettings



</td>
<td valign="top">

Manage Authorization Settings



</td>
<td valign="top">

Enables you to manage all kinds of role, group, and user mappings on account and subscription level.

> ### Note:  
> Assigning this scope to a role requires to assign the readAccount, readSubscriptions and readAuthorizationSettings scopes as well.



</td>
</tr>
<tr>
<td valign="top" rowspan="2">

Basic Authentication Management



</td>
<td valign="top">

manageBasicAuthentication



</td>
<td valign="top">

Manage Basic Authentication Settings



</td>
<td valign="top">

Enables you to manage the *Basic Authentication* configuration of a subaccount. It defines the Identity Authentication tenant to be used for validating the user names and passwords.



</td>
</tr>
<tr>
<td valign="top">

readBasicAuthentication



</td>
<td valign="top">

Read Basic Authentication Settings



</td>
<td valign="top">

Enables you to view the *Basic Authentication* configuration of a subaccount. It shows the Identity Authentication tenant to be used for validating the user names and passwords.



</td>
</tr>
<tr>
<td valign="top" rowspan="4">

Connectivity Service



</td>
<td valign="top">

readDestinations



</td>
<td valign="top">

View Destinations



</td>
<td valign="top">

Enables you to view destinations required for communication outside SAP BTP.



</td>
</tr>
<tr>
<td valign="top">

manageDestinations



</td>
<td valign="top">

Manage Destinations



</td>
<td valign="top">

Enables you to create, update, and delete destinations and their properties required for communication outside SAP BTP.



</td>
</tr>
<tr>
<td valign="top">

readSCCTunnels



</td>
<td valign="top">

View SCC Tunnels



</td>
<td valign="top">

Enables you to view the data transmission tunnels used by the Cloud connector to communicate with back-end systems.



</td>
</tr>
<tr>
<td valign="top">

manageSCCTunnels



</td>
<td valign="top">

Manage SCC Tunnels



</td>
<td valign="top">

Enables you to operate the data transmission tunnels used by the Cloud connector.



</td>
</tr>
<tr>
<td valign="top" rowspan="2">

Document Service



</td>
<td valign="top">

listECMRepositories



</td>
<td valign="top">

List Document Service Repositories



</td>
<td valign="top">

Enables you to list the document service repositories.



</td>
</tr>
<tr>
<td valign="top">

manageECM



</td>
<td valign="top">

Manage Document Service Repositories



</td>
<td valign="top">

Enables you to create and delete document service repositories, including the management of repository keys.



</td>
</tr>
<tr>
<td valign="top" rowspan="3">

Enterprise Messaging



</td>
<td valign="top">

readMessagingService



</td>
<td valign="top">

Read Messaging Service



</td>
<td valign="top">

Enables you to view details of messaging hosts, queues, and applications bindings to messaging hosts.



</td>
</tr>
<tr>
<td valign="top">

manageMessagingQueuesAndBindings



</td>
<td valign="top">

Manage Queues and Application Bindings



</td>
<td valign="top">

Enables you to:

-   Create, edit, and delete queues.
-   Clear all messages from a queue.
-   Create and delete application bindings.



</td>
</tr>
<tr>
<td valign="top">

manageMessagingHosts



</td>
<td valign="top">

Manage Messaging Hosts



</td>
<td valign="top">

Enables you to create, edit, and delete messaging hosts.



</td>
</tr>
<tr>
<td valign="top" rowspan="6">

Extension Integration Management



</td>
<td valign="top">

readExtensionIntegration



</td>
<td valign="top">

Read Extension Integration



</td>
<td valign="top">

Enables you to read integration tokens.



</td>
</tr>
<tr>
<td valign="top">

manageExtensionIntegration



</td>
<td valign="top">

Manage Extension Integration



</td>
<td valign="top">

Enables you to create and delete integration tokens.



</td>
</tr>
<tr>
<td valign="top">

manageApplicationRoleProvider



</td>
<td valign="top">

Manage Application Role Provider



</td>
<td valign="top">

Enables you to manage Java applications' role provider using the SAP BTP cockpit.



</td>
</tr>
<tr>
<td valign="top">

readApplicationRoleProvider



</td>
<td valign="top">

Read Application Role Provider



</td>
<td valign="top">

Enables you to read the Java applications' role provider configuration using the SAP BTP cockpit.



</td>
</tr>
<tr>
<td valign="top">

readExtensionConfiguration



</td>
<td valign="top">

Read Extension Configuration



</td>
<td valign="top">

Enables you to read the extension configuration.



</td>
</tr>
<tr>
<td valign="top">

manageExtensionConfiguration



</td>
<td valign="top">

Manage Extension Configuration



</td>
<td valign="top">

Enables you to manage the extension configuration.



</td>
</tr>
<tr>
<td valign="top" rowspan="3">

Git Service



</td>
<td valign="top">

accessGit



</td>
<td valign="top">

Access Git Repositories



</td>
<td valign="top">

Enables you to create repositories, push commit, push tags, create new remote branches, and push commits authored by other users \(forge author identity\).

> ### Note:  
> Assigning this scope to a role requires to assign the readHTML5Applications scope as well.



</td>
</tr>
<tr>
<td valign="top">

manageGit



</td>
<td valign="top">

Manage Git Repositories



</td>
<td valign="top">

Enables you to delete repositories, run garbage collection on repositories, lock and unlock repositories, delete remote branches, delete tags, push commits made by other users \(forge committer identity\), forcefully push commits, for example to rewrite the history of a Git repository, and forcefully push tags, for example to move the version of an HTML5 application to a different commit.

> ### Note:  
> Assigning this scope to a role requires to assign the readHTML5Applications scope as well.



</td>
</tr>
<tr>
<td valign="top">

readGit



</td>
<td valign="top">

Browse Git Repositories



</td>
<td valign="top">

Enables you to clone a repository as well as to fetch commits and tags.

> ### Note:  
> Assigning this scope to a role requires to assign the readHTML5Applications scope as well.



</td>
</tr>
<tr>
<td valign="top" rowspan="2">

HTML5 Application Management



</td>
<td valign="top">

readHTML5Applications



</td>
<td valign="top">

List HTML5 Applications



</td>
<td valign="top">

Enables you to list HTML applications and review their status.

> ### Note:  
> Assigning this scope to a role requires to assign the readAccount scope as well.



</td>
</tr>
<tr>
<td valign="top">

manageHTML5Applications



</td>
<td valign="top">

Manage HTML5 Applications



</td>
<td valign="top">

Enables you to create, start, update, and delete HTML5 applications.

> ### Note:  
> Assigning this scope to a role requires to assign the readAccount scope as well.



</td>
</tr>
<tr>
<td valign="top" rowspan="5">

Java Application Lifecycle Management



</td>
<td valign="top">

readJavaApplications



</td>
<td valign="top">

List Java Applications



</td>
<td valign="top">

Enables you to list Java applications, get their status, and list Java application processes.

> ### Note:  
> Assigning this scope to a role requires to assign the readMonitoringData scope as well.



</td>
</tr>
<tr>
<td valign="top">

manageJavaApplications



</td>
<td valign="top">

Manage Java Applications



</td>
<td valign="top">

Enables you to create, deploy, start, stop, update, and delete a Java application.

> ### Note:  
> Assigning this scope to a role requires to assign the readMonitoringData scope as well.



</td>
</tr>
<tr>
<td valign="top">

manageJavaProcesses



</td>
<td valign="top">

Manage Java Processes



</td>
<td valign="top">

Enables you to start or stop Java application processes.

> ### Note:  
> Assigning this scope to a role requires to assign the readMonitoringData scope as well.



</td>
</tr>
<tr>
<td valign="top">

profileApplication



</td>
<td valign="top">

Profile Java Applications



</td>
<td valign="top">

Enables you to profile Java applications.



</td>
</tr>
<tr>
<td valign="top">

debugApplication



</td>
<td valign="top">

Debug Java Applications



</td>
<td valign="top">

Enables you to debug Java applications.



</td>
</tr>
<tr>
<td valign="top" rowspan="2">

Keystore Service



</td>
<td valign="top">

manageKeystores



</td>
<td valign="top">

Manage Keystores



</td>
<td valign="top">

Enables you to manage \(create, delete, list\) key stores \(using the console client\).



</td>
</tr>
<tr>
<td valign="top">

readKeystores



</td>
<td valign="top">

View Keystores



</td>
<td valign="top">

Enables you to lists all the services grouped by service category in the cockpit and view their enablement status.



</td>
</tr>
<tr>
<td valign="top" rowspan="3">

Logging Service



</td>
<td valign="top">

readLogs



</td>
<td valign="top">

View Application Logs



</td>
<td valign="top">

Enables you to view all logs available for a Java application.



</td>
</tr>
<tr>
<td valign="top">

manageLogs



</td>
<td valign="top">

Manage Application Logs



</td>
<td valign="top">

Enables you to change the log level for Java application logs.



</td>
</tr>
<tr>
<td valign="top">

readHeapDumps



</td>
<td valign="top">

View Heap Dumps



</td>
<td valign="top">

Enables you to view heap dumps as well as to download heap dump files for a Java application.

> ### Note:  
> Assigning this scope to a role requires to assign the readLogs scope as well.



</td>
</tr>
<tr>
<td valign="top" rowspan="2">

Member Management



</td>
<td valign="top">

readAccountMembers



</td>
<td valign="top">

View Account Members



</td>
<td valign="top">

Enables you to view a list of members for an individual subaccount.

> ### Note:  
> Assigning this scope to a role requires to assign the readCustomPlatformRoles scope as well.



</td>
</tr>
<tr>
<td valign="top">

manageAccountMembers



</td>
<td valign="top">

Manage Account Members



</td>
<td valign="top">

Enables you to add and remove members for an individual subaccount and to assign user roles to them.



</td>
</tr>
<tr>
<td valign="top">

Metering Service



</td>
<td valign="top">

readMeteringData



</td>
<td valign="top">

Read Metering Data



</td>
<td valign="top">

Enables you to access data related to your application's resource consumption, e.g. network data volume or database size.



</td>
</tr>
<tr>
<td valign="top" rowspan="4">

Monitoring Service



</td>
<td valign="top">

readMonitoringConfiguration



</td>
<td valign="top">

Read Monitoring Configuration



</td>
<td valign="top">

Enables you to list JMX checks, availability checks, and alert recipients.



</td>
</tr>
<tr>
<td valign="top">

readMonitoringData



</td>
<td valign="top">

Read Monitoring Data



</td>
<td valign="top">

Enables you to view history of metrics, current metrics, and JMX MBeans.



</td>
</tr>
<tr>
<td valign="top">

manageMonitoringConfiguration



</td>
<td valign="top">

Manage Monitoring Configuration



</td>
<td valign="top">

Enables you to set and update JMX checks, availability checks, and alert recipients. It also allows you to manage custom HTTP checks.



</td>
</tr>
<tr>
<td valign="top">

executeJMXOperation



</td>
<td valign="top">

Execute JMX Operation



</td>
<td valign="top">

Enables you to run JMX operations through the JMX console.



</td>
</tr>
<tr>
<td valign="top" rowspan="2">

Multi-Target Application Management



</td>
<td valign="top">

readMultiTargetApplication



</td>
<td valign="top">

Browse Solutions Inventory



</td>
<td valign="top">

Enables you to list solutions, get their status, and list solution operations.



</td>
</tr>
<tr>
<td valign="top">

manageMultiTargetApplication



</td>
<td valign="top">

Manage Solutions



</td>
<td valign="top">

Enable you to deploy, delete, and subscribe to solutions using Multi-Target Applications \(MTA\).



</td>
</tr>
<tr>
<td valign="top" rowspan="2">

OAuth Client Management



</td>
<td valign="top">

readOAuthSettings



</td>
<td valign="top">

View OAuth Settings



</td>
<td valign="top">

Enables you to view OAuth Application Client settings.

> ### Note:  
> This scope is used for viewing the OAuth clients for **OAuth-protected applications**, not for the platform APIs. Each platform API requires its own scopes, described in its documentation.

> ### Note:  
> Assigning this scope to a role requires to assign the readAccount and readSubscriptions scopes as well.



</td>
</tr>
<tr>
<td valign="top">

manageOAuthSettings



</td>
<td valign="top">

Manage OAuth Settings



</td>
<td valign="top">

Enables you to manage OAuth Application Client settings.

> ### Note:  
> This scope is used for managing the OAuth clients for **OAuth-protected applications**, not for the platform APIs. Each platform API requires its own scopes, described in its documentation.

> ### Note:  
> Assigning this scope to a role requires to assign the readAccount, readSubscriptions and readOAuthSettings scopes as well.



</td>
</tr>
<tr>
<td valign="top" rowspan="2">

Password Storage



</td>
<td valign="top">

managePasswords



</td>
<td valign="top">

Manage Passwords



</td>
<td valign="top">

Enables you to set and delete passwords for a given application in the password storage \(using the console client\).



</td>
</tr>
<tr>
<td valign="top">

readPasswords



</td>
<td valign="top">

Read Passwords



</td>
<td valign="top">

Enables you to retrieve the passwords put into password storage for a given application \(using the console client\).



</td>
</tr>
<tr>
<td valign="top" rowspan="4">

SAP HANA / SAP ASE Service



</td>
<td valign="top">

readDatabaseInformation



</td>
<td valign="top">

View Database Information



</td>
<td valign="top">

Enables you to view lists of SAP HANA and SAP ASE database systems, databases, and database-related service requests. You can also view information such as the assigned database type, the database version, and data source bindings.



</td>
</tr>
<tr>
<td valign="top">

administrateDatabases



</td>
<td valign="top">

Administrate Databases



</td>
<td valign="top">

Enables you to manage the lifecycle of SAP HANA and SAP ASE database systems \(upgrade, restart, etc.\). It also allows you how to create SAP HANA database users and assign the administrator role to them \(not applicable to SAP HANA MDC tenant databases\). In addition, it enables you to allow members of other subaccounts to open tunnels to SAP HANA and SAP ASE databases in your subaccount.



</td>
</tr>
<tr>
<td valign="top">

manageDatabases



</td>
<td valign="top">

Manage Databases



</td>
<td valign="top">

Enables you to manage SAP HANA and SAP ASE databases, database schemas for shared SAP HANA databases, and data source bindings. It also allows you to create database users and assign the developer role to them \(only applicable to SAP ASE databases and shared SAP HANA databases\).



</td>
</tr>
<tr>
<td valign="top">

openDatabaseTunnels



</td>
<td valign="top">

Manage Database Tunnels



</td>
<td valign="top">

Enables you to open tunnels to SAP HANA and SAP ASE databases.



</td>
</tr>
<tr>
<td valign="top" rowspan="2">

Service Management



</td>
<td valign="top">

listServices



</td>
<td valign="top">

List Services



</td>
<td valign="top">

Enables you to browse through the list of services and review their status in your subaccount.



</td>
</tr>
<tr>
<td valign="top">

manageServices



</td>
<td valign="top">

Manage Services



</td>
<td valign="top">

Allows you to list and enable services in the cockpit.

> ### Note:  
> For applying any service-specific configuration, additional scopes \(e.g. manageDestinations\) may be required.



</td>
</tr>
<tr>
<td valign="top" rowspan="2">

Subscription Management



</td>
<td valign="top">

manageSubscriptions



</td>
<td valign="top">

Manage Subscriptions



</td>
<td valign="top">

Enables you to manage subscribed Java and HTML5 applications.

> ### Note:  
> Assigning this scope to a role requires to assign the manageHTML5Applications scope as well. It is planned to remove this requirement in a future release.



</td>
</tr>
<tr>
<td valign="top">

readSubscriptions



</td>
<td valign="top">

View Subscriptions



</td>
<td valign="top">

Enables you to list your subscribed Java and HTML5 applications.

> ### Note:  
> Assigning this scope to a role requires to assign the readHTML5Applications scope as well. It is planned to remove this requirement in a future release.



</td>
</tr>
<tr>
<td valign="top" rowspan="2">

Trust Management



</td>
<td valign="top">

readTrustSettings



</td>
<td valign="top">

View Trust Settings



</td>
<td valign="top">

Enables you to read trust configurations.

> ### Note:  
> Assigning this scope to a role requires to assign the readAccount, readAuthorizationSettings and readSubscriptions scopes as well.



</td>
</tr>
<tr>
<td valign="top">

manageTrustSettings



</td>
<td valign="top">

Manage Trust Settings



</td>
<td valign="top">

Enables you to manage trust configurations \(change local provider, add trusted application/platform IdPs\).

> ### Note:  
> Assigning this scope to a role requires to assign the readTrustSettings, readAccount, readAuthorizationSettings and readSubscriptions scopes as well.



</td>
</tr>
<tr>
<td valign="top" rowspan="2">

Virtual Machines



</td>
<td valign="top">

readVirtualMachines



</td>
<td valign="top">

List Virtual Machines



</td>
<td valign="top">

Enables you to list virtual machines, volumes, volume snapshots, security group rules, to get their status, and list virtual machine processes.



</td>
</tr>
<tr>
<td valign="top">

manageVirtualMachines



</td>
<td valign="top">

Manage Virtual Machines



</td>
<td valign="top">

Enables you to create and delete virtual machines, volumes, volume snapshots, security group rules, and access points.



</td>
</tr>
</table>

