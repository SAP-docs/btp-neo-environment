<!-- copy9c29bddd479949c2bb9cb3c5ad597f96 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Change the Display Name of Your Global Account

Change the display name for the global account using the SAP BTP cockpit.



<a name="copy9c29bddd479949c2bb9cb3c5ad597f96__context_a3l_2rb_r1b"/>

## Context

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**

> ### Tip:  
> To find out how to tell which cloud management tools feature set your global account uses, see [Cloud Management Tools — Feature Set Overview](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/caf4e4e23aef4666ad8f125af393dfb2.html "Cloud management tools represent the group of technologies designed for managing SAP BTP.") :arrow_upper_right:.

<a name="task_af5_xsw_2qb"/>

<!-- task\_af5\_xsw\_2qb -->

## Changing the global account name



<a name="task_af5_xsw_2qb__prereq_sf1_vtw_2qb"/>

## Prerequisites

You are a member of the global account that you'd like to edit.



<a name="task_af5_xsw_2qb__context_tf1_vtw_2qb"/>

## Context

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**

The overview of global accounts available to you is your starting point for viewing and changing global account details in the cockpit. To view or change the display name for a global account, trigger the intended action directly from the tile for the relevant global account.



<a name="task_af5_xsw_2qb__steps_uf1_vtw_2qb"/>

## Procedure

1.  Choose the global account for which you'd like to change the display name and choose ![](images/Edit_Icon_abfe424.png) on its tile.

    A new dialog shows up with the mandatory *Display Name* field that is to be changed.

2.  Enter the new human-readable name for the global account.

3.  Save your changes.


<a name="task_o14_g5w_2qb"/>

<!-- task\_o14\_g5w\_2qb -->

## Changing the global account name



<a name="task_o14_g5w_2qb__prereq_p14_g5w_2qb"/>

## Prerequisites

You are an admin of the global account that you'd like to edit.



<a name="task_o14_g5w_2qb__context_q14_g5w_2qb"/>

## Context

> ### Tip:  
> You can also change the account's display name using the SAP BTP command line interface \(btp CLI\) with the `btp update accounts/global-account` command. See [Account Administration Using the SAP BTP Command Line Interface \(btp CLI\)](account-administration-using-the-sap-btp-command-line-interface-btp-cli-7c6df2d.md).



<a name="task_o14_g5w_2qb__steps_r14_g5w_2qb"/>

## Procedure

1.  Open your global account in the SAP BTP cockpit.

2.  Navigate to the *Account Explorer* page.

3.  In the *Directories & Subaccounts* view, locate the first entry in your account structure, which is your global account, and click <span class="SAP-icons"></span> Actions. Then select *Edit*.

4.  In the *Edit Global Account* dialog box, enter the new human-readable name for the global account.

5.  Save your changes.


**Related Information**  


[Account Model](../10-concepts-neo/account-model-722a475.md#copy722a4755da7f4b7e9929be8f15af0f1b "Learn more about the different types of accounts on SAP BTP and how they relate to each other.")

