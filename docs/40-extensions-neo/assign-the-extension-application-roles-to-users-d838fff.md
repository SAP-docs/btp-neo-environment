<!-- loiod838fff69c8e4c1ab7e84ed2794f2b1e -->

# Assign the Extension Application Roles to Users

To complete the authorization configuration for your extension application, you assign the extension application roles you have imported in the SAP SuccessFactors systems to the user to whom you want to grant access to your application.



## Prerequisites

-   You have a role-based permission environment for your SAP SuccessFactors company instance.
-   Your have either a *Super Administrator* or a *Security Admin* user for SAP SuccessFactors and have access to the functionality on the SAP SuccessFactors Admin page.
-   You have deployed the extension application.



## Context

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**

Use this procedure to assign the permission roles to users.



<a name="loiod838fff69c8e4c1ab7e84ed2794f2b1e__steps_vth_y2g_dq"/>

## Procedure

1.  Log on to SAP SuccessFactors with the following URL:

    ***https://*<SAP\_SuccessFactors\_landscape\>*/login***

    Where *<SAP\_SuccessFactors\_landscape\>* is the fully qualified domain name of the host on which the SAP SuccessFactors company is running.

2.  Navigate to the *Manage Permission Roles*, as follows:

    -   For Version 12 UI Framework \(Revolution\) not enabled: Navigate to:*Admin Center* \> *Manage Security* \> *Manage Permission Roles*.

    -   For Version 12 UI Framework \(Revolution\) enabled: Navigate to: *Admin Center* \> *Manage Employees* \> *Set User Permissions* \> *Manage Permission Roles*.

3.  Locate the role you want to manage, and from the *Take Action* dropdown box next to the role, select *Edit*.

4.  On the *Permission Role Detail* page, scroll down to the *Grant this role to...*section, and then choose *Add*. The system opens the *Grant this role to...* page.

5.  On the *Grant this role to...* page, define whom you want to grant this role to, and specify the target population accordingly.

6.  To navigate back to the *Permission Role Detail* page, choose *Finished*.

7.  Save your entries.


