<!-- loiofa1bd9cf472e46d49472092ffedf7307 -->

# Enable Application Providers to Access Your Subaccount

If your scenario requires it, you can add application providers as members to your SAP BTP subaccount in the Neo environment and assign them the administrator role so that they can deploy and administer the applications you have purchased.



## Prerequisites

-   You have an enterprise account.
-   You have the Administrator role for the subaccount.
-   You have the user ID of the user responsible for deploying and managing the applications you have purchased. You can get this information from your application provider.

    > ### Tip:  
    > You can request user IDs at the SAP Service Marketplace: http://service.sap.com/request-user
    > 
    > SAP Service Marketplace users are automatically registered with the SAP ID service, which controls user access to SAP BTP.




## Context

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/docs/btp/sap-business-technology-platform/sap-business-technology-platform?version=Cloud) .**

As an administrator of a subaccount, you can add members to it and make them administrators of the subaccount using the SAP BTP cockpit. For example, if you have purchased an application from an SAP implementation partner, you may need to enable the partner to deploy and administer the application.



## Procedure

1.  Choose the subaccount to which you'd like to add members.

2.  In the navigation area, choose *Members*.

    All members currently assigned to the subaccount are shown in a list.

3.  Choose *Add Members*.

4.  Enter the user IDs you have received from your application provider, separated by commas, spaces, semicolons, or line breaks.

    User IDs are case-insensitive and can contain alphanumeric characters only. Currently, there is no user validation.

5.  Select the *Administrator* checkbox.

    > ### Note:  
    > By default, the *Developer* option is selected. Do not unselect this checkbox.

6.  Choose *Add Members*.

    Any changes you make take effect immediately. The users are added to the list of team members and are assigned the developer and the administrator role. They can now deploy and administer applications in your subaccount.

    > ### Note:  
    > You cannot remove your own administrator role.

7.  Notify your application provider that they now have the necessary permissions to access the subaccount.


