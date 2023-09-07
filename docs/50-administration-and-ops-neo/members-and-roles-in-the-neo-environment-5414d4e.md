<!-- loio5414d4e295ef48f88c35de15e6498ede -->

# Members and Roles in the Neo Environment

A member is a user who is assigned to an SAP BTP global account or subaccount. A member automatically has the permissions required to use the SAP BTP functionality within the scope of the respective accounts and as permitted by their account member roles.

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**



<a name="loio5414d4e295ef48f88c35de15e6498ede__section_j4w_qfc_t3b"/>

## Roles

Roles determine which functions in the cockpit users can view and access, and which actions they can initiate.

Roles support typical tasks performed by users when interacting with the cloud platform, for example, adding and removing users. A user can be assigned one or more roles, where each role comes with a set of permissions. The set of assigned roles defines what functionality is available to the user and what activities he can perform.

The Administrator role in a global account is automatically assigned to the user who has purchased resources for an enterprise account. A global account administrator has permissions to manage all roles in the relevant global account and can assign the Administrator role to other users in the same global account. He can add members to the global account who are then automatically assigned the Administrator role.

On the *Members* page at the global account level in the cockpit, all global account members can view the global account administrators.

Note the following:

-   Users can be assigned to one or more subaccounts and to one or more roles in the relevant subaccount.
-   If the user is assigned to more than one subaccount, an administrator must assign the roles to the user for each subaccount.
-   Roles apply to all operations associated with the subaccount, irrespective of the tool used \(Eclipse-based tools, cockpit, and console client\).
-   As an administrator in the Neo environment, you cannot remove your own administrator role. You can remove any member except yourself.

