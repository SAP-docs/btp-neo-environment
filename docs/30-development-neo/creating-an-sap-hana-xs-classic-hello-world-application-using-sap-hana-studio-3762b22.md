<!-- loio3762b229a4074fc59ac6a9ee7404f8c9 -->

# Creating an SAP HANA XS Classic Hello World Application Using SAP HANA Studio

Create and test a simple SAP HANA XS classic application that displays the "Hello World" message.



## Prerequisites

-   You have a subaccount in the SAP BTP, Neo environment.

-   You're assigned the Administrator role for the subaccount.

-   Make sure the database you want to use is deployed in your account before you begin with this tutorial. For more information, see [Getting Started](https://help.sap.com/viewer/d4790b2de2f4429db6f3dff54e4d7b3a/Cloud/en-US/446fa573ed7142788d646fc023ab1cfd.html "Choose your quickstart scenario based on the type of the database system.") :arrow_upper_right:. You can create SAP HANA XS classic applications using one of the following database systems:

    -   SAP HANA single-container database system \(XS\)

    -   SAP HANA tenant database system \(MDC\)


-   You also need to install the tools as described in [Install SAP HANA Tools for Eclipse](install-sap-hana-tools-for-eclipse-b0e351a.md) to follow the steps described in this tutorial.




## Context

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**

In this tutorial, you complete the following steps:

1.  [Create a Database User](creating-an-sap-hana-xs-classic-hello-world-application-using-sap-hana-studio-3762b22.md#loioa9d9d44ef8ff423fbe848e80cd383054)
2.  [Add a Repository Workspace](creating-an-sap-hana-xs-classic-hello-world-application-using-sap-hana-studio-3762b22.md#loiod694ddc1e41d4c84b60708137b35b9c7)
3.  [Add an XS Application Project](creating-an-sap-hana-xs-classic-hello-world-application-using-sap-hana-studio-3762b22.md#loio93cfb85816144ec292bf115b6c8bb190)
4.  [Write Server-Side JavaScript](creating-an-sap-hana-xs-classic-hello-world-application-using-sap-hana-studio-3762b22.md#loio08cf4a2c726a46b192cd72e57a3e1218)
5.  [Test Your Application](creating-an-sap-hana-xs-classic-hello-world-application-using-sap-hana-studio-3762b22.md#loiod405d990fe634a0e8ba47baca7fb26bd)
6.  [Retrieve Data from SAP HANA](creating-an-sap-hana-xs-classic-hello-world-application-using-sap-hana-studio-3762b22.md#loio2642959ddda14ab6b4145ced47507fad)
7.  [Test Your Application Again](creating-an-sap-hana-xs-classic-hello-world-application-using-sap-hana-studio-3762b22.md#loio0d3002f953ec4a1190ac5b7ba019f16c)

<a name="loioa9d9d44ef8ff423fbe848e80cd383054"/>

<!-- loioa9d9d44ef8ff423fbe848e80cd383054 -->

## Create a Database User



## Context

You will perform all subsequent activities with this new user.



<a name="loioa9d9d44ef8ff423fbe848e80cd383054__steps_create_db_user_hana_mdc"/>

## Procedure

1.  In the SAP BTP cockpit, navigate to a subaccount. For more information, see [Navigate in the Cockpit](../50-administration-and-ops-neo/navigate-in-the-cockpit-fdeff7e.md).

2.  In the navigation area, choose *SAP HANA / SAP ASE* \> *Databases & Schemas*.

    All databases available in the selected account are listed with their ID, type, version, and related database system.

    > ### Tip:  
    > To view the details of a database, for example, its state and the number of existing bindings, select a database in the list and click the link on its name. On the overview of the database, you can perform further actions, for example, delete the database.

3.  Depending on the database you are using, choose one of the following options:


    <table>
    <tr>
    <th valign="top">

    If you want to create your application using...


    
    </th>
    <th valign="top">

    Do the following:


    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    **An SAP HANA XS database**


    
    </td>
    <td valign="top">
    
    Follow the steps described in [Create a Database Administrator User](create-a-database-administrator-user-c0fce6f.md).


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    **An SAP HANA tenant database**


    
    </td>
    <td valign="top">
    
    1.  Select the relevant SAP HANA tenant database in the list.

    2.  In the overview that is shown in the lower part of the screen, open the *SAP HANA Web-based Development Workbench* link under *Development Tools*.
    3.  In the *Enter Username* field, enter `SYSTEM`, then enter the password you determined for the SYSTEM user in the *Enter Password* field. You're now logged on to the SAP HANA cockpit.
    4.  Open the *Security* tool of the SAP HANA Web-based Development Workbench.
    5.  Expand the *Security* node.
    6.  Open the context menu for the *Users* node and choose *New User*.
    7.  On the *User* tab, provide a name for the new user.

        The user name always appears in upper case letters.

    8.  In the *Authentication* section, make sure the *Password* checkbox is selected and enter a password.

        > ### Note:  
        > The password must start with a letter and only contain uppercase and lowercase letters \('a' - 'z', 'A' - 'Z'\), and numbers \('0' - '9'\).

    9.  To create the database user, in the menu bar click the *Save* icon.

        The new database user is displayed as a new node under the *Users* node.

    10. To assign your user the roles with the required permissions for working with SAP HANA Web-based Development Workbench, go to the *Granted Roles* section and choose the *\+ \(Add\)* button.
    11. Type `ide` in the search field and select all roles in the result list.
    12. Choose *OK*.

        The roles are added on the *Granted Roles* tab.

    13. To assign the `CONTENT_ADMIN` role to the user, repeat the steps in the *Granted Roles* section, searching for `CONTENT_ADMIN`.

        > ### Note:  
        > For more information on the CONTENT\_ADMIN role, see [Predefined Database \(Catalog\) Roles](https://help.sap.com/viewer/b3ee5778bc2e4a089d3299b82ec762a7/2.0.06/en-US/de421861bb571014846288086be76719.html).

    14. Save your changes.
    15. Before you continue to work with the SAP HANA Web-based Development Workbench, you log out first and log on again with your new database user.

        > ### Caution:  
        > At this point, you are still logged on with the SYSTEM user. You can only use your new database user to work with SAP HANA Web-based Development Workbench by logging out from SAP HANA Cockpit first. Otherwise, you would automatically log in to the SAP HANA Web-based Development Workbench with the SYSTEM user instead of your new database user. Therefore, choose the *Logout* button before you continue to work with the SAP HANA Web-based Development Workbench, where you need to log on again with the new database user.



    
    </td>
    </tr>
    </table>
    

<a name="loiod694ddc1e41d4c84b60708137b35b9c7"/>

<!-- loiod694ddc1e41d4c84b60708137b35b9c7 -->

## Add a Repository Workspace



<a name="loiod694ddc1e41d4c84b60708137b35b9c7__prereq_vdh_g31_srb"/>

## Prerequisites

-   You've installed the latest SAP JVM version. For more information, see [\(Optional\) Install SAP JVM](https://help.sap.com/viewer/ea72206b834e4ace9cd834feed6c0e09/Cloud/en-US/76137f42711e1014839a8273b0e91070.html).

-   You've opened a tunnel to your database and make sure that it's open until you complete the tutorial. For more information, see [Open Database Tunnels](https://help.sap.com/viewer/d4790b2de2f4429db6f3dff54e4d7b3a/Cloud/en-US/6930850a8f9a40489c01ed1aa381946d.html).

-   You've installed and set up all the necessary tools. We recommend that you use the latest SAP HANA version. For more information, see [Install SAP HANA Tools for Eclipse](https://help.sap.com/viewer/d4790b2de2f4429db6f3dff54e4d7b3a/Cloud/en-US/b0e351ada628458cb8906f55bcac4755.html).

-   You've connected to the tenant database system via the Eclipse IDE. For more information, see [Connect to SAP HANA Databases via the Eclipse IDE](https://help.sap.com/viewer/d4790b2de2f4429db6f3dff54e4d7b3a/Cloud/en-US/4efc124a0ccc42b3b502ad3a3908d23d.html).




## Context

After you add the SAP HANA system hosting the repository that stores your application-development files, you must specify a repository workspace, which is the location in your file system where you save and work on the development files.



<a name="loiod694ddc1e41d4c84b60708137b35b9c7__steps_oz2_hkk_5x"/>

## Procedure

1.  In the Eclipse IDE, go to *Window* \> *Perspective* \> *Open Perspective* \> *Other*.

2.  Select *SAP HANA Development* and choose *Open*.

3.  In the *Repositories* view, choose *File* \> *New* \> *Repository Workspace*.

    -   SAP HANA system:

        Choose the same database system you just added for this tutorial.

        > ### Note:  
        > To add your database system to Elipse, follow the steps in [Connect to SAP HANA Databases via the Eclipse IDE](https://help.sap.com/viewer/d4790b2de2f4429db6f3dff54e4d7b3a/Cloud/en-US/4efc124a0ccc42b3b502ad3a3908d23d.html).

        > ### Remember:  
        > Make sure that the tunnel is open until you complete the tutorial.

    -   Workspace Name:

        If a default workspace exists, uncheck the *Default workspace* option and enter a workspace name.

        A folder with the name you type is created below the *Workspace Root*.

    -   Workspace root:

        The *Workspace Root* is a folder that contains the workspace you create in this step. The *Workspace Root* can be anywhere on your local file system.


4.  Choose *Finish.*




## Results

In the *Repositories* view, you see your workspace, which enables you to browse the repository of the system tied to this workspace. The repository packages are displayed as folders.

At the same time, a folder will be added to your file system to hold all your development files.

<a name="loio93cfb85816144ec292bf115b6c8bb190"/>

<!-- loio93cfb85816144ec292bf115b6c8bb190 -->

## Add an XS Application Project



## Context

After you set up a development environment for the chosen SAP HANA system, you can add a project to contain all the development objects you want to create as part of the application-development process. There are a variety of project types for different types of development objects. Generally, a project type ensures that only the necessary libraries are imported to enable you to work with development objects that are specific to a project type. In this tutorial, you create an XS Project.



<a name="loio93cfb85816144ec292bf115b6c8bb190__steps_y4k_zlk_5x"/>

## Procedure

1.  In the *SAP HANA Development* perspective in the Eclipse IDE, choose *File* \> *New* \> *XS Project*.

2.  Make sure the *Share project in SAP repository* option is selected.

3.  Enter a project name.

4.  Choose *Next*.

5.  Select the repository workspace you created in the previous step.

6.  Choose *Finish* without doing any further changes.




## Results

The *Project Explorer* view in the *SAP HANA Development* perspective in Eclipse displays the new project.

> ### Note:  
> If your XS Project isn’t visible in the *Project Explorer*, choose the*\(︙\)* button in menu bar for the *Project Explorer* view to change the project presentation from *Hierarchical* to *Flat*.

The system information in brackets to the right of the project node name in the *Project Explorer* view indicates that the project has been shared. Shared projects are regularly synchronized with the repository hosted on the SAP HANA system you’re connected to.

<a name="loio08cf4a2c726a46b192cd72e57a3e1218"/>

<!-- loio08cf4a2c726a46b192cd72e57a3e1218 -->

## Write Server-Side JavaScript



## Context

SAP HANA Extended Application Services \(SAP HANA XS\) supports server-side application programming in JavaScript. In this step, you add some simple JavaScript code that generates a page which displays the words `Hello, World!`



<a name="loio08cf4a2c726a46b192cd72e57a3e1218__steps_m1b_x52_vx"/>

## Procedure

1.  In the *Project Explorer* view in the *SAP HANA Development* perspective in Eclipse, right-click your XS project, and choose *New* \> *Other*.

    > ### Note:  
    > If your XS Project isn’t visible in the *Project Explorer*, choose the*\(︙\)* button in menu bar for the *Project Explorer* view to change the project presentation from *Hierarchical* to *Flat*.

2.  In the *Select a wizard* dialog, choose *SAP HANA* \> *Application Development* \> *XS JavaScript File*.

3.  In the *New XS JavaScript File* dialog, enter `MyFirstSourceFile.xsjs` as *File name*.

4.  Choose *Finish*.

5.  In the `MyFirstSourceFile.xsjs` file, enter the following code and save the file:

    ```
    $.response.contentType = "text/html";
    $.response.setBody( "Hello, World !");
    ```

    > ### Note:  
    > By default, saving the file automatically commits the saved version of the file to the repository.

    The example code shows how to use the SAP HANA XS JavaScript API's `response` object to write HTML. By typing `$.` you have access to the API's objects.

6.  Check that the application descriptor files \(`.xsapp` and `.xsaccess`\) are present in the root package of your new XS JavaScript application.

    The application descriptors are mandatory and describe the framework in which an SAP HANA XS classic application runs. The `.xsapp` file indicates the root point in the package hierarchy where content is to be served to client requests; the `.xsaccess` file defines who has access to the exposed content and how.

    > ### Note:  
    > By default, the project-creation Wizard creates the application descriptors automatically. If they aren't present, you see a 404 error message in the Web Browser when you call the XS JavaScript service. In this case, you need to create the application descriptors manually. See the [SAP HANA Developer Guide for SAP HANA Studio](http://help.sap.com/saphelp_hanaplatform/helpdata/en/4e/102295434d45b1b5b5e7cea036aab9/content.htm?frameset=/en/80/b052e7c2c54a358a1a675d3bd5c3b8/frameset.htm&current_toc=/en/34/29fc63a1de4cd6876ea211dc86ee54/plain.htm&node_id=42) for instructions.

7.  Open the context menu for the new file and select *Team* \> *Activate*. The activate operation publishes your work and creates the corresponding catalog objects. You can now test it.


<a name="loiod405d990fe634a0e8ba47baca7fb26bd"/>

<!-- loiod405d990fe634a0e8ba47baca7fb26bd -->

## Test Your Application



## Context

Check if your application is working and if the `Hello, World!` message is displayed.



<a name="loiod405d990fe634a0e8ba47baca7fb26bd__steps_h1w_fqf_vx"/>

## Procedure

1.  In the SAP BTP cockpit, choose *SAP HANA / SAP ASE* \> *Databases & Schemas*.

2.  Select the relevant SAP HANA tenant database.

3.  Open the *SAP HANA Web-based Development Workbench* link under *Development Tools*.

4.  When the web editor opens, copy the first part of the URL up to and including the “*com*”.

5.  To form your target URL, add a */* followed by the project name.

6.  Then add another */* followed by the name of the file we just added in the previous step.

    **Example**

    **URL that you need to adapt**: https://mydadb01wfddybp1mp.int.sap.eu2.hana.ondemand.com/sap/hana/ide/

    **Project name**: hana-one

    **File name**: MyFirstSourceFile.xsjs

    **Target URL**: https://mydadb01wfddybp1mp.int.sap.eu2.hana.ondemand.com/hana-one/MyFirstSourceFile.xsjs

7.  Place the target URL in your web browser address bar and press [ENTER\] to see the response.

    > ### Note:  
    > If you've used an SAP HANA XS database for creating your SAP HANA XS classic application, you can also launch your application from the SAP BTP cockpit by choosing the application URL after navigating to *Applications* \> *HANA XS Applications*. For more information, see [Launch SAP HANA XS Applications](launch-sap-hana-xs-applications-0dd61c3.md).




## Results

The following text should be displayed:

```
Hello, World !
```

<a name="loio2642959ddda14ab6b4145ced47507fad"/>

<!-- loio2642959ddda14ab6b4145ced47507fad -->

## Retrieve Data from SAP HANA



## Context

To extract data from the database, you use your JavaScript code to open a connection to the database and then prepare and run an SQL statement. The results are added to the `Hello, World!` response. You use the following SQL statement to extract data from the database:

```
select * from DUMMY 
```

The SQL statement returns one row with one field called *DUMMY*, whose value is *X*.



<a name="loio2642959ddda14ab6b4145ced47507fad__steps_yrg_srf_vx"/>

## Procedure

1.  In the *Repositories* view in the *SAP HANA Development* perspective in Eclipse, open the `MyFirstSourceFile.xsjs` file in the embedded JavaScript editor.

2.  In the `MyFirstSourceFile.xsjs` file, replace your existing code with the following code:

    ```
    $.response.contentType = "text/html";
    var output = "Hello, World !"; 
    
    var conn = $.db.getConnection();
    var pstmt = conn.prepareStatement( "select * from DUMMY" );
    var rs = pstmt.executeQuery();
    
    if (!rs.next()) {
        $.response.setBody( "Failed to retrieve data" );
        $.response.status =  $.net.http.INTERNAL_SERVER_ERROR;
    } else {
        output = output + "This is the response from my SQL: " + rs.getString(1);
    }
    rs.close();
    pstmt.close();
    conn.close();
    
    $.response.setBody(output);
    ```

3.  Save the file `MyFirstSourceFile.xsjs`.

4.  Open the context menu of the `MyFirstSourceFile.xsjs` file and choose *Team* \> *Activate*.


<a name="loio0d3002f953ec4a1190ac5b7ba019f16c"/>

<!-- loio0d3002f953ec4a1190ac5b7ba019f16c -->

## Test Your Application Again



## Context

Check if your application is retrieving data from your SAP HANA database.



<a name="loio0d3002f953ec4a1190ac5b7ba019f16c__steps_h1w_fqf_vx"/>

## Procedure

1.  In the SAP BTP cockpit, choose *SAP HANA / SAP ASE* \> *Databases & Schemas*.

2.  Select the relevant SAP HANA tenant database.

3.  Open the *SAP HANA Web-based Development Workbench* link under *Development Tools*.

4.  When the web editor opens, copy the first part of the URL up to and including the “*com*”.

5.  To form your target URL, add a */* followed by the project name.

6.  Then add another */* followed by the name of the file we just added in the previous step.

    **Example**

    **URL that you need to adapt**: https://mydadb01wfddybp1mp.int.sap.eu2.hana.ondemand.com/sap/hana/ide/

    **Project name**: hana-one

    **File name**: MyFirstSourceFile.xsjs

    **Target URL**: https://mydadb01wfddybp1mp.int.sap.eu2.hana.ondemand.com/hana-one/MyFirstSourceFile.xsjs

7.  Place the target URL in your web browser address bar and press [ENTER\] to see the response.

    > ### Note:  
    > If you've used an SAP HANA XS database for creating your SAP HANA XS classic application, you can also launch your application from the SAP BTP cockpit by choosing the application URL after navigating to *Applications* \> *HANA XS Applications*. For more information, see [Launch SAP HANA XS Applications](launch-sap-hana-xs-applications-0dd61c3.md).




## Results

The following text should be displayed:

```
Hello, World!This is the reponse from my SQL: X
```

