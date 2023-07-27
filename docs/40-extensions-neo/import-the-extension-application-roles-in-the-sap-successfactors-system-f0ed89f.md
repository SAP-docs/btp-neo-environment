<!-- loiof0ed89f98d894f9591d9bad20c68cf5f -->

# Import the Extension Application Roles in the SAP SuccessFactors System

To complete the authorization configuration of your extension application, you import the application-specific roles into to the SAP SuccessFactors company instance connected to your extension subaccount.



## Prerequisites

-   You have created the resource file with the required role definitions. For more information, see [Create the Resource File with Role Definitions](create-the-resource-file-with-role-definitions-93d5ce5.md).
-   You have downloaded and configured SAP BTP console client. For more information, see [Using the Console Client](../50-administration-and-ops-neo/using-the-console-client-8900b22.md).

-   You have downloaded and set up the console client for SAP BTP, Neo environment. For more information, see [Console Client for the Neo Environment](../50-administration-and-ops-neo/console-client-for-the-neo-environment-7613230.md).




## Context

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://launchpad.support.sap.com/#/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**

Using the `hcmcloud-import-roles` console client command, you import the required role definitions in the SAP SuccessFactors company instance connected to this account.



<a name="loiof0ed89f98d894f9591d9bad20c68cf5f__steps_qmh_1mz_cq"/>

## Procedure

1.  To start the console client for SAP BTP, Neo environment, open the command prompt and navigate to the folder containing neo.bat/sh \(SDK installation folder/tools\). For more information, see [Using the Console Client](../50-administration-and-ops-neo/using-the-console-client-8900b22.md).

2.  Open the command prompt and navigate to the folder containing neo.bat/sh \(SDK installation folder/tools\).

3.  Execute the following command:

    ```
    neo hcmcloud-import-roles --account <subaccount_name> --user <e-mail_or_user> --host <host> --location <path to the file containing role definitions>
    ```

    > ### Note:  
    > For more information about the file that contains the role definitions, see [Create the Resource File with Role Definitions](create-the-resource-file-with-role-definitions-93d5ce5.md).

    > ### Note:  
    > The size of the file containing the role definitions must not exceed 500 KB.

4.  Enter your password if requested.

5.  Press ENTER and the import of the role definitions starts.




## Results

You have imported the application-specific roles in the SAP SuccessFactors company instance connected to your subaccount. Now you need to assign users to these roles.

**Related Information**  


[Assign the Extension Application Roles to Users](assign-the-extension-application-roles-to-users-d838fff.md "To complete the authorization configuration for your extension application, you assign the extension application roles you have imported in the SAP SuccessFactors systems to the user to whom you want to grant access to your application.")

[hcmcloud-import-roles](../50-administration-and-ops-neo/hcmcloud-import-roles-d3dd77e.md "This command imports SAP SuccessFactors HXM suite roles into the SAP SuccessFactors customer instance linked to an extension subaccount.")

