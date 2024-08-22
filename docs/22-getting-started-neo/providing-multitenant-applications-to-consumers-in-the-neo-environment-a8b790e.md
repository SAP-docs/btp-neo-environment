<!-- loioa8b790ee12f14468931e7e955c8d4b0a -->

# Providing Multitenant Applications to Consumers in the Neo Environment

In the Neo environment, you can develop and run multitenant \(tenant-aware\) applications that you can make available to multiple consumers.

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of the following technology portfolios: application development; process automation; integration; data, analytics, and enterprise planning; artificial intelligence. The platform offers users the ability to turn data into business value, compose end-to-end business processes, connect entire IT landscapes, and personalize, build and extend SAP applications. This reduces the overall total cost of ownership maintaining SAP landscapes and third-party software across end-to-end business processes.") :arrow_upper_right:.**



<a name="loioa8b790ee12f14468931e7e955c8d4b0a__section_abj_n5r_3cb"/>

## Developing and Deploying Multitenant Applications

For detailed instructions on developing multitenant applications, see [Developing Multitenant Applications in the Neo Environment](../30-development-neo/developing-multitenant-applications-in-the-neo-environment-54a7615.md).



<a name="loioa8b790ee12f14468931e7e955c8d4b0a__section_ngt_m5r_3cb"/>

## List Java Subscriptions Using the Console Client

**Prerequisites**

-   An enterprise account. For more information, see [Global Accounts](../10-concepts-neo/account-model-722a475.md#loio9b7d44f92eec44a6ae87129c02aeec0d).

-   Develop and deploy an application in the Neo environment for multiple consumers. For more information, see [Developing Multitenant Applications in the Neo Environment](../30-development-neo/developing-multitenant-applications-in-the-neo-environment-54a7615.md).

-   Provider and consumer subaccounts that belong to the same region. For more information, see [Regions and Hosts Available for the Neo Environment](../10-concepts-neo/regions-and-hosts-available-for-the-neo-environment-d722f7c.md).

-   Set up the console client. For more information, see [Set Up the Console Client](../30-development-neo/set-up-the-console-client-7613dee.md).


To list all subaccounts subscribed to a Java application, use the `list-subscribed-accounts` command.

> ### Example:  
> ```
> neo list-subscribed-accounts --account mysubaccount --application demo --user myuser --host us1.hana.ondemand.com
> ```

