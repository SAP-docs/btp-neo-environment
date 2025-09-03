<!-- loio42575dcfcc784ec4aab6a23e9310a5fa -->

# Create an HTML5 Application

You create new applications in the SAP BTP cockpit.



## Context

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/docs/btp/sap-business-technology-platform/sap-business-technology-platform?version=Cloud) .**

For each new application a new Git repository is created automatically. To view detailed information on the Git repository, including the repository URL and the latest commits, choose *Applications* \> *HTML5 Applications* in the navigation area and then *Versioning*.

> ### Note:  
> To create the HTML5 application in more than one region, create the application in each region separately and copy the content to the new Git repository.



## Procedure

1.  Log on with a user \(who is a subaccount member\) to the SAP BTP cockpit.

2.  Choose *Applications* \> *HTML5 Applications* in the navigation area.

    If you have already created applications using this subaccount, the list of HTML5 applications is displayed.

3.  To create a new HTML5 application, choose *New Application* and enter an application name.

    > ### Note:  
    > Adhere to the naming convention for application names:
    > 
    > -   The name must contain no more than 30 characters.
    > -   The name must contain only lowercase alphanumeric characters.
    > -   The name must start with a letter.

4.  Choose *Save*.

5.  Clone the repository to your development environment.

    1.  To start SAP Web IDE and automatically clone the repository of your app, choose *Edit Online* \(![](images/HTML5_Edit_Online_Button_272cc13.png)\) at the end of the table row of your application.

    2.  On the *Clone Repository* screen, if prompted enter your user and password \(SCN user and SCN password\), and choose *Clone*.





## Results

You created an application and a corresponding Git repository.

**Related Information**  


[Navigate in the Cockpit](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/0874895f1f78459f9517da55a11ffebd.html "Learn how to navigate to your global accounts, directories, and subaccounts in the SAP BTP cockpit.") :arrow_upper_right:

