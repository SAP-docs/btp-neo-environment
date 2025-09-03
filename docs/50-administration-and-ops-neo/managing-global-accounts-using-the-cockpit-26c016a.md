<!-- copy26c016aea03d4b8dbcdd4055c23c70ef -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Managing Global Accounts Using the Cockpit

Your SAP BTP global account is the entry point for managing the resources, landscape, and entitlements for your departments and projects in a self-service manner.

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/docs/btp/sap-business-technology-platform/sap-business-technology-platform?version=Cloud) .**



<a name="copy26c016aea03d4b8dbcdd4055c23c70ef__section_mr1_jjq_lnb"/>

## Global Account Settings

As a global account administrator, you can access the global account settings by clicking :gear: in the SAP BTP cockpit.

In the *General* tab of the global account settings, you can obtain general information about your global account, including your global account ID, global account name, account type, payment models, contract status, global account subdomain, geographic access restrictions, and when your account was created.

> ### Note:  
> In this tab, you cannot change any of the values. The only value that you can edit is the global account name, and you can do this in the *Account Explorer* page \(see [Change the Display Name of Your Global Account](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/36a6674cf7184907aca3f062f83588e8.html "Change the display name for the global account using the SAP BTP cockpit.") :arrow_upper_right:\).

In the *Subaccounts* tab in the global account settings, you can

-   Define default settings that are used when creating a new subaccount in this global account.

    You can set the supported providers, the default provider, and the default region.

-   Set the option to enable the force deletion of subaccounts.

    If this option is selected, all global account admins can force delete subaccounts that are not marked as "used for production". The force deletion of a subaccount permanently deletes all its data, including applications, service instances, spaces, active subscriptions, and members. The force deletion is permanent and irreversible. This option also enables the force deletion of subaccounts using the btp CLI or the SAP Cloud Management APIs. Subaccounts that are marked as "used for production" cannot be force deleted.


**Related Information**  


[Setting Up Your Account Model](https://help.sap.com/viewer/df50977d8bfa4c9a8a063ddb37113c43/Cloud/en-US/2db81f42f5194454beecde6cd4994dda.html "Learn how to set up your account model with global accounts and subaccounts, and how to use directories, spaces and namespaces to match your business and development needs.") :arrow_upper_right:

[Managing Directories Using the Cockpit](managing-directories-using-the-cockpit-f495ac1.md "Learn how to organize and manage your subaccounts according to your technical and business needs by using directories in the SAP BTP cockpit.")

[Managing Subaccounts Using the Cockpit](managing-subaccounts-using-the-cockpit-55d0b6d.md "Learn how to structure a global account according to your organization’s and project’s requirements with regard to members, authorizations, and entitlements by managing subaccounts.")

