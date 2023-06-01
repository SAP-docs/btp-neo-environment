<!-- loio4959458552574c77b62fe27b0eb363ef -->

# Creating an SAP HANA XS Hello World Application Using SAP HANA Web-based Development Workbench

Create and test a simple SAP HANA XS application that displays the "Hello World" message using the SAP HANA Web-Based Development Workbench.

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**



<a name="loio4959458552574c77b62fe27b0eb363ef__section_awk_sqk_3gb"/>

## Prerequisites in Enterprise Accounts

-   Install an SAP HANA tenant database system \(MDC\). See [Install Database Systems](https://help.sap.com/viewer/3fa880aa54b74110ae99ad01503fcd60/Cloud/en-US/1261e6b87e174c05b774ea38fa3c8c51.html "Install a database system in the Neo environment using the SAP BTP cockpit.") :arrow_upper_right:.

-   You are assigned the Administrator role for the subaccount.


 <a name="copy4b84bc893c23410aba4d35e7aabc9d88"/>

<!-- copy4b84bc893c23410aba4d35e7aabc9d88 -->

## Create a Database

In your subaccount in the SAP BTP cockpit, you create a database on an SAP HANA tenant database system.



## Procedure

1.  In the SAP BTP cockpit, navigate to a subaccount. For more information, see [Navigate in the Cockpit](../50-administration-and-ops-neo/navigate-in-the-cockpit-fdeff7e.md).

2.  In the navigation area, choose *SAP HANA / SAP ASE* \> *Databases & Schemas*.

3.  From the *Databases & Schemas* page, choose *New*.

4.  Enter the required data:


    <table>
    <tr>
    <th valign="top">

    Property


    
    </th>
    <th valign="top">

    Value


    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
         *Database ID* 


    
    </td>
    <td valign="top">
    
        Example: ***tutorial*** 


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
         *Database System* 


    
    </td>
    <td valign="top">
    
        An SAP HANA tenant database system.

    *Example:*

    ***mdc1 \(HANAMDC\)***

    > ### Note:  
    > ***mdc1*** corresponds to the database system on which you create the database.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
         *SYSTEM User Password* 


    
    </td>
    <td valign="top">
    
        The password for the SYSTEM user of the database.

    > ### Note:  
    > The SYSTEM user is a preconfigured database superuser with irrevocable system privileges, such as the ability to create other database users, access system tables, and so on. A database-specific SYSTEM user exists in every database of a tenant database system.


    
    </td>
    </tr>
    </table>
    
5.  Choose *Create*.

6.  The *Events* page shows the progress of the database creation. Wait until the tenant database is in state *Started*.

7.  \(Optional\) To view the details of the new database, choose *Overview* in the navigation area and select the database in the list. Verify that the status *STARTED* is displayed.


 <a name="copy3954abb204c94c27bda8160c9b9b0e05"/>

<!-- copy3954abb204c94c27bda8160c9b9b0e05 -->

## Create a Database User and Add the Required Roles

Create a new database user in the SAP HANA cockpit and assign the user the required permissions for working with the SAP HANA Web-based Development Workbench.



<a name="copy3954abb204c94c27bda8160c9b9b0e05__context_tgm_vsk_3gb"/>

## Context

You've specified a password for the SYSTEM user when you created an SAP HANA tenant database. You now use the SYSTEM user to log on to SAP HANA cockpit and create your own database administration user.

> ### Caution:  
> You should not use the SYSTEM user for day-to-day activities. Instead, use this user to create dedicated database users for administrative tasks and to assign privileges to these users.



<a name="copy3954abb204c94c27bda8160c9b9b0e05__steps_q2q_4y3_1fb"/>

## Procedure

1.  Log on to the SAP HANA cockpit:

    1.  In the navigation area of the SAP BTP cockpit, choose *SAP HANA / SAP ASE* \> *Databases & Schemas*.

    2.  Select the relevant SAP HANA tenant database in the list.

    3.  In the database overview, open the*SAP HANA Web-based Development Workbench* link under *Development Tools*.

    4.  Enter ***SYSTEM*** as the user, and its password.

        A message appears, telling you that you don’t have the required roles.

    5.  Choose *OK*.

        You receive a confirmation that the required roles are assigned to you automatically.

    6.  Choose *Continue*.

        You’re now logged on to the SAP HANA cockpit.


2.  Open the *Security* tool of the SAP HANA Web-based Development Workbench.

3.  Expand the *Security* node.

4.  Open the context menu for the *Users* node and choose *New User*.

5.  On the *User* tab, provide a name for the new user.

    The user name always appears in upper case letters.

6.  In the *Authentication* section, make sure the *Password* checkbox is selected and enter a password.

    The password must start with a letter and only contain uppercase and lowercase letters \('a' – 'z', 'A' – 'Z'\), and numbers \('0' – '9'\).

7.  To create the database user, in the menu bar click the *Save* icon.

    The new database user is displayed as a new node under the *Users* node.

8.  To assign your user the roles with the required permissions for working with SAP HANA Web-based Development Workbench, go to the *Granted Roles* section and choose the *\+ \(Add\)* button.

9.  Type ***ide*** in the search field and select all roles in the result list.

10. Choose *OK*.

    The roles are added on the *Granted Roles* tab.

11. To assign the `CONTENT_ADMIN` role to the user, repeat the steps in the *Granted Roles* section, searching for `CONTENT_ADMIN`.

    > ### Note:  
    > For more information about the CONTENT\_ADMIN role, see [Predefined Database \(Catalog\) Roles](https://help.sap.com/viewer/b3ee5778bc2e4a089d3299b82ec762a7/2.0.06/en-US/de421861bb571014846288086be76719.html).

12. Save your changes.

13. Before you continue to work with the SAP HANA Web-based Development Workbench, you log out first and log on again with your new database user.

    > ### Caution:  
    > At this point, you’re still logged on with the SYSTEM user. You can only use your new database user to work with SAP HANA Web-based Development Workbench by logging out from SAP HANA cockpit first. Otherwise, you would automatically log in to the SAP HANA Web-based Development Workbench with the SYSTEM user instead of your new database user. Therefore, choose the *Logout* button before you continue to work with the SAP HANA Web-based Development Workbench, where you need to log on again with the new database user.

14. \(Optional\) [Disable the Password Lifetime Handling for a New Technical SAP HANA Database User](https://help.sap.com/viewer/d4790b2de2f4429db6f3dff54e4d7b3a/Cloud/en-US/c3d14449083f4ef895926c19a8d151f6.html "When you create a data source binding in the Neo environment, you specify a technical database user that determines to which SAP HANA XS or SAP HANA tenant database schema the application is bound. You need to prevent the system from asking you to change the initial password of that user. Otherwise, the application may not start correctly.") :arrow_upper_right:.

    This step isn’t necessary to complete this tutorial, but you shouldn't forget to disable the password lifetime handling in productive scenarios.


 <a name="copyac4b1ad8e271437c99ec3508023ab4f2"/>

<!-- copyac4b1ad8e271437c99ec3508023ab4f2 -->

## Create and Deploy an SAP HANA XS Classic Application

Create an SAP HANA XS classic Hello World program using the SAP HANA Web-based Development Workbench.



## Procedure

1.  In the navigation area of the SAP BTP cockpit, choose *SAP HANA / SAP ASE* \> *Databases & Schemas*.

2.  Select the relevant database.

3.  In the database overview, open the *SAP HANA Web-based Development Workbench* link under *Development Tools*.

4.  Log on to the SAP HANA Web-based Development Workbench with your new database user and password.

5.  Open the *Editor* tool of the SAP HANA Web-based Development Workbench.

    > ### Tip:  
    > The editor header shows details for your user and database. Hover over the entry for the SID to view the details.

6.  To create a new package, choose *New* \> *Package* from the context menu of the *Content* folder.

7.  Enter a package name.

    The package appears under the *Content* folder node.

8.  From the context menu for the new package node, choose *Create Application*.

9.  Select *HANA XS Hello World* as template and choose *Create*.

10. To deploy the program, select the `logic.xsjs` file from the new package and choose *Run*.

    The program is deployed and appears in the browser: ***Hello World from User <Your User\>.***


