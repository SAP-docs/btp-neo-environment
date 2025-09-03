<!-- loioede5f721e78e4d678c87c8a200c564ca -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Manage Custom Platform Roles

Subaccount administrators can define custom platform roles and assign them to the members of its subaccounts.



<a name="loioede5f721e78e4d678c87c8a200c564ca__prereq_gdt_dr2_5db"/>

## Prerequisites

You have the Administrator role for the subaccount.



## Context

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/docs/btp/sap-business-technology-platform/sap-business-technology-platform?version=Cloud) .**



## Procedure

1.  Choose *Platform Roles* in the navigation area for the subaccount for which you'd like to manage custom platform roles.

    All custom and predefined platform roles available for the subaccount are shown in a list.

2.  You have the following options:

    -   Create, edit, and delete custom platform roles.
    -   Create a copy of an existing custom platform role and make changes to your copy.
    -   View custom and predefined platform role details, including the scopes assigned to it, in read-only mode.

        > ### Note:  
        > You cannot change or delete a predefined platform role, but you can copy from it and make changes to the copy.

    -   Use the search function:
        -   You can search for all the elements in the list of platform roles and restrict it to the entries you are interested in.

        -   In the Create, Copy, and the Edit dialogs, find the scopes that you want to combine into the custom platform role quickly.



3.  To create a custom platform role, choose *New Platform Role*.

    1.  Enter an ID \(mandatory\), display name, and a description.

    2.  Select the platform scopes and save your changes.


4.  To create a custom or a predefined platform role by copying from an existing one, choose <span class="SAP-icons-V5"></span> \(Copy\) and proceed as in the previous step. The scopes from the original role are selected by default.

5.  To edit a custom platform role, choose :pencil2:.

6.  To view platform role details, including the scopes assigned to it, in read-only mode, choose :eyeglasses:.

7.  To delete a custom platform role, choose :wastebasket:.

8.  To assign a custom platform role to a member, perform the steps described in [Add Members to Your Neo Subaccount](add-members-to-your-neo-subaccount-a253570.md).


**Related Information**  


[Platform Scopes](platform-scopes-f226074.md "")

[Managing Member Authorizations in the Neo Environment](managing-member-authorizations-in-the-neo-environment-a1ab5c4.md "SAP BTP includes predefined platform roles that support the typical tasks performed by users when interacting with the platform. In addition, subaccount administrators can combine various scopes into a custom platform role that addresses their individual requirements.")

