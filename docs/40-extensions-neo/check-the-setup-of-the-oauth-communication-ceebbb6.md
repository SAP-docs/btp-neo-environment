<!-- loioceebbb6270434fceaa64a92cef6c769c -->

# Check the Setup of the OAuth Communication



## Context

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/docs/btp/sap-business-technology-platform/sap-business-technology-platform?version=Cloud) .**



## Procedure

1.  Launch SAP Web IDE. You can follow the steps in [Configure and Check the SSO Configuration](configure-and-check-the-sso-configuration-f907bd4.md).

2.  Choose *File* \> *New* \> *Project from Template*, or on the SAP Web IDE welcome page, choose *New Project from Template* under *Create a Project*.

3.  In the *Template Selection*, select *List Report Application*. Choose *Next*.

4.  In the *Basic Information* section, add *TestExtension* as a project name and as a title. Choose *Next*.

5.  In the *Data Connection* section select *Service Catalog*. Then, select a system from the drop-down menu. The destination you have created before should be there.

6.  Select the destination you have defined. You should see a list of services.

7.  If you don’t get any errors, your destination with OAuth authentication is working, the test is fulfilled.

8.  Exit the wizard.


