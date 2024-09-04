<!-- loioadd07725e5bf4811a60e8b88e5fc8b1d -->

# Single Logout \(SLO\) in OpenID Connect \(OIDC\) Authentication

Configure single logout \(SLO\) in OpenID Connect \(OIDC\) authentication for applications running on SAP BTP, Neo environment. Ensure seamless logout functionality for all applications deployed on this subaccount.



<a name="loioadd07725e5bf4811a60e8b88e5fc8b1d__prereq_bby_5ln_xbc"/>

## Prerequisites

-   You have an Identity Authentication tenant you've configured for OIDC authentication with your Neo subaccount. See [OpenID Connect \(OIDC\) Authentication](openid-connect-oidc-authentication-084c6fb.md).
-   In your Neo subaccount, you have a deployed application using OIDC Authorizaton Code Flow. See [\(Identity Authentication documentation\) Using Authorization Code Flow](https://help.sap.com/docs/identity-authentication/identity-authentication/using-authorization-code-flow?version=Cloud).
-   In your Neo subaccount, you have configured OIDC authentication. See [OpenID Connect \(OIDC\) Authentication](openid-connect-oidc-authentication-084c6fb.md).



## Context

On the Identity Authentication tenant side, you need to configure a set of URIs that will corespond to the logout URIs of the applications deployed in you Neo subaccount.



## Procedure

1.  Open the Administration Console of the Identity Authentication tenant.

2.  In the *Applications & Resources* dropdown menu, navigate to *Applications*.

3.  From the list of applications select the application representing your subaccount's OIDC configuration.

    > ### Tip:  
    > The application created for your subaccount's OIDC configuration has the following name:
    > 
    > `SAP BTP Neo OIDC Application - <subaccount>`

4.  On the right click on the *OpenID Connect Configuration*.

5.  From here you can add the following URIs for SLO with your Neo applications:

    -   `Redirect URIs` - The redirection URIs to which the response can be sent
    -   `Front-Channel Logout URIs` - These URIs are where the service will trigger logout when session ends
    -   `Post Logout Redirect URIs`

    For more information about configuring these URIs, see:

    -   [Configure OpenID Connect Application for Authorization Code Flow](https://help.sap.com/docs/cloud-identity-services/cloud-identity-services/auth-code-configure-openid-connect-application-for-authorization-code-flow) 
    -   [Redirect URIs, Post Logout Redirect URI Rules](https://help.sap.com/docs/cloud-identity-services/cloud-identity-services/redirect-uris-post-logout-redirect-uri-rules)

    > ### Restriction:  
    > `Back-Channel Logout URIs` are not supported for this SLO scenario.

6.  Click the *Save* button in the top right corner.


