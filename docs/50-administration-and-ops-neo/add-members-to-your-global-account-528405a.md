<!-- copy528405a0e2bb411b88baa91868bf9c54 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Add Members to Your Global Account

Add users as global account members using the SAP BTP cockpit.



<a name="copy528405a0e2bb411b88baa91868bf9c54__prereq_hdd_wd2_nbb"/>

## Prerequisites

You have the Administrator role in the global account.



## Context

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://launchpad.support.sap.com/#/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**



<a name="copy528405a0e2bb411b88baa91868bf9c54__steps_igf_mlf_knb"/>

## Procedure

1.  Find out which cloud management tools feature set your global account uses. For more information, see [Cloud Management Tools — Feature Set Overview](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/caf4e4e23aef4666ad8f125af393dfb2.html "Cloud management tools represent the group of technologies designed for managing SAP BTP.") :arrow_upper_right:.

2.  Learn how to add members to your global account.

    -   [Add Members to Your Global Account \[Feature Set A\]](add-members-to-your-global-account-528405a.md#copy528405a0e2bb411b88baa91868bf9c54__AddMembers-FSA) 
    -   [Add Members to Your Global Account \[Feature Set B\]](add-members-to-your-global-account-528405a.md#copy528405a0e2bb411b88baa91868bf9c54__AddMembers-FSB)


**Related Information**  


[Cloud Management Tools — Feature Set Overview](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/caf4e4e23aef4666ad8f125af393dfb2.html "Cloud management tools represent the group of technologies designed for managing SAP BTP.") :arrow_upper_right:

[User and Member Management](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/cc1c676b43904066abb2a4838cbd0c37.html "On SAP BTP, member management happens at all levels from global account to environment, while user management is done for business applications.") :arrow_upper_right:

<a name="AddMembers-FSA"/>

<!-- AddMembers-FSA -->

## Add Members to Your Global Account \[Feature Set A\]

Add users as global account members using the SAP BTP cockpit.



<a name="AddMembers-FSA__context_qpw_tkf_knb"/>

## Context

The users you add as members at global account level are automatically assigned the Administrator role.

All global account administrators can do the following:

-   View all the subaccounts in the global account, meaning all the subaccount tiles in the global account's *Subaccounts* page.
-   Edit general properties of the subaccounts in the global account from the *Edit* icon in the subaccount tile.
-   Create a new subaccount in the global account.
-   View, add, and remove global account members.
-   Manage entitlements for the global account.

By default, the cockpit and console client are configured to use SAP ID Service, which uses the SAP user base, as an identity provider for user authentication. If you want to use a custom user base and custom Identity Authentication tenant settings, see [Platform Identity Provider](../60-security-neo/platform-identity-provider-80edbe7.md).

On the *Members* page at the global account level in the cockpit, all global account members can view the global account administrators. If you're a subaccount member, you're also a member of the global account.



<a name="AddMembers-FSA__steps_spw_tkf_knb"/>

## Procedure

1.  Choose the global account to which you'd like to add members.

2.  In the navigation area, choose *Members*.

3.  Choose *Add Members*.

    If you want to use a custom user base, choose *Other* for *User Base* and then enter the corresponding Identity Authentication tenant name. For more information, see [Platform Identity Provider](../60-security-neo/platform-identity-provider-80edbe7.md).

4.  Enter up to 100 user IDs. To separate them, you can use commas, spaces, semicolons, or line breaks.

5.  Choose *Add Members*.




<a name="AddMembers-FSA__postreq_tpw_tkf_knb"/>

## Next Steps

To delete members at global account level, choose :wastebasket: next to the user's ID.

<a name="AddMembers-FSB"/>

<!-- AddMembers-FSB -->

## Add Members to Your Global Account \[Feature Set B\]

Add members to your global account by assigning them a role collection.



<a name="AddMembers-FSB__prereq_sf4_3hg_klb"/>

## Prerequisites

-   You must be a global account administrator to add other global account members.

-   The users exist in a trusted platform identity provider.

    All users of SAP BTP are stored in identity providers, either in the default or in a custom identity provider. SAP BTP needs a copy of the user, sometimes called a shadow user. You assign the shadow user authorizations to access resources in SAP BTP. When a user authenticates, SAP BTP forwards the request to the identity provider.

    For more information, see [Trust and Federation with Identity Providers](https://help.sap.com/viewer/ae8e8427ecdf407790d96dad93b5f723/Cloud/en-US/cb1bc8f1bd5c482e891063960d7acd78.html "When setting up accounts you need to assign users. While we provide you with your first users to get you started, your organization has identity providers that you want to integrate.") :arrow_upper_right:.




<a name="AddMembers-FSB__context_gr5_5kf_knb"/>

## Context

Assign predefined or custom role collections to users who need to manage or view the global account in SAP BTP cockpit. Examples of predefined role collections include the following:

-   *Global Account Administrator*

-   *Global Account Viewer*


For more information about these role collections, see [Role Collections and Roles in Global Accounts, Directories, and Subaccounts [Feature Set B]](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/0039cf082d3d43eba9200fe15647922a.html "In the cloud management tools feature set B, SAP BTP provides a set of role collections to set up administrator access to your global account and subaccounts.") :arrow_upper_right:.



<a name="AddMembers-FSB__steps_vqz_cjg_klb"/>

## Procedure

1.  Navigate to your global account.

2.  Add a user to your global account.

    For more information, see [Create Users](https://help.sap.com/viewer/ae8e8427ecdf407790d96dad93b5f723/Cloud/en-US/a3bc7e863ac54c23ab856863b681c9f8.html "As an administrator, you can create shadow users in your subaccount. When you create a shadow user, you must know and specify which identity provider stores the user.") :arrow_upper_right:.

3.  Assign a role collection to the user.

    For more information, see [Assign Users to Role Collections](https://help.sap.com/viewer/ae8e8427ecdf407790d96dad93b5f723/Cloud/en-US/c5766765bda74ad59fe656977c8fa4d6.html "You can assign users to a role collection by adding them to the role collection.") :arrow_upper_right:.




<a name="AddMembers-FSB__result_syg_v3g_klb"/>

## Results

The next time this user logs on to the SAP BTP cockpit, the user can access this global account.

