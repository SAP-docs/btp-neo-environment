<!-- loio084c6fbf9c984a0292183b41120e7cb4 -->

# OpenID Connect Authentication

Protect your applications on SAP BTP, Neo environment with OpenID Connect \(OIDC\) authentication method using an Identity Authentication tenant as an OpenID Connect provider.



<a name="loio084c6fbf9c984a0292183b41120e7cb4__prereq_cb1_fr2_jzb"/>

## Prerequisites

-   You have administrative rights over your subaccount in the Neo environment.
-   You have an Identity Authentication tenant for this subccount. See [\(Identity Authentication documentation\) Initial Setup](https://help.sap.com/docs/identity-authentication/identity-authentication/initial-setup?version=Cloud).
-   You have enabled Beta features for this subaccount. See [Account Model](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/8ed4a705efa0431b910056c0acdbf377.html#loio8ed4a705efa0431b910056c0acdbf377 "Learn more about the different types of accounts on SAP BTP and how they relate to each other.") :arrow_upper_right: \(subsection *Using Beta Features with Subaccounts*\).



## Context

> ### Note:  
> This is a beta feature. Beta features aren't part of the officially delivered scope that SAP guarantees for future releases. For more information, see [Important Disclaimers and Legal Information](https://help.sap.com/viewer/disclaimer).

With the OpenID Connect authentication method, the Identity Authentication tenant is used as an OpenID Connect provider. Your application's users will authenticate using the credentials defined and verified by the Identity Authentication tenant \(by default, this is a user name/e-mail address and password pair but you can configure your tenant to use others\).

> ### Note:  
> We support the *Authorization Code* flow of the OpenID Connect protocol. For more information about this scenario with Identity Authentication service, see [\(Identity Authentication documentation\) Using Authorization Code Flow](https://help.sap.com/docs/identity-authentication/identity-authentication/using-authorization-code-flow?version=Cloud).

General information about OpenID Connect supported by Identity Authentication service: [\(Identity Authentication documentation\) OpenID Connect](https://help.sap.com/docs/identity-authentication/identity-authentication/openid-connect?version=Cloud).



## Procedure

1.  In the SAP BTP cockpit, navigate to your subaccount. See [Navigate in the Cockpit](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/0874895f1f78459f9517da55a11ffebd.html "Learn how to navigate to your global accounts and subaccounts in the SAP BTP cockpit.") :arrow_upper_right:.

2.  Navigate to *Security* \> *Trust* \> *OpenID Connect Authentication*.

3.  Click *Select OpenID Connect Provider*.

4.  In the list of Identity Authentication tenants that appears, choose the tenant that you want to use as OpenID Connect provider.

    The required application configuration for OpenID Connect is automatically created on the tenant side. It has the following name:

    `SAP BTP Neo OIDC Application - <subAccount>`

    > ### Note:  
    > If you remove this OpenID Connect provider or switch to another one, the created application configuration on the Identity Authentication tenant will be deleted.

5.  If required for your OIDC scenario, configure further the created OpenID Connect application on the Identity Authentication tenant side. For example, you may need to configure user attributes or risk-based authentication.

    See:

    -   [\(Identity Authentication documentation\) OpenID Connect](https://help.sap.com/docs/identity-authentication/identity-authentication/openid-connect?version=Cloud)
    -   [\(Identity Authentication documentation\) Tenant OpenID Connect Configurations](https://help.sap.com/docs/identity-authentication/identity-authentication/tenant-openid-connect-configurations?version=Cloud)

6.  In your application code, declare usng `OIDC` authentication method in the `web.xml`. See [Declarative Authentication](authentication-e637f62.md#loioe36c712efa844e8199a9c4bd681cb4e0).

7.  \(Optional\) If required, change the authentication configuration \(authentication stack\). See [Authentication Configuration](authentication-configuration-4a46723.md).


**Related Information**  


[\(Identity Authentication documentation\) OpenID Connect](https://help.sap.com/docs/identity-authentication/identity-authentication/openid-connect?version=Cloud)

[\(Identity Authentication documentation\) Using the Authorization Code Flow](https://help.sap.com/docs/identity-authentication/identity-authentication/using-authorization-code-flow?version=Cloud)

[\(Identity Authentication documentation\) Tenant OpenID Connect Configurations](https://help.sap.com/docs/identity-authentication/identity-authentication/tenant-openid-connect-configurations?version=Cloud)

[\(OpenID specification\) OpenID Connect Core 1.0](https://openid.net/specs/openid-connect-core-1_0.html)

