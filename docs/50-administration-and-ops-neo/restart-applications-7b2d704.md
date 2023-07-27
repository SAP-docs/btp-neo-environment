<!-- loio7b2d7049d7434575ae425e96215f57aa -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Restart Applications

You can directly restart applications, as well as restart individual application processes.



## Context

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://launchpad.support.sap.com/#/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**

To restart a Java application without downtime in the SAP BTP cockpit, do the following:



## Procedure

1.  Open the subaccount in the cockpit.

    For information about the cockpit logon URL according to your region and host, see the *Related Information* section.

2.  Choose *Applications* \> *Java Applications* in the navigation area.

3.  To choose an action for an application process, click the relevant application's name in the list to go the the application overview page.

4.  Choose *Monitoring* \> *Processes* in the navigation area and proceed as follows:

    1.  Start an additional process.

        Choose <span style="font-size:24px;line-height: 28px;"><span class="SAP-icons"></span></span> \(Start Additional Process\).

        The application’s state continues to be shown as *Started* and an additional process appears in the *Processes* panel.

        > ### Note:  
        > If the number of running processes equals the maximum number of processes, you won't be able to start a new process. To start an additional process, increase the maximum number of processes to at least one more than the current number of running processes.

    2.  Disable the old process.

        Choose <span style="font-size:24px;line-height: 28px;"><span class="SAP-icons"></span></span> \(Disable Process\).

        The process state changes to *Started \(disabled\)*. The process continues to handle working sessions, but does not accept new connections, which allows you to shut it down gracefully.

    3.  Wait for at least 30 seconds so that all running requests are completed.

    4.  Stop the old process.

        Choose <span style="font-size:24px;line-height: 28px;"><span class="SAP-icons"></span></span> \(Stop\).

        The process is stopped and removed from the list.

    5.  Repeat until all application processes have been restarted.



