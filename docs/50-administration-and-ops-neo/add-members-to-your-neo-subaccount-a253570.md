<!-- loioa253570f081e448d9f78fc2bfeedfdc3 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Add Members to Your Neo Subaccount

Add users as members to a subaccount in the Neo environment and assign roles to them using the SAP BTP cockpit.



<a name="loioa253570f081e448d9f78fc2bfeedfdc3__prereq_bzj_4dy_dcb"/>

## Prerequisites

-   You have an enterprise account.
-   You have the Administrator role for the subaccount.
-   You have the user IDs of the members that you want to add.

    > ### Tip:  
    > *User Management* application: [1271482](https://me.sap.com/notes/1271482).




## Context

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of the following technology portfolios: application development; process automation; integration; data, analytics, and enterprise planning; artificial intelligence. The platform offers users the ability to turn data into business value, compose end-to-end business processes, connect entire IT landscapes, and personalize, build and extend SAP applications. This reduces the overall total cost of ownership maintaining SAP landscapes and third-party software across end-to-end business processes.") :arrow_upper_right:.**

In the Neo environment, you can assign predefined roles to subaccount members, but you can also create custom platform roles. For more information, see [Manage Custom Platform Roles](manage-custom-platform-roles-ede5f72.md). Administrators can request S-user IDs on the SAP ONE Support Launchpad [Managing Member Authorizations in the Neo Environment](managing-member-authorizations-in-the-neo-environment-a1ab5c4.md).



## Procedure

> ### Tip:  
> If you're a global account administrator, you can quickly assign yourself as an administrator of a subaccount by going to the *Account Explorer* page and then choosing the *Add Me as Admin* option in the *Actions* \(<span class="SAP-icons-V5"></span>\) context menu of the subaccount. To assign other users, follow the instructions below.
> 
> This feature may not be available if it has been disabled for your global account.
> 
> To disable this feature, send an opt-out request using the component BC-NEO-CIS-OPS. See [Getting Support](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/5dd739823b824b539eee47b7860a00be.html "To get help, use the available support channels provided by SAP for Me.") :arrow_upper_right: for information about opening a case and getting technical assistance.

1.  Choose the subaccount to which you'd like to add members.

2.  In the navigation area, choose *Members*.

    Administrators can request S-user IDs on the SAP ONE Support LaunchpadAll members currently assigned to the subaccount are shown in a list.

    > ### Note:  
    > The name of a member is shown only after he or she visits the subaccount for the first time.

3.  Choose *Add Members*.

4.  Enter one or more user IDs, separated by commas, spaces, semicolons, or line breaks.

    There is currently no user validation.

5.  Select the roles for the members and save your changes.




<a name="loioa253570f081e448d9f78fc2bfeedfdc3__postreq_qpy_qm1_4db"/>

## Next Steps

-   To select or unselect roles for a member, choose ![](images/Edit_Icon_abfe424.png) \(Edit\). The changes you make to the member's roles take effect immediately.
-   You can enter a comment when editing user roles. This lets you track the reasons for subaccount membership and other important data. The comments are visible to all members.
-   You can send an e-mail to a member. This option appears only after the recipient visits the subaccount for the first time.
-   To remove all the roles of a member, choose *Delete* \(trashcan\). This also removes the member from the subaccount.
-   Choose the *History* button to view a list of changes to members \(for example, added or removed members, or changed role assignments\).
-   Use the filter to show only the members with the role you've selected.

**Related Information**  


[Managing Member Authorizations in the Neo Environment](managing-member-authorizations-in-the-neo-environment-a1ab5c4.md "SAP BTP includes predefined platform roles that support the typical tasks performed by users when interacting with the platform. In addition, subaccount administrators can combine various scopes into a custom platform role that addresses their individual requirements.")

