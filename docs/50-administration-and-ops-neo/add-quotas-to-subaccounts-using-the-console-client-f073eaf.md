<!-- loiof073eaf5e6104c90836611322d3397c7 -->

# Add Quotas to Subaccounts Using the Console Client

You can use the Neo console client to add quotas to subaccounts



<a name="loiof073eaf5e6104c90836611322d3397c7__prereq_zs5_h5y_dcb"/>

## Prerequisites

-   An enterprise account.

-   You must be a member of the global account that contains the subaccount.
-   Set up the console client. See [Set Up the Console Client](https://help.sap.com/viewer/ea72206b834e4ace9cd834feed6c0e09/Cloud/en-US/7613dee4711e1014839a8273b0e91070.html).



## Context

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of the following technology portfolios: application development; process automation; integration; data, analytics, and enterprise planning; artificial intelligence. The platform offers users the ability to turn data into business value, compose end-to-end business processes, connect entire IT landscapes, and personalize, build and extend SAP applications. This reduces the overall total cost of ownership maintaining SAP landscapes and third-party software across end-to-end business processes.") :arrow_upper_right:.**



## Procedure

Open a command line and enter the following string:

```
neo set-quota --account <subaccount_technical_name> --host <host> --user <e-mail_or_user> --amount <quota_type>:<integer_amount_of_quota>
```

**Example:**

```
neo set-quota --account mysubaccount --user myuser --host eu1.hana.ondemand.com --amount lite:2
```

> ### Note:  
> For more information on adding quotas to subaccounts using the console client, see [set-quota](https://help.sap.com/viewer/ea72206b834e4ace9cd834feed6c0e09/Cloud/en-US/4108f0f0680446a39db27f624c0e8b6a.html).

