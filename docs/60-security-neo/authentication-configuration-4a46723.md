<!-- loio4a467239658c437b9e2de6c9ddfd93fb -->

# Authentication Configuration

You can configure the behavior of standard authentication methods, or define custom ones, based on custom combinations of login options.



## Prerequisites

-   You have an application with authentication defined in its `web.xml` or source code. See [Authentication](authentication-e637f62.md#loioe637f62abb571014857cb0232adc43a7).



## Context

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**

The following table describes the available login options. In the default authentication configuration, they are pre-assigned to standard authentication methods. If you want to change this, you need to create a custom configuration.

For each authentication method, you can select a custom combination of options. You may need to select more than one option if you want to enable more than one way for users to authenticate for this application.

If you select more than one option, SAP BTP will delegate authentication to the relevant login modules consecutively in a stack. When a login module succeeds to authenticate the user, authentication ends with success. If no login module succeeds, authentication fails.


<table>
<tr>
<th valign="top">

Login Option

</th>
<th valign="top">

Descrption

</th>
</tr>
<tr>
<td valign="top">

*OpenID Connect provider*

</td>
<td valign="top">

Authentication is implemented over the OpenID Connect \(OIDC\) protocol, and delegated to an Identity Authentication tenant. The credentials users need to present depend on the tenant settings. See [OpenID Connect Authentication](openid-connect-authentication-084c6fb.md).

> ### Note:  
> You cannot combine this option with *Trusted SAML 2.0 identity provider* and *Application-to-Application SSO*.



</td>
</tr>
<tr>
<td valign="top">

*Trusted SAML 2.0 identity provider*

</td>
<td valign="top">

Authentication is implemented over the Security Assertion Markup Language \(SAML\) 2.0 protocol, and delegated to SAP ID service, an Identity Authentication tenant or custom identity provider \(IdP\). The credentials users need to present depend on the identity provider settings. See [Application Identity Provider](application-identity-provider-dc61853.md#loiodc618538d97610148155d97dcd123c24).

> ### Note:  
> We recommend using the *OpenID Connect provider* option instead of *Trusted SAML 2.0 identity provider* and *Application-to-Application SSO*.



</td>
</tr>
<tr>
<td valign="top">

*User name and password*

</td>
<td valign="top">

HTTP BASIC authentication with user name and password. The user name and password are validated either by SAP ID service \(default\) or by an on-premise SAP NetWeaver AS Java. See [Using an SAP System as an On-Premise User Store](using-an-sap-system-as-an-on-premise-user-store-71fdf1c.md).

</td>
</tr>
<tr>
<td valign="top">

*Client certificate*

</td>
<td valign="top">

Users authenticate with a client certificate installed in an on-premise SAP NetWeaver Application Server for Java system. See [Enabling Client Certificate Authentication](enabling-client-certificate-authentication-0d7cf63.md)

</td>
</tr>
<tr>
<td valign="top">

*Application-to-Application SSO*

</td>
<td valign="top">

Used for AppToAppSSO destinations. See [Application-to-Application SSO Authentication](https://help.sap.com/viewer/b865ed651e414196b39f8922db2122c7/Cloud/en-US/e022a5eebaec4dbbabef7f5d60e13dd4.html "") :arrow_upper_right:.

> ### Note:  
> When you select *Trusted SAML 2.0 identity provider*, *Application-to-Application SSO* becomes enabled automatically.



</td>
</tr>
<tr>
<td valign="top">

*OAuth 2.0 token*

</td>
<td valign="top">

Authentication is implemented over the OAuth 2.0 protocol. Users need to present an OAuth access token as credential. See [OAuth 2.0 Authorization Code Grant](oauth-2-0-authorization-code-grant-b7b5893.md).

</td>
</tr>
</table>



## Procedure

1.  In the SAP BTP cockpit, navigate to the required SAP BTP subaccount. See [Navigate in the Cockpit](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/0874895f1f78459f9517da55a11ffebd.html "Learn how to navigate to your global accounts and subaccounts in the SAP BTP cockpit.") :arrow_upper_right:.

2.  Enter the *Applications* \> *Java Applications* section.

3.  Click the application you want to configure.

4.  Enter the *Authentication Configuration* section.

5.  To configure the default settings, choose *Activate Custom Configuration*.

    *Reset Custom ConfigurationYou can configure existing authentication methods or create new ones. If you need to restore the default state of all default methods, choose the* button for the entire panel. If you need to restore the default state of a particular method, choose the *Reset Authentication Method* button for that method \(not available for custom methods you defined\).

6.  Save the changes to the authentication configuration.

7.  Restart the application so the changes can take effect.




## Example

You have a Web application that users access using a Web browser. You want users to log in using a SAML identity provider. Hence, you define the FORM authentication method in the `web.xml`You can configure existing authentication methods or create new ones. If you need to of the application. However, later you decide to provide mobile access to your application using the OAuth protocol \(SAML is not optimized for mobile access\). You do this by adding the *OAuth 2.0 token* option for the FORM method for your application. In this way, desktop users will continue to log in using a SAML identity provider, and mobile users will use an OAuth 2.0 access token.

**Related Information**  


[Authentication](authentication-e637f62.md#loioe637f62abb571014857cb0232adc43a7 "In the Neo environment, enable user authentication for access to your applications.")

[Specifying Authentication Mechanisms \(general information\)](http://docs.oracle.com/javaee/6/tutorial/doc/gkbaa.html#gkbsa)

