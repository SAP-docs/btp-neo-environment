<!-- loio2e2a5b67f5ba4782a9070534148e8426 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Manage the Account Explorer Hierarchy \[Feature Set B\]

Create an account structure by creating a hierarchy of directories and subaccounts using the SAP BTP cockpit. Add, move, and delete subaccounts and directories in your structure.



<a name="loio2e2a5b67f5ba4782a9070534148e8426__context_rns_xdt_1qb"/>

## Context

Here, you'll learn how to:

-   Add directories and subaccounts to a directory

-   Move directories and subaccounts in the account structure

-   Delete directories and subaccounts from the account structure


A subaccount moves with its assigned service plans and quota. The entitlements of the source and target directories are adjusted accordingly.

If any entitlement for a plan in the target directory is configured with the auto-assign option, it is then automatically applied to the moved subaccount. Automatic quota assignments are subject to available quota in the target directory.

You can create a hierarchical structure that is 7 levels deep. The highest level of a given path is always the global account and the lowest is a subaccount, which means that you can have up to 5 levels of directories.



<a name="loio2e2a5b67f5ba4782a9070534148e8426__steps_x5j_1ft_1qb"/>

## Procedure

1.  Add directories and subaccounts to a directory.

    1.  When creating a new directory or subaccount, you can choose the parent directory directly in the creation dialog.


2.  Move subaccounts in the account structure.

    1.  Click <span class="SAP-icons"></span> Actions and select *Edit*. Then select a new parent.

    2.  Click <span class="SAP-icons"></span> Actions and select *Move*. Then select a new parent.

    3.  Click <span class="SAP-icons"></span> Move to move subaccounts by drag and dropping.


3.  Delete directories and subaccounts from the account structure.

    1.  Click <span class="SAP-icons"></span> Actions and select *Delete*.

    2.  To delete a subaccount, you can also navigate into the subaccount and click *Delete Subaccount*.



**Related Information**  


[Cloud Management Tools — Feature Set Overview](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/caf4e4e23aef4666ad8f125af393dfb2.html "Cloud management tools represent the group of technologies designed for managing SAP BTP.") :arrow_upper_right:

[Directories \[Feature Set B\]](../10-concepts-neo/account-model-722a475.md#loioa92721fc75524ec09a7a7255997dbd94 "Directories allow you to organize and manage your subaccounts according to your technical and business needs.")

[Create a Directory \[Feature Set B\]](create-a-directory-feature-set-b-b8ef1c4.md "Create a directory using the SAP BTP cockpit to organize and manage your subaccounts. For example, you can group subaccounts by project, team, or department.")

[Create a Subaccount](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/05280a123d3044ae97457a25b3013918.html "Create subaccounts in your global account using the SAP BTP cockpit.") :arrow_upper_right:

