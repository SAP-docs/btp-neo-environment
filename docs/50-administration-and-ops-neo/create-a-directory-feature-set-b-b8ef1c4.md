<!-- loiob8ef1c48499a49e9a2dc1d1c8de0a85a -->

# Create a Directory \[Feature Set B\]

Create a directory using the SAP BTP cockpit to organize and manage your subaccounts. For example, you can group subaccounts by project, team, or department.



## Context

> ### Note:  
> This feature is new in Feature Set B so there is no equivalent in Feature Set A. For more information, see [Cloud Management Tools — Feature Set Overview](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/caf4e4e23aef4666ad8f125af393dfb2.html "Cloud management tools represent the group of technologies designed for managing SAP BTP.") :arrow_upper_right:.

For more information on directories, see [Directories \[Feature Set B\]](../10-concepts-neo/account-model-722a475.md#loioa92721fc75524ec09a7a7255997dbd94).



## Procedure

1.  In your global account, navigate to the *Account Explorer* page.

2.  In the *Create* dropdown, choose *Directory*.

3.  In the dialog, enter a display name for your new directory and choose a parent. The parent can be the global account or another directory.

4.  **Optional:** Under *Advanced* \> *Labels*, assign labels to the directory to make organizing and filtering your directories and their subaccounts easier. For more information, see [Labels \[Feature Set B\]](../10-concepts-neo/account-model-722a475.md#loioe8663c08ead648faa673b0d63c5b478e).

    > ### Tip:  
    > -   When adding multiple values to a label, press [Enter\] after each value.
    > -   When you start typing, any matching label names and values that are already assigned to other directories in your global account are offered as suggestions.

    > ### Note:  
    > All subaccounts in the path of this directory also inherit all labels that are assigned to this directory.

5.  Review the details of your directory and choose *Create* to finalize the process.




<a name="loiob8ef1c48499a49e9a2dc1d1c8de0a85a__result_cfq_gxk_kkb"/>

## Results

Your directory is created.



<a name="loiob8ef1c48499a49e9a2dc1d1c8de0a85a__postreq_xpr_bxk_kkb"/>

## Next Steps

Once you've created a directory you can perform the following actions:

-   Edit the directory - you can edit the name, description, entitlements and labels of the directory.
-   Add subaccounts to the directory - [Manage the Account Explorer Hierarchy \[Feature Set B\]](manage-the-account-explorer-hierarchy-feature-set-b-2e2a5b6.md).
-   Delete the directory - you can only delete a directory that does not contain any subaccounts or subdirectories.

**Related Information**  


[Cloud Management Tools — Feature Set Overview](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/caf4e4e23aef4666ad8f125af393dfb2.html "Cloud management tools represent the group of technologies designed for managing SAP BTP.") :arrow_upper_right:

[Directories \[Feature Set B\]](../10-concepts-neo/account-model-722a475.md#loioa92721fc75524ec09a7a7255997dbd94 "Directories allow you to organize and manage your subaccounts according to your technical and business needs.")

[Manage the Account Explorer Hierarchy \[Feature Set B\]](manage-the-account-explorer-hierarchy-feature-set-b-2e2a5b6.md "Create an account structure by creating a hierarchy of directories and subaccounts using the SAP BTP cockpit. Add, move, and delete subaccounts and directories in your structure.")

[Manage Users in Directories \[Feature Set B\]](manage-users-in-directories-feature-set-b-ff4d4a4.md "Manage members in your directory using the SAP BTP cockpit.")

[Configure Entitlements and Quotas for Directories [Feature Set B]](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/37f8871865114f44aebee3db6ac64b72.html "Assign entitlements to directories by adding service plans and distribute the quotas available in your global account to your directories using the SAP BTP cockpit.") :arrow_upper_right:

[View Directory Usage Analytics \[Feature Set B\]](view-directory-usage-analytics-feature-set-b-a287782.md "You can explore, compare, and analyze all your actual usage data for the services and applications that are available in your directory.")

[Labels \[Feature Set B\]](../10-concepts-neo/account-model-722a475.md#loioe8663c08ead648faa673b0d63c5b478e "Labels are user-defined words or phrases that you can assign to various entities in SAP BTP to categorize them in your global account, to identify them more easily.")

