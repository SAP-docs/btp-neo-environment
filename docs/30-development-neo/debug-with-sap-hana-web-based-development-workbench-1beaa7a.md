<!-- loio1beaa7aaadc743568c8144066d005dab -->

# Debug with SAP HANA Web-based Development Workbench

You can only debug SAP HANA server-side JavaScript with the SAP HANA Tools plugin for Eclipse as of release 7.4. If you are working with lower plugin versions, use the SAP HANA Web-based Development Workbench to perform your debugging tasks.



## Prerequisites

-   Your database user is assigned the *sap.hana.xs.debugger::Debugger* role.
-   You have enabled debugging in the SAP HANA studio. Note that to do the following, you require the *sap.hana.xs.lm.roles::Administrator* role:
    1.  Switch to the *Administration Console* perspective.
    2.  Double-click your system.
    3.  Switch to the *Configuration* tab.
    4.  Set the following parameter: *xsengine.ini* \> *debugger* \> *enabled=true*. If the *debugger* section is not already present, create it and add the parameter *enabled*. Assign the value `true` to the *enabled* parameter.




## Context

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of the following technology portfolios: application development; process automation; integration; data, analytics, and enterprise planning; artificial intelligence. The platform offers users the ability to turn data into business value, compose end-to-end business processes, connect entire IT landscapes, and personalize, build and extend SAP applications. This reduces the overall total cost of ownership maintaining SAP landscapes and third-party software across end-to-end business processes.") :arrow_upper_right:.**



## Procedure

1.  In the SAP BTP cockpit, navigate to a subaccount. For more information, see [Navigate in the Cockpit](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/0874895f1f78459f9517da55a11ffebd.html "Learn how to navigate to your global accounts, directories, and subaccounts in the SAP BTP cockpit.") :arrow_upper_right:.

2.  Choose *Applications* \> *HANA XS Applications*.

    > ### Note:  
    > We recommend that you use the Google Chrome browser.

3.  In the *HANA XS Applications* table, select the application to display its details.

4.  In the *Application Details* section, click *Open in Web-based Development Workbench*. Note that the SAP HANA Web-based Development Workbench can also be opened directly at the following URL: `https://<database instance><subaccount>.<host>/sap/hana/xs/ide/`

5.  Depending on whether you want to debug a `.xsjs` file or a more complex scenario \(set a breakpoint in a `.xsjs` file and run another file\), do the following:

    -   `.xsjs` file:
        1.  Set the breakpoints and then choose the *Run on server \(F8\)* button.

    -   Complex scenario:

        1.  Set the breakpoint in the `.xsjs` file you want to debug.
        2.  Open a new tab in the browser and then open the other file on this tab by entering its URL \(`https://<database instance><subaccount>.<host>/<package>/<file>`\).

        > ### Note:  
        > If you synchronously call the `.xsjs` file in which you have set a breakpoint and then open the other file in the SAP HANA Web-based Development Workbench and execute it by choosing the *Run on server \(F8\)* button, you will block your debugging session. You will then need to terminate the session by closing the SAP HANA Web-based Development Workbench tab.


    > ### Note:  
    > If you leave your debugging session idle for some time once you have started debugging, your session will time out. An error in the WebSocket connection to the backend will be reported and your WebSocket connection for debugging will be closed. If this occurs, reopen the SAP HANA Web-based Development Workbench and start another debugging session.


