<!-- copy302dcf474b4e464daef82f11c92932ff -->

# Using Multiple Subaccounts for Staged Application Development

SAP BTP allows you to achieve isolation between the different application life cycle stages \(development, testing, productive\) by using multiple subaccounts.



## Prerequisites

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**

-   You have developed an application. For more information, see [Developing Java Applications](../30-development-neo/developing-java-applications-ac36e1f.md).
-   You have a subaccount in an enterprise account. For more information, see [Global Accounts](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/8ed4a705efa0431b910056c0acdbf377.html#loioc165d95ee700407eb181770901caec94 "A global account is the realization of a contract you or your company has made with SAP.") :arrow_upper_right:.



## Context

Using multiple subaccounts ensures better stability. Also, you can achieve better security for productive applications because permissions are given per subaccount.

For example, you can create three different subaccounts for one application and assign the necessary amount of compute unit quota to them:

-   **dev** - use for development purposes and for testing the increments in the cloud, you can grant permissions to all application developers
-   **test** - use for testing the developed application and its critical configurations to ensure quality delivery \(integration testing and testing in productive-like environment prior to making it publicly available\)
-   **prod** - use to run productive applications, give permissions only to operators.

You can create multiple subaccounts and assign quota to them either using the console client or the cockpit.

<a name="task_atw_dlx_xl"/>

<!-- task\_atw\_dlx\_xl -->

## Create Multiple Subaccounts from the Cockpit



<a name="task_atw_dlx_xl__steps_skq_flx_xl"/>

## Procedure

1.  Open the cockpit and navigate to your global account.

2.  Choose *New Subaccount* and specify a display name.

3.  Use the "+" and "-" buttons next to quota types to set the desired amount of quota and choose the *Save* button.

    Next, you can deploy your application in the newly created subaccount using the Eclipse IDE or the console client. Then, you can test your application and make it ready for productive use.

    You can transfer the application from one subaccount to another by redeploying it in the respective subaccount.


<a name="task_rpm_wlx_xl"/>

<!-- task\_rpm\_wlx\_xl -->

## Create Multiple Subaccounts with the Console Client



<a name="task_rpm_wlx_xl__steps_xwr_xlx_xl"/>

## Procedure

1.  Open the command prompt and navigate to the folder containing `neo.bat/sh (<SDK installation folder>/tools)`.

2.  Create a new subaccount.

    Execute:

    `neo create-account -a <subaccount> -u <user who is member of that subaccount> -h <host> -n <display name of the new subaccount>`

3.  Assign the necessary amount of quota to the subaccount.

    Execute:

    `neo set-quota -a <subaccount> -u <user name or email> -h <host> -m <type of the quota lite, pro, prem or prem-plus>:<integer amount of the quota>`

    Next, you can deploy your application in the newly created subaccount by executing `neo deploy -a <subaccount> -h <host> -b <application name> -s <file location> -u <user name or email>`. Then, you can test your application and make it ready for productive use.

    You can transfer the application from one subaccount to another by redeploying it in the respective subaccount.


**Related Information**  


[Org Administration Using the Cockpit](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/c4c25cc63ac845779f76202360f98694.html "In the Cloud Foundry enviroment, manage orgs, spaces and space quota plans using the SAP BTP cockpit.") :arrow_upper_right:

[Deploying and Updating Java Applications](../30-development-neo/deploying-and-updating-java-applications-e5dfbc6.md "The Java application lifecycle management (Java ALM) service for SAP BTP lets you deploy and update Java applications via console client commands, the SAP BTP cockpit, or the Java ALM REST API.")

[create-account](create-account-05f96cf.md "Creates a new subaccount with an automatically generated unique ID as subaccount technical name and the specified display name and assigns the user as a subaccount owner. The user is authorized against the existing subaccount passed as --account parameter. Optionally, you can clone an existing subaccount configuration to save time and effort.")

[delete-account](delete-account-8bd9552.md "Deletes a particular subaccount. Only the user who has created the subaccount is allowed to delete it.")

[list-accounts](list-accounts-2abad16.md "Lists all subaccounts that a customer has. Authorization is performed against the subaccount passed as --account parameter.")

[set-quota](set-quota-4108f0f.md "Sets compute unit quotas for a given subaccount.")

