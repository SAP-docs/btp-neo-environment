<!-- loio7612f03c711e1014839a8273b0e91070 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Start and Stop Applications

You can directly start, stop, and undeploy applications, as well as start, stop, and disable individual application processes.



## Context

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**

An application can run on one or more application processes. The use of multiple processes allows you to distribute application load and provide failover capability. The number of processes that you can start depends on the compute unit quota available to your global account and how an individual application has been configured. If you reach the maximum, increase the maximum number of processes first before you can start another process.

> ### Note:  
> By default the application is started on one application process and is allowed to run on a maximum of one process. To use multiple processes, an application must be deployed with the `minimum-processes` and `maximum-processes` parameters set appropriately.

> ### Note:  
> While an application name is assigned manually and is unique in a subaccount, an application process ID is generated automatically whenever a new process is started and is unique across the cloud platform.



<a name="loio7612f03c711e1014839a8273b0e91070__steps_txs_4v4_zl"/>

## Procedure

1.  Open the subaccount in the cockpit.

    For information about the cockpit logon URL according to your region and host, see the *Related Information* section.

2.  Choose *Applications* \> *Java Applications* in the navigation area.

3.  You have the following options for the applications in the list:


    <table>
    <tr>
    <th valign="top">

    To...
    
    </th>
    <th valign="top">

    Choose...
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    Start an application
    
    </td>
    <td valign="top">
    
    <span style="font-size:24px;line-height: 28px;"><span class="SAP-icons"></span></span> \(Start\)

    The application transitions to the *Started* state.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Start an additional process
    
    </td>
    <td valign="top">
    
    <span style="font-size:24px;line-height: 28px;"><span class="SAP-icons"></span></span> \(Start Additional Process\)

    The application’s state continues to be shown as *Started* and an additional process appears in the *Processes* panel.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Stop an application
    
    </td>
    <td valign="top">
    
    <span style="font-size:24px;line-height: 28px;"><span class="SAP-icons"></span></span> \(Stop\)

    All running processes are stopped and the application transitions to the *Stopped* state.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Undeploy an application
    
    </td>
    <td valign="top">
    
    <span style="font-size:24px;line-height: 28px;"><span class="SAP-icons"></span></span> \(Delete\)

    The application is deleted from your subaccount and disappears from the application list. This also removes all data related to the application, such as configuration settings and logs.

    Data source bindings are not deleted. To delete all data source bindings created for this application, select the checkbox.

    > ### Note:  
    > Bound databases and schemas will not be deleted. You can delete database and schema bindings using the *Databases & Schemas* panel.


    
    </td>
    </tr>
    </table>
    
4.  To choose an action for an application process, click the relevant application's name in the list to go the the application overview page.

5.  Choose *Monitoring* \> *Processes* in the navigation area and proceed as follows:


    <table>
    <tr>
    <th valign="top">

    To...
    
    </th>
    <th valign="top">

    Choose...
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    Start an additional process
    
    </td>
    <td valign="top">
    
    <span style="font-size:24px;line-height: 28px;"><span class="SAP-icons"></span></span> \(Start Additional Process\)

    The application’s state continues to be shown as *Started* and an additional process appears in the *Processes* panel.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Restart a process
    
    </td>
    <td valign="top">
    
    <span style="font-size:24px;line-height: 28px;"><span class="SAP-icons"></span></span> \(Restart\)

    The running process is stopped and a new process started. A new process ID is generated automatically.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Disable a process
    
    </td>
    <td valign="top">
    
    <span style="font-size:24px;line-height: 28px;"><span class="SAP-icons"></span></span> \(Disable Process\)

    The process state changes to *Started \(disabled\)*. The process continues to handle working sessions, but does not accept new connections, which allows you to shut it down gracefully.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Enable a process
    
    </td>
    <td valign="top">
    
    <span style="font-size:24px;line-height: 28px;"><span class="SAP-icons"></span></span> \(Enable Process\)

    The process state changes back to *Started*.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Stop a process
    
    </td>
    <td valign="top">
    
    <span style="font-size:24px;line-height: 28px;"><span class="SAP-icons"></span></span> \(Stop\)

    The process is stopped and removed from the list. If the application has no further processes, it transitions to the *Stopped* state.
    
    </td>
    </tr>
    </table>
    

**Related Information**  


[Regions and Hosts Available for the Neo Environment](../10-concepts-neo/regions-and-hosts-available-for-the-neo-environment-d722f7c.md "Each region represents a geographical location (for example, Europe, US East) where applications, data, or services are hosted.")

[deploy](deploy-937db4f.md "Deploying an application publishes it to SAP BTP. Use the optional parameters to make some specific configurations of the deployed application.")

[Scale Applications](scale-applications-745781b.md "Each application is started on a dedicated SAP BTP Runtime. One application can be started on one or many application processes, according to the compute unit quota that you have.")

[Perform Soft Shutdown](perform-soft-shutdown-17e8e96.md "Soft shutdown enables an operator to stop an application or application process in a way that no data is lost. Using soft shutdown gives sufficient time to finish serving end user requests or background jobs.")

[Administering Database Schemas](https://help.sap.com/viewer/d4790b2de2f4429db6f3dff54e4d7b3a/Cloud/en-US/2040a8a60de84c09994f64f74896b18f.html "An overview of the different tasks you can perform to administer database schemas in the Neo environment.") :arrow_upper_right:

