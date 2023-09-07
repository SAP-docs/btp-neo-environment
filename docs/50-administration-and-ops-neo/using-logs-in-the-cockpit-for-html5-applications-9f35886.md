<!-- loio9f358860642c4ed283cd889a5bc42461 -->

# Using Logs in the Cockpit for HTML5 Applications

You can view logs on an HTML5 application running in your subaccount or on a subscription to an HTML application.

The cockpit provides the following types of logs for an HTML5 application:

-   Default traces

-   HTTP access logs


You can see the logs in a log viewer, or you can download them in a log file.

> ### Note:  
> The cockpit displays only the logs that are available for the application. For example, you see only HTTP access logs because no other logs are available for this application.



## Context

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**

Depending on the total logs size, a few files per day can be logged for each type of log \(default traces and HTTP access log\) . The logs are kept for 7 days before they are deleted. If the application is deleted, the logs are deleted as well. Currently, the following data is logged:

**Default Traces**

-   The time stamp \(date, time in milliseconds, time zone\) of when the error occurred
-   A unique request ID
-   The log level \(currently only ERROR and WARNING are available\)
-   The actual error message text

> ### Note:  
> Each row in the log can be up to 3 KB. If the row’s size is bigger than 3 KB, it’s truncated.

**HTML Access Logs**

-   The time stamp \(date, time in milliseconds, time zone\) of the request

-   The client IP address

-   The user ID

-   The request method \(for example GET\)

-   The request path suffix

-   The response status code

-   The request body size in bytes

-   The request processing duration in milliseconds


<a name="task_rnm_rbh_gn"/>

<!-- task\_rnm\_rbh\_gn -->

## View Logs for an HTML5 Application



<a name="task_rnm_rbh_gn__steps_gyj_wbh_gn"/>

## Procedure

1.  Open the subaccount in the SAP BTP cockpit.

    For more information, see [Navigate in the Cockpit](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/0874895f1f78459f9517da55a11ffebd.html "Learn how to navigate to your global accounts and subaccounts in the SAP BTP cockpit.") :arrow_upper_right:.

2.  Go to the *Applications* \> *HTML5 Applications* page of the subaccount.

3.  Choose the relevant application to go to the overview.

    The latest logs are listed in the *Most Recent Logging* panel with the following information: type; date and time of the last modification; and size.

4.  To view a more extensive list of logs, choose *Monitoring* \> *Logging* in the navigation area.

    This page lists all default traces and HTTP access log files for the last week with the following information:

    -   Date and time of the last modification

    -   Size


    .

5.  To display the contents of a particular log file, choose ![](images/Display_HTML5_Log_Icon_8241912.png) \(*Display*\). To download the file, choose ![](images/Download_HTML5_Log_Icon_1835bb5.png) \(*Download*\).


<a name="task_aj2_pdc_cqb"/>

<!-- task\_aj2\_pdc\_cqb -->

## View Logs for a Subscription to an HTML5 Application



<a name="task_aj2_pdc_cqb__steps_vrl_rdc_cqb"/>

## Procedure

1.  Open the subaccount in the SAP BTP cockpit.

    For more information, see [Navigate in the Cockpit](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/0874895f1f78459f9517da55a11ffebd.html "Learn how to navigate to your global accounts and subaccounts in the SAP BTP cockpit.") :arrow_upper_right:.

2.  Go to the *Applications* \> *Subscriptions* page of the subaccount.

3.  Choose the subscribed application to go to the overview.

4.  Choose *Logging* in the navigation area.

    This page lists all default traces and HTTP access log files for the last week with the following information:

    -   Date and time of the last modification

    -   Size


    .

5.  To display the contents of a particular log file, choose ![](images/Display_HTML5_Log_Icon_8241912.png) \(*Display*\). To download the file, choose ![](images/Download_HTML5_Log_Icon_1835bb5.png) \(*Download*\).


**Related Information**  


[Log Viewers for HTML5 Applications](https://help.sap.com/viewer/f88a032109f0429caea276fc6e3a95f9/Cloud/en-US/8a2bef5ed305481c9640b4cda3613293.html "The SAP BTP cockpit provides dedicated log viewers for showing default traces and HTTP access logs.") :arrow_upper_right:

