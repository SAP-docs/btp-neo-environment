<!-- copyfdeff7e68f64496eb8a1fb31f6a08b73 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Navigate in the Cockpit

Learn how to navigate to your global accounts and subaccounts in the SAP BTP cockpit.



## Context

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**



<a name="copyfdeff7e68f64496eb8a1fb31f6a08b73__steps_hbw_vy2_knb"/>

## Procedure

1.  Find out which cloud management tools feature set your global account uses. For more information, see [Cloud Management Tools — Feature Set Overview](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/caf4e4e23aef4666ad8f125af393dfb2.html "Cloud management tools represent the group of technologies designed for managing SAP BTP.") :arrow_upper_right:.

2.  Become familiar with the navigation behavior in the SAP BTP cockpit.

    -   [Navigate in the Cockpit to Global Accounts and Subaccounts \[Feature Set A\]](navigate-in-the-cockpit-fdeff7e.md#copyfdeff7e68f64496eb8a1fb31f6a08b73__Navigate-FSA)

    -   [Navigate in the Cockpit to Global Accounts and Subaccounts \[Feature Set B\]](navigate-in-the-cockpit-fdeff7e.md#copyfdeff7e68f64496eb8a1fb31f6a08b73__Navigate-FSB)


<a name="Navigate-FSA"/>

<!-- Navigate-FSA -->

## Navigate in the Cockpit to Global Accounts and Subaccounts \[Feature Set A\]



<a name="Navigate-FSA__steps_bhk_my2_knb"/>

## Procedure

1.  Navigate to a global account.

    You can see the following path in the breadcrumbs:

    :house: Home / <span class="SAP-icons"></span> <global\_account\>

2.  Navigate to a subaccount.

    1.  Select the global account that contains the subaccount you'd like to navigate to by following the steps described above.

    2.  Select the subaccount.


    You can see the following path in the breadcrumbs:

    :house: Home / <span class="SAP-icons"></span> <global\_account\> / <span class="SAP-icons"></span> <subaccount\>


<a name="Navigate-FSB"/>

<!-- Navigate-FSB -->

## Navigate to Global Accounts, Directories, and Subaccounts \[Feature Set B\]



<a name="Navigate-FSB__steps_ibv_bhf_mqb"/>

## Procedure

1.  Navigate to a global account.

    -   **You have only one global account:**

        When you log on to the cockpit you’re automatically taken into your global account, to the *Account Explorer* page.

    -   **You have multiple global accounts:**

        When you log on to the cockpit, a dialog opens up containing the list of all global accounts that you’re part of. In this dialog, select the global account you want to navigate to.

        > ### Tip:  
        > If you have one global account you usually navigate to, you can choose *Remember my selection* in the initial dialog. This means you’ll be automatically redirected to your preferred global account after logging on, without seeing the dialog with all the options each time.
        > 
        > If you've chosen a default global account, you can change or remove it anytime. To do so, navigate to the *Account Explorer* page of any global account, choose *Switch Global Account*.
        > 
        > To change it, choose the desired new default global account from the list, select *Save new selection as default global account* and choose *Continue*. Your new default is savedand you’re redirected to that global account.
        > 
        > To delete the default global account and go back to seeing the selection dialog after each logon, simply choose the <span class="SAP-icons"></span> icon next to your default global account name in the dialog and choose *Close*.


    You can see which global account you are in at any time by looking at the first item in the breadcrumbs. It looks like this: :globe_with_meridians: *<global account name\>*

2.  Navigate to a different global account.

    -   Navigate to the *Account Explorer* page at global account level and choose *Switch Global Account*.

    -   Use the dropdown menu next to the :globe_with_meridians: *<global account name\>*.

3.  \(Optional\) Navigate to directories.

    1.  When you enter your global account, you are by default taken to the *Account Explorer* page of that global account. To navigate to a directory, choose the corresponding entry in one of the views in the *Directories & Subaccounts* tab.

        > ### Note:  
        > If a directory has the **user management** capability enabled, then you can access this directory \(or its subdirectories\) only if you are a global account admin or you are assigned as a member of the directory. See [Manage Users in Directories \[Feature Set B\]](manage-users-in-directories-feature-set-b-ff4d4a4.md).
        > 
        > The :lock: icon is shown next to directories that you aren't authorized to access.


4.  Navigate to subaccounts.

    1.  When you enter your global account, you are by default taken to the *Account Explorer* page of that global account. To navigate to a subaccount, choose the corresponding entry from one of the views.

        Once you've entered a subaccount, the breadcrumbs look like this: :globe_with_meridians: *<global account name\> /* <span class="SAP-icons"></span> *<subaccount name\>*

        > ### Note:  
        > To access a subaccount your user must have authorizations in the subaccount tenant.
        > 
        > The :lock: icon is shown next to subaccounts that you aren't authorized to access.



