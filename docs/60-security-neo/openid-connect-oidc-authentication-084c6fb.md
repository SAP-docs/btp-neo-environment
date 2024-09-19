<!-- loio084c6fbf9c984a0292183b41120e7cb4 -->

# OpenID Connect \(OIDC\) Authentication

Protect your applications on SAP BTP, Neo environment with OpenID Connect \(OIDC\) authentication method using an Identity Authentication tenant as an OpenID Connect provider.



<a name="loio084c6fbf9c984a0292183b41120e7cb4__prereq_cb1_fr2_jzb"/>

## Prerequisites

-   You have administrative rights over your subaccount in the Neo environment. See [Members and Roles in the Neo Environment](../50-administration-and-ops-neo/members-and-roles-in-the-neo-environment-5414d4e.md).
-   \(If you want to use a tenant\) You have an Identity Authentication tenant for this subccount. See [\(Identity Authentication documentation\) Initial Setup](https://help.sap.com/docs/identity-authentication/identity-authentication/initial-setup?version=Cloud).



<a name="loio084c6fbf9c984a0292183b41120e7cb4__context_dfq_xgm_2cc"/>

## Context

With the OpenID Connect authentication method, the Identity Authentication tenant or SAP ID service is used as an OpenID Connect provider. Your application's users will authenticate using the credentials defined and verified by the Identity Authentication tenant \(by default, this is a user name/e-mail address and password pair but you can configure your tenant to use others\).

By default, SAP ID Service is used. You can change it to an Identity Authentication tenant, and back to SAP ID Service at any time.

> ### Note:  
> We support the *Authorization Code* flow of the OpenID Connect protocol. For more information about this scenario with Identity Authentication service, see [\(Identity Authentication documentation\) Using Authorization Code Flow](https://help.sap.com/docs/identity-authentication/identity-authentication/using-authorization-code-flow?version=Cloud).

General information about OpenID Connect supported by Identity Authentication service: [\(Identity Authentication documentation\) OpenID Connect](https://help.sap.com/docs/identity-authentication/identity-authentication/openid-connect?version=Cloud).



<a name="loio084c6fbf9c984a0292183b41120e7cb4__steps_efq_xgm_2cc"/>

## Procedure

1.  In the SAP BTP cockpit, navigate to your subaccount. See [Navigate in the Cockpit](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/0874895f1f78459f9517da55a11ffebd.html "Learn how to navigate to your global accounts, directories, and subaccounts in the SAP BTP cockpit.") :arrow_upper_right:.

2.  Navigate to *Security* \> *Trust* \> *OpenID Connect Authentication*.

3.  Click *Select OpenID Connect Provider*.

4.  In the list of Identity Authentication tenants that appears, choose the tenant that you want to use as OpenID Connect provider.

    The required application configuration for OpenID Connect is automatically created on the tenant side. It has the following name:

    `SAP BTP Neo OIDC Application - <subaccount>`

    If you want to choose another Open ID Connect provider or switch back to SAP ID service, choose *Delete OpenID Connect Provider*.

    > ### Note:  
    > This will also delete the created application configuration **on the Identity Authentication tenant**.

5.  If required for your OIDC scenario, configure further the created OpenID Connect \(OIDC\) application on the Identity Authentication tenant side. For example, you may need to configure user attributes/groups or risk-based authentication.

    Group assignments are configured as OIDC application attributes \(see [\(Identity Authentication documentation\) Tenant OpenID Connect Configurations](https://help.sap.com/docs/identity-authentication/identity-authentication/tenant-openid-connect-configurations?version=Cloud)\). Refer to the table below for more information:


    <table>
    <tr>
    <th valign="top">

    Scenario
    
    </th>
    <th valign="top">

    Group Types
    
    </th>
    <th valign="top">

    Attribute Name
    
    </th>
    <th valign="top">

    Attribute Source
    
    </th>
    <th valign="top">

    Attribute Value
    
    </th>
    </tr>
    <tr>
    <td valign="top" rowspan="2">
    
    IAS tenant as a proxy for a third-party identity provider
    
    </td>
    <td valign="top">
    
    Default Groups

    Will be assigned to all users coming from this corporate identity provider.
    
    </td>
    <td valign="top">
    
    `default_groups`
    
    </td>
    <td valign="top">
    
    Expression
    
    </td>
    <td valign="top">
    
    The group name \(String\).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Dynamic Groups

    Will be assigned only to users matching a given conditon.
    
    </td>
    <td valign="top">
    
    `dynamic_groups`
    
    </td>
    <td valign="top">
    
    Expression
    
    </td>
    <td valign="top">
    
    `<tbt>condition</tbt>dynamic group name`

    The `<tbt>` and `</tbt>` parts delimit the condition specifying which users will the group be applied to.

    For more information about the format of the condition, see the *Identity Federation* section of [Configuring Attributes Based on Flexible Parameters](https://help.sap.com/docs/cloud-identity-services/cloud-identity-services/configure-default-attributes-sent-to-application#procedure).

    In the final part of the attribute value, place the dynamic group name.

    For example:

    `<tbt>${corporateIdP.uid:regex[^P.*$]}</tbt>AllPUsers`

    This expression will assign dynamic group `AllPUsers` to all users with user IDs starting with P.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    IAS tenant user base

    As a prerequisite, you have created the required tenant users and groups using the Administration Console. See [Managing Users](https://help.sap.com/docs/cloud-identity-services/cloud-identity-services/user-management) and [Managing Groups](https://help.sap.com/docs/cloud-identity-services/cloud-identity-services/user-groups).
    
    </td>
    <td valign="top">
    
    \-
    
    </td>
    <td valign="top">
    
    `groups`
    
    </td>
    <td valign="top">
    
    Identity Directory
    
    </td>
    <td valign="top">
    
    `Groups` \(choose the option from the dropdown\)
    
    </td>
    </tr>
    </table>
    
    > ### Note:  
    > Make sure you create the same groups in the SAP BTP cockpit, and assign them to the required roles. See [Managing Roles](managing-roles-db8175b.md).

6.  In your application code, declare usng `OIDC` authentication method in the `web.xml`. See [Declarative Authentication](authentication-e637f62.md#loioe36c712efa844e8199a9c4bd681cb4e0).

7.  \(Optional\) If required, change the authentication configuration \(authentication stack\). See [Authentication Configuration](authentication-configuration-4a46723.md).


**Related Information**  


[\(Identity Authentication documentation\) OpenID Connect](https://help.sap.com/docs/identity-authentication/identity-authentication/openid-connect?version=Cloud)

[\(Identity Authentication documentation\) Using the Authorization Code Flow](https://help.sap.com/docs/identity-authentication/identity-authentication/using-authorization-code-flow?version=Cloud)

[\(Identity Authentication documentation\) Tenant OpenID Connect Configurations](https://help.sap.com/docs/identity-authentication/identity-authentication/tenant-openid-connect-configurations?version=Cloud)

[\(OpenID specification\) OpenID Connect Core 1.0](https://openid.net/specs/openid-connect-core-1_0.html)

