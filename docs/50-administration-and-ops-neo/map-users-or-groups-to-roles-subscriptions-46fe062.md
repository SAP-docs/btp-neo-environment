<!-- loio46fe062843504031a7ef9a196a1862d4 -->

# Map Users or Groups to Roles \(Subscriptions\)

You assign a role to users or a group of users.



## Prerequisites

-   If you want to use groups, you have configured the groups for your identity provider as described in [Application Identity Provider](../60-security-neo/application-identity-provider-dc61853.md#loiodc618538d97610148155d97dcd123c24).



## Context

> ### Caution:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/docs/btp/sap-business-technology-platform/sap-business-technology-platform?version=Cloud) .**

> ### Tip:  
> Additional IP outbound addresses will soon be used in all regions in the Neo environment. For more information, see [Additional IP Addresses Added to SAP BTP, Neo Runtime Regions](https://help.sap.com/whats-new/cf0cb2cb149647329b5d02aa96303f56?version=Cloud&Component=Region&Valid_as_Of=2026-11-02:2026-11-02). To subscribe to such notifications, see SAP Note [3513325](https://me.sap.com/notes/3513325).

Since all HTML5 applications and all HTML5 application subscriptions use the same roles, changing a role affects all applications that use this role.



## Procedure

1.  In the cockpit, choose *Applications* \> *Subscriptions* in the navigation area.

2.  From the list of subscribed HMTL5 applications, select any subscription.

3.  Choose *Roles* in the navigation area.

4.  Select the role for which you want to manage assignments.

5.  To assign a new user or group, choose *Assign* from the users or groups section respectively.

6.  Enter the name of the user or group, and choose *Assign*.


