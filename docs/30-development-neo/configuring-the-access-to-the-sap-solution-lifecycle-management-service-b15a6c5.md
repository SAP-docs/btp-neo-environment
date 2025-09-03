<!-- loiob15a6c5c6c97475f8297f83f83dd4e31 -->

# Configuring the Access to the SAP Solution Lifecycle Management service

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/docs/btp/sap-business-technology-platform/sap-business-technology-platform?version=Cloud) .**

To deploy Multitarget Applications from other tools, such as CTS+ or the Transport Management Service, you have to connect to the SAP Solution Lifecycle Management service for SAP BTP by using its dedicated service endpoint `https://slservice.<landscape-host>/slservice`. You have two authentication methods available - Basic authentication, and OAuth Platform API Client.

> ### Note:  
> The default option for both CTS+ and Transport Management Service is Basic authentication.

The complete URL you have to use is based on the following patterns, respectively:

-   `https://slservice.<landscape-host>/slservice/slp/basic/<subaccount-technical-name>/slp` - authentication using username and password
-   `https://slservice.<landscape-host>/slservice/slp/oauth/<subaccount-technical-name>/slp` - authentication using an OAuth token created using the OAuth client

> ### Caution:  
> OAuth authentication is supported for CPI and Fiori scenario only.

Landscape host can be found at [Regions and Hosts Available for the Neo Environment](../10-concepts-neo/regions-and-hosts-available-for-the-neo-environment-d722f7c.md).

Depending on your chosen method, proceed as follows:

-   Basic authentication:
    1.  Ensure the user has an assigned platform role that contains the following scopes:

        -   *Manage Multitarget Applications*
        -   *Read Multitarget Applications*

        For more information, see section [Managing Member Authorizations in the Neo Environment](../50-administration-and-ops-neo/managing-member-authorizations-in-the-neo-environment-a1ab5c4.md)


-   Authentication using an OAuth Client:
    1.  Create a new OAuth client as described in [Using Platform APIs](using-platform-apis-392af9d.md).
    2.  During the process, assign the following scopes from the SAP Solution Lifecycle Management service API:
        -   *Manage Multitarget Applications*
        -   *Read Multitarget Applications* 



