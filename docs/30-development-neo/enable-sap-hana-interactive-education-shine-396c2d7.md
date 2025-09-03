<!-- loio396c2d7a319747caac332a38f76cfc76 -->

# Enable SAP HANA Interactive Education \(SHINE\)

You can enable the SAP HANA Interactive Education \(SHINE\) demo application for a new or existing SAP HANA tenant database.



## Context

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/docs/btp/sap-business-technology-platform/sap-business-technology-platform?version=Cloud) .**

> ### Restriction:  
> SHINE is not available on the China \(Shanghai\) region.

SAP HANA Interactive Education \(SHINE\) demonstrates how to build native SAP HANA applications. The demo application comes with sample data and design-time developer objects for the application's database tables, data views, stored procedures, OData, and user interface. For more information, see the [SAP HANA Interactive Education \(SHINE\) documentation](http://help.sap.com/hana/SAP_HANA_Interactive_Education_SHINE_en.pdf).

By default, SHINE is available for all SAP HANA tenant databases in trial accounts in the Neo environment.



## Procedure

1.  Log in to the SAP BTP cockpit navigate to a subaccount. For more information, see [Navigate in the Cockpit](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/0874895f1f78459f9517da55a11ffebd.html "Learn how to navigate to your global accounts, directories, and subaccounts in the SAP BTP cockpit.") :arrow_upper_right:.

2.  In the navigation area, choose *SAP HANA / SAP ASE* \> *Databases & Schemas*.

3.  To enable SHINE for an SAP HANA tenant database, you must first create a SHINE user. If you are enabling SHINE for a new SAP HANA tenant database, a SHINE user can be automatically created during the database creation. If you are enabling SHINE for an existing SAP HANA tenant database, you must manually create the SHINE user.


    <table>
    <tr>
    <th valign="top">

    To...
    
    </th>
    <th valign="top">

    Do the following:
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    **Enable SHINE for a new SAP HANA tenant database**
    
    </td>
    <td valign="top">
    
    1.  Follow the steps described in [Create SAP HANA Tenant Databases](https://help.sap.com/viewer/d4790b2de2f4429db6f3dff54e4d7b3a/Cloud/en-US/533384eda57e428f98a43815e6a11119.html#loio46af2934d19343ca8250ce288d27ea41 "Use the cockpit to create an SAP HANA tenant database on an SAP HANA database management system in your subaccount in the Neo environment.") :arrow_upper_right:.
    2.  From the list of all databases and schemas, choose the SAP HANA tenant database you just created.
    3.  In the overview in the lower part of the screen, choose the *SAP HANA Interactive Education \(SHINE\)* link under *Education Tools*.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    **Enable SHINE for an existing SAP HANA tenant database**
    
    </td>
    <td valign="top">
    
    1.  From the list of all databases and schemas, choose the SAP HANA tenant database for which you want to enable SHINE.
    2.  In the overview in the lower part of the screen, open the *SAP HANA Cockpit* link under *Administration Tools*.
    3.  In the *Enter Username* field, enter `SYSTEM`, then enter the password you determined for the SYSTEM user.

        The first time you log in to the *SAP HANA Cockpit*, you are informed that you don't have the roles that you need to open the SAP BTP cockpit.

    4.  Choose *OK*. The required roles are assigned to you automatically.
    5.  Choose *Continue.*

        You are now logged in to the *SAP HANA Cockpit*.

    6.  Choose *Manage Roles and Users*.
    7.  To create database users and assign them the required roles, expand the *Security* node.
    8.  Open the context menu for the *Users* node and choose *New User*.
    9.  On the *User* tab, provide a name for the new SHINE user.

        > ### Note:  
        > The user name can contain only uppercase and lowercase letters \('a' - 'z', 'A' - 'Z'\), numbers \('0' - '9'\), and underscores \('\_'\).

        The user name always appears in uppercase letters.

    10. In the *Authentication* section, make sure the *Password* option is selected and enter a password.

        > ### Note:  
        > The password must contain at least one uppercase and one lowercase letter \('a' - 'z', 'A' - 'Z'\) and one number \('0' - '9'\). It can also contain special characters \(except ", ' and \\\).

    11. Choose *Save*.

        The new database user appears as a new node under the *Users* node.

    12. In the *Granted Roles* section, select *\+ \(Add Role\)*.
    13. Enter `democontent` in the search field and select all roles in the result list.
    14. Choose *Ok*.

        The roles are added to the *Granted Roles* tab.

    15. Save your changes.
    16. On the *Overview* page of your SAP HANA tenant database in the *cockpit*, choose the *SAP HANA Interactive Education \(SHINE\)* link under *Education Tools* in the lower part of the screen.


    
    </td>
    </tr>
    </table>
    
    A login screen for the SHINE demo application is shown in a new browser window.

4.  Enter the credentials of the SHINE user you created and choose *Login*.

    > ### Note:  
    > The first time you log in to the SHINE demo application, you are prompted to change your initial password.




## Results

You see the SHINE demo application for your SAP HANA tenant database. Consult the [SAP HANA Interactive Education \(SHINE\) documentation](http://help.sap.com/hana/SAP_HANA_Interactive_Education_SHINE_en.pdf) for detailed information about using the application.

