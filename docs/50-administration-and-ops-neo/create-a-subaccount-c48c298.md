<!-- copyc48c2985de5a4fa692f03b7ee3f563b2 -->

# Create a Subaccount

Create subaccounts in your global account using the SAP BTP cockpit.

<a name="task_pdx_hmd_cqb"/>

<!-- task\_pdx\_hmd\_cqb -->

## Create a Subaccount \[Feature Set A\]



<a name="task_pdx_hmd_cqb__prereq_eds_lmd_cqb"/>

## Prerequisites

You are a global account administrator.

> ### Recommendation:  
> Before creating your subaccounts, we recommend you learn more about [Setting Up Your Account Model](https://help.sap.com/viewer/df50977d8bfa4c9a8a063ddb37113c43/Cloud/en-US/2db81f42f5194454beecde6cd4994dda.html "The hierarchical structure between global accounts, directories, and subaccounts lets you define an account model that accurately fits your business and development needs.") :arrow_upper_right:.



<a name="task_pdx_hmd_cqb__context_fds_lmd_cqb"/>

## Context

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**

You create subaccounts in your global account. Once you create a new subaccount, you see a tile for it in the global account view, and you are automatically assigned to it as an administrator.



<a name="task_pdx_hmd_cqb__steps_gds_lmd_cqb"/>

## Procedure

1.  From your global account, choose *New Subaccount*.

2.  Specify a display name.

3.  **Optional:** Enter a description.

4.  Select the *Neo Environment* checkbox.

5.  Choose the desired infrastructure provider and region for your subaccount.

6.  Enter a subdomain for your subaccount. This will become part of the URL for accessing applications that you subscribe to from this subaccount.

    > ### Note:  
    > The subdomain can contain only letters, digits and hyphens \(not allowed in the beginning or at the end\), and must be unique across all subaccounts in the same region. Uppercase and lowercase letters can be used, however that alone does not qualify as a means to differentiate subdomains \(e.g. `SUBDOMAIN` and `subdomain` are considered to be the same\).
    > 
    > The subdomain can't be changed once you have created the subaccount.

7.  **Optional:** If your subaccount is to be used for production purposes, select the *Used for production* option.

    > ### Note:  
    > This does not change the configuration of your subaccount. Use this flag for your internal use to operate your production subaccounts in your global account and systems more efficiently. Your cloud operator may also use this flag to take appropriate action when handling incidents related to mission-critical accounts in production systems.
    > 
    > You can change your selection at any time by editing the subaccount properties. Do not select this option if your account is used for non-production purposes, such as development, testing, and demos.

8.  **Optional:** To use beta services and applications in the current subaccount, select *Enable beta features*.

    > ### Caution:  
    > You shouldn't use SAP BTP beta features in subaccounts that belong to productive enterprise accounts. For more information, see [Important Disclaimers and Legal Information](https://help.sap.com/viewer/disclaimer).

    > ### Note:  
    > Once you have enabled this setting in a subaccount you cannot disable it.

9.  Save your changes.




<a name="task_pdx_hmd_cqb__result_hds_lmd_cqb"/>

## Results

A new tile appears in the global account page with the subaccount details.



<a name="task_pdx_hmd_cqb__postreq_ids_lmd_cqb"/>

## Next Steps

Once you've created your subaccount, navigate to it to enable the environment that you wish to use.

<a name="task_dvg_gmd_cqb"/>

<!-- task\_dvg\_gmd\_cqb -->

## Create a Subaccount \[Feature Set B\]



<a name="task_dvg_gmd_cqb__prereq_qcg_tmd_cqb"/>

## Prerequisites

You are a global account administrator.

> ### Recommendation:  
> Before creating your subaccounts, we recommend you learn more about [Setting Up Your Account Model](https://help.sap.com/viewer/df50977d8bfa4c9a8a063ddb37113c43/Cloud/en-US/2db81f42f5194454beecde6cd4994dda.html "The hierarchical structure between global accounts, directories, and subaccounts lets you define an account model that accurately fits your business and development needs.") :arrow_upper_right:.



<a name="task_dvg_gmd_cqb__context_rcg_tmd_cqb"/>

## Context

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**

You create subaccounts in your global account. Once you create a new subaccount, you see a tile for it in the global account view, and you are automatically assigned to it as an administrator.



<a name="task_dvg_gmd_cqb__steps_scg_tmd_cqb"/>

## Procedure

1.  From your global account, navigate to the *Account Explorer* page.

2.  Select *Create* \> *Subaccount*.

3.  Specify a display name.

4.  **Optional:** Enter a description.

5.  Enter a subdomain for your subaccount. This will become part of the URL for accessing applications that you subscribe to from this subaccount.

    > ### Note:  
    > The subdomain can contain up to 63 characters such as letters, digits and hyphens \(not allowed in the beginning or at the end\), and must be unique across all subaccounts in the same region. Uppercase and lowercase letters can be used, however that alone does not qualify as a means to differentiate subdomains \(e.g. `SUBDOMAIN` and `subdomain` are considered to be the same\).

6.  Choose the desired region for your subaccount.

7.  Select a parent for your subaccount. The parent can either be the global account or a directory.

8.  If your subaccount is to be used for production purposes, select the *Used for production* option.

    > ### Note:  
    > This does not change the configuration of your subaccount. Use this flag for your internal use to operate your production subaccounts in your global account and systems more efficiently. Your cloud operator may also use this flag to take appropriate action when handling incidents related to mission-critical accounts in production systems.
    > 
    > You can change your selection at any time by editing the subaccount properties. Do not select this option if your account is used for non-production purposes, such as development, testing, and demos.

9.  **Optional:** To use beta services and applications in the current subaccount, under *Advanced*, select *Enable beta features*.

    > ### Caution:  
    > You shouldn't use SAP BTP beta features in subaccounts that belong to productive enterprise accounts. For more information, see [Important Disclaimers and Legal Information](https://help.sap.com/viewer/disclaimer).

    > ### Note:  
    > Once you have enabled this setting in a subaccount you cannot disable it.

10. **Optional:** Under *Advanced* \> *Labels*, assign labels to the subaccount to make organizing and filtering your subaccounts easier. For more information, see [Labels \[Feature Set B\]](../10-concepts-neo/account-model-722a475.md#loioe8663c08ead648faa673b0d63c5b478e).

    > ### Tip:  
    > -   When adding multiple values to a label, press [Enter\] after each value.
    > -   When you start typing, any matching label names and values that are already assigned to other subaccounts in your global account are offered as suggestions.

11. Save your changes.




<a name="task_dvg_gmd_cqb__result_tcg_tmd_cqb"/>

## Results

A new tile appears in the global account page with the subaccount details.



<a name="task_dvg_gmd_cqb__postreq_ucg_tmd_cqb"/>

## Next Steps

Once you've created your subaccount, navigate to it to enable the environment that you wish to use.

**Related Information**  


[Cloud Management Tools — Feature Set Overview](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/caf4e4e23aef4666ad8f125af393dfb2.html "Cloud management tools represent the group of technologies designed for managing SAP BTP.") :arrow_upper_right:

[Global Accounts](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/8ed4a705efa0431b910056c0acdbf377.html#loioc165d95ee700407eb181770901caec94 "A global account is the realization of a contract you or your company has made with SAP.") :arrow_upper_right:

[Navigate in the Cockpit](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/0874895f1f78459f9517da55a11ffebd.html "Learn how to navigate to your global accounts and subaccounts in the SAP BTP cockpit.") :arrow_upper_right:

[Account Model](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/8ed4a705efa0431b910056c0acdbf377.html#loio8ed4a705efa0431b910056c0acdbf377 "Learn more about the different types of accounts on SAP BTP and how they relate to each other.") :arrow_upper_right:

