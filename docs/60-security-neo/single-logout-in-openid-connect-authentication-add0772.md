<!-- loioadd07725e5bf4811a60e8b88e5fc8b1d -->

# Single Logout in OpenID Connect Authentication

Configuring Single Logout in OpenID Connect Authentication for SAP BTP Neo OIDC Application. Use it to ensure seamless logout functionality for all applications deployed on NEO SAP BTP in the tenant, by following the specific steps for configuring SLO URIs in the IAS tenant Admin console.



<a name="loioadd07725e5bf4811a60e8b88e5fc8b1d__prereq_bby_5ln_xbc"/>

## Prerequisites

-   You have administrative rights in the configure IAS tenant.
-   You have a working application with which is using OIDC Authentication Flow.\(The name of the application should be the following: SAP BTP Neo OIDC Application - <subAccount\> \(The name of the subaccount should be the name where the application is depolyed\)\).



## Context

In order for SLO to work with custom tenant, a mandatory configuration has to be created inside the configured for OIDC Authentication Flow IAS Subaccount application, otherwise it won't work by default. There a specific URLs have to be configured that will corespond with logout URLs on all of the applications deployed on NEO SAP BTP in this tenant.



## Procedure

1.  Navigate to the configured IAS tenant Admin console.

2.  From the Applications & Resources dropdown menu, navigate to Applications.

3.  From the list of Applications select the application for which you want to configure SLO URIs.

4.  On the right click on the OpenID Connect Configuration.

5.  From here you can add the following URIs:

    1.  Redirect URIs - For more information regarding usage of Redirect URIs please check the following section \(Link to Redirect URIs Section\)

    2.  Front-Channel Logout URIs - These URIs are where the service will trigger logout when session ends.

    3.  Back-Channel Logout URIs - At the moment of writing this documentation, we do not support Back-Channel Logout URLs.

    4.  Post Logout Redirect URIs - For more information regarding the usage of these URIs, please check the following section \(Link to Redirect URIs Section\)


6.  Click on the save button in the top right corner.


