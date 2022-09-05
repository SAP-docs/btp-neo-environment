<!-- loioff4d4a4caff94b0486b6427eaa8a0b91 -->

# Manage Users in Directories \[Feature Set B\]

Manage members in your directory using the SAP BTP cockpit.



<a name="loioff4d4a4caff94b0486b6427eaa8a0b91__prereq_egz_33d_cqb"/>

## Prerequisites

-   You're a directory administrator.

-   User management is enabled for this directory.

    Choose *Enable User Management* to enable the user management capabilities for this directory if the feature isn't enabled already.

    > ### Note:  
    > Only one directory in a path can manage entitlements or users.

-   Your platform user exists in a trusted identity provider.

    All users of SAP BTP are stored in identity providers, either in the default or in a custom identity provider. SAP BTP needs a copy of the user, sometimes called a shadow user. You assign the shadow user authorizations to access resources in SAP BTP. When a user authenticates, SAP BTP forwards the request to the identity provider.

    For more information, see [Trust and Federation with Identity Providers](https://help.sap.com/viewer/ae8e8427ecdf407790d96dad93b5f723/Cloud/en-US/cb1bc8f1bd5c482e891063960d7acd78.html "When setting up accounts you need to assign users. While we provide you with your first users to get you started, your organization has identity providers that you want to integrate.") :arrow_upper_right:.




<a name="loioff4d4a4caff94b0486b6427eaa8a0b91__context_nw4_4fx_stb"/>

## Context

Assign predefined or custom role collections to users who need to manage or view the directory in SAP BTP cockpit. Examples of predefined role collections include the following:

-   *Directory Administrator*
-   *Directory Viewer*

For more information about these role collections, see [Role Collections and Roles in Global Accounts, Directories, and Subaccounts [Feature Set B]](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/0039cf082d3d43eba9200fe15647922a.html "In the cloud management tools feature set B, SAP BTP provides a set of role collections to set up administrator access to your global account and subaccounts.") :arrow_upper_right:.



## Procedure

1.  Navigate to your directory.

2.  Add a user to your directory.

    For more information, see [Create Users](https://help.sap.com/viewer/ae8e8427ecdf407790d96dad93b5f723/Cloud/en-US/a3bc7e863ac54c23ab856863b681c9f8.html "As an administrator, you can create shadow users in your subaccount. When you create a shadow user, you must know and specify which identity provider stores the user.") :arrow_upper_right:.

3.  Assign a role collection to the user.

    For more information, see [Assign Users to Role Collections](https://help.sap.com/viewer/ae8e8427ecdf407790d96dad93b5f723/Cloud/en-US/c5766765bda74ad59fe656977c8fa4d6.html "You can assign users to a role collection by adding them to the role collection.") :arrow_upper_right:.




<a name="loioff4d4a4caff94b0486b6427eaa8a0b91__result_t5w_zfx_stb"/>

## Results

The next time this user logs on to the SAP BTP cockpit, the user can access this directory.

**Related Information**  


[Working with Users](https://help.sap.com/viewer/ae8e8427ecdf407790d96dad93b5f723/Cloud/en-US/2c91f88e60ea4677a076212085b42d02.html "In the SAP BTP cockpit, you can see the users of your global account or subaccount, user-related identity provider information, and their authorizations. In a user&apos;s overview, you can create and delete users, and assign role collections. You can also display an overview of the role collections, where you can drill down all the way to the role, and see the application that the role is belongs to.") :arrow_upper_right:

[Role Collections and Roles in Global Accounts, Directories, and Subaccounts [Feature Set B]](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/0039cf082d3d43eba9200fe15647922a.html "In the cloud management tools feature set B, SAP BTP provides a set of role collections to set up administrator access to your global account and subaccounts.") :arrow_upper_right:

