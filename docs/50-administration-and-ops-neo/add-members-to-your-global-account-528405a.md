<!-- copy528405a0e2bb411b88baa91868bf9c54 -->

# Add Members to Your Global Account

Add users as global account members using the SAP BTP cockpit.



<a name="copy528405a0e2bb411b88baa91868bf9c54__prereq_ukv_qjz_ncc"/>

## Prerequisites

-   You must be a global account administrator to add other global account members.

    If you don't have a global account administrator or one isn't available, there is a workaround using SAP for Me.

    For more information, see [2669325 - How to add a user as a Global Account administrator for SAP Business Technology Platform](https://me.sap.com/notes/0002669325).

-   The users exist in a trusted platform identity provider.

    All users of SAP BTP are stored in identity providers, either in the default or in a custom identity provider. SAP BTP needs a copy of the user, sometimes called a shadow user. You assign the shadow user authorizations to access resources in SAP BTP. When a user authenticates, SAP BTP forwards the request to the identity provider.

    For more information, see [Trust and Federation with Identity Providers](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/cb1bc8f1bd5c482e891063960d7acd78.html "") :arrow_upper_right:.




<a name="copy528405a0e2bb411b88baa91868bf9c54__context_dlv_qjz_ncc"/>

## Context

Assign predefined or custom role collections to users who need to manage or view the global account in SAP BTP cockpit. Examples of predefined role collections include the following:

-   *Global Account Administrator*

-   *Global Account Viewer*


For more information about these role collections, see [Role Collections and Roles in Global Accounts, Directories, and Subaccounts](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/0039cf082d3d43eba9200fe15647922a.html "SAP BTP provides a set of role collections to set up administrator access to your global account and subaccounts.") :arrow_upper_right:.



<a name="copy528405a0e2bb411b88baa91868bf9c54__steps_flv_qjz_ncc"/>

## Procedure

1.  Navigate to your global account.

2.  Add a user to your global account.

    For more information, see [Create Users](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/a3bc7e863ac54c23ab856863b681c9f8.html "As an administrator, you can create shadow users in your subaccount. When you create a shadow user, you must know and specify which identity provider stores the user.") :arrow_upper_right:.

    > ### Note:  
    > If the user is already a user in a subaccount and has logged on to SAP BTP cockpit, SAP BTP adds the user at the global account level automatically, but without any role collections.

3.  Assign a role collection to the user.

    For more information, see [Assign Users to Role Collections](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/c5766765bda74ad59fe656977c8fa4d6.html "You can assign users to a role collection by adding them to the role collection.") :arrow_upper_right:.




<a name="copy528405a0e2bb411b88baa91868bf9c54__result_glv_qjz_ncc"/>

## Results

The next time this user logs on to the SAP BTP cockpit, the user can access this global account.

**Related Information**  


[User and Member Management](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/cc1c676b43904066abb2a4838cbd0c37.html "On SAP BTP, user management takes place at all levels from global account to environment. There are different types of users, such as depending on their roles in the company.") :arrow_upper_right:

