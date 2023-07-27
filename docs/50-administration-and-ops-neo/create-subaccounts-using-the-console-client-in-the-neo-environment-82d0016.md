<!-- loio82d001643aa84752a45a966269460436 -->

# Create Subaccounts Using the Console Client in the Neo Environment

You can create subaccounts using the console client in the Neo environment.



<a name="loio82d001643aa84752a45a966269460436__prereq_ubt_44c_bcb"/>

## Prerequisites

-   You have an enterprise account.

-   You must be a member of the global account that contains the subaccount.
-   You work in the Neo environment.

-   You set up the console client. See [Set Up the Console Client](https://help.sap.com/viewer/ea72206b834e4ace9cd834feed6c0e09/Cloud/en-US/7613dee4711e1014839a8273b0e91070.html).

> ### Recommendation:  
> Before creating your subaccounts, we recommend you learn more about [Setting Up Your Account Model](https://help.sap.com/viewer/df50977d8bfa4c9a8a063ddb37113c43/Cloud/en-US/2db81f42f5194454beecde6cd4994dda.html "The hierarchical structure between global accounts, directories, and subaccounts lets you define an account model that accurately fits your business and development needs.") :arrow_upper_right:.



## Context

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://launchpad.support.sap.com/#/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**



<a name="loio82d001643aa84752a45a966269460436__steps_rjp_fgd_bcb"/>

## Procedure

Open a command line and enter the following string:

```
neo create-account --display-name <subaccount_display_name> --account <subaccount_technical_name> --user <e-mail_or_user> --host <host> 
```

**Example:**

```
neo create-account --account mysubaccount --display-name mynewsubaccount --user myuser --host hana.ondemand.com
```

> ### Note:  
> For more information on creating new subaccounts and cloning existing subaccounts using the console client, see [create-account](create-account-05f96cf.md).

