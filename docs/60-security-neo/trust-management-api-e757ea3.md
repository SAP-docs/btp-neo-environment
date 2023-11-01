<!-- loioe757ea3d554b4900a0cab6a46a85aaec -->

# Trust Management API

The Trust Management API for Neo environment allows exporting of the trust configuration from one subaccount and importing it in the same or another subaccount \(this overwrites the existing trust configuration for that subaccount\).

A trust configuration consists of the local service provider settings and application identity providers \(IdPs\).

For more information about the trust configuration, see [Application Identity Provider](application-identity-provider-dc61853.md#loiodc618538d97610148155d97dcd123c24).



<a name="loioe757ea3d554b4900a0cab6a46a85aaec__section_at1_gxg_mtb"/>

## Using the API

**Prerequisites**

> ### Note:  
> This platform API is protected with *OAuth client credentials*.

1.  Create an OAuth client for platform API with required scopes `readTrustSettings` and `manageTrustSettings`.

    > ### Note:  
    > For exporting the trust configuration, you need only `readTrustSettings`. For importing it, you need both `readTrustSettings` and `manageTrustSettings`.

2.  Get an access token with the above scopes.

For more information, see [Using Platform APIs](../30-development-neo/using-platform-apis-392af9d.md).



**API URL**

`https://api.<cloud platform host>/trust/v2/accounts/<subaccount>`

For the cloud platform host, see [Regions and Hosts Available for the Neo Environment](../10-concepts-neo/regions-and-hosts-available-for-the-neo-environment-d722f7c.md).

**API Reference**

See [Trust Management API Reference](https://api.sap.com/api/TrustManagementAPI/overview).



**Use Cases**


<table>
<tr>
<th valign="top">

Use Case

</th>
<th valign="top">

Description

</th>
<th valign="top">

Corresponding Trust Settings

</th>
</tr>
<tr>
<td valign="top">

Fully featured application identity providers

</td>
<td valign="top">

For delegating the authentication and authorization of your applications to a third-party identity provider.

For more information, see [Authorization and Trust Management in the Neo Environment](authorization-and-trust-management-in-the-neo-environment-e6b196a.md).

</td>
<td valign="top">

*Local Service Provider*

*Configuration Type*: Custom

*Application Identity Providers*

At least one fully featured \(not only for IdP-initiated SSO or only for OAuth 2.0 SAML Beared Flow\)

</td>
</tr>
<tr>
<td valign="top">

Configuration with application identity providers only for IdP-initiated single-sign on \(SSO\) or only for OAuth 2.0 SAML Bearer Flow

</td>
<td valign="top">

This allows a more fine-granular and secure control of which IdPs are allowed during login.

*Only for IDP-initiated SSO*: This identity provider can be used only for IdP-initiated single sign-on scenarios. The applications deployed at SAP BTP cannot use it for user authentication from their login pages, for example. Only users coming from links to the application at the IdP side will be able to authenticate.

*Only for OAuth 2.0 SAML Bearer Flow*: The IdP will only be used to validate SAML Assertions received via the OAuth SAML Bearer Flow.

</td>
<td valign="top">

*Local Service Provider*

*Configuration Type*: Default

*Application Identity Providers*

*Only for IdP-initiated SSO*: enabled or *Only for SAML Bearer Flow*: enabled

</td>
</tr>
<tr>
<td valign="top">

Principal propagation

</td>
<td valign="top">

Enables applications to propagate principal information to each other. Choose this use case if you want to enable application-to-application single sign-on.

</td>
<td valign="top">

*Local Service Provider*

*Configuration Type*: Default

*Application Identity Providers*

None

*Principal Propagation*: enabled

</td>
</tr>
<tr>
<td valign="top">

Cross-subaccount principal propagation

</td>
<td valign="top">

Enables principal propagation between applications in different subaccounts. For more information, see [Principal Propagation Between Neo Subaccounts](principal-propagation-between-neo-subaccounts-038c9de.md#loio038c9de27e5c4867a3f13cda9e8c0823).

</td>
<td valign="top">

*Local Service Provider*

*Configuration Type*: Default

*Principal Propagation*: enabled

*Application Identity Providers*: at least one identity provider for IdP-initiated SSO

*Only for IdP-initiated SSO*: enabled

</td>
</tr>
</table>

> ### Note:  
> In the use cases with *Configuration Type*: Default, SAP ID Service will be used as the application identity provider. We recommend using this for testing purposes only.



<a name="loioe757ea3d554b4900a0cab6a46a85aaec__section_brn_whl_mtb"/>

## Examples

**Example 1: Configuration with Fully Featured Application Identity Providers**

If you want to configure custom application identity providers for your subaccount, you need to create a **custom** local service provider configuration, specifying the signing key, certificate, and additional properties.

The application identity providers also need to have their basic settings, such as name, description, Single Sign-On URL and so on. You can also define additional user attributes and groups \(default or assertion-based\). For more information, see [Configure Trust to the SAML Identity Provider](application-identity-provider-dc61853.md#loiob6cfc4bb4bff4ace90afc71b0962fcb5).

> ### Source Code:  
> ```
> {
>     "configurationType": "Custom",
>     "localServiceProvider": {
>         "name": "ExampleSPName",
>         "signingKey": "<private-key>",
>         "signingCertificate": "<public-certificiate>",
>         "principalPropagationEnabled": "false",
>         "forceAuthenticationEnabled": "false",
>         "useCustomApplicationDomains": "true",
>         "centralRedirectUrl": "<valid-url>",
>         "defaultIdentityProviderName": "<idp-name>",
>         "customDomainSloUrls": [
>         	{
>         		"customDomainSloUrl": "<valid-url>"
>         	}
>         ]
>     },
>     "applicationIdentityProviders": {
>         "identityProviders": [
>             {
>                 "name": "ExampleIdP",
>                 "description": "<description>",
>                 "enabled": "true",
>                 "ssoUrl": "https://example.com",
>                 "ssoBinding": "HTTP-POST",
>                 "assertionConsumerService": "AssertionConsumerService",
>                 "sloUrl": "",
>                 "sloBinding": "HTTP-POST",
>                 "userIdSource": {
>                     "type": "Attribute",
>                     "value": "UserId"
>                 },
>                 "userIdPrefix": "Company",
>                 "userIdSuffix": "Ltd.",
>                 "signatureAlgorithm": "SHA-256",
>                 "signingCertificate": "<idp-certificate>",
>                 "assertionBasedAttributes": [
>                     {
>                         "assertionAttribute": "First Name",
>                         "principalAttribute": "firstName"
>                     }
>                 ],
>                 "defaultAttributes": [
>                     {
>                         "defaultAttribute": "Company",
>                         "value": "Company Ltd."
>                     }
>                 ],
>                 "assertionBasedGroups": [
>                     {
>                         "group": "Manager",
>                         "rules": [
>                             {
>                                 "assertionAttribute": "Department",
>                                 "operation": "equals",
>                                 "value": "Team Manager"
>                             },
>                             {
>                                 "assertionAttribute": "Manager",
>                                 "operation": "regexp",
>                                 "value": "[.*]"
>                             }
>                         ]
>                     },
>                     {
>                         "group": "Developers",
>                         "rules": [
>                             {
>                                 "assertionAttribute": "Position",
>                                 "operation": "regexp",
>                                 "value": "[.*]"
>                             }
>                         ]
>                     }
>                 ],
>                 "defaultGroups": [
>                     {
>                         "group": "Developers"
>                     }
>                 ],
>                 "onlyForIdpInitiatedSSO": "false",
>                 "onlyForOAuthSAMLBearerFlow": "false"
>             }
>         ]
>     }
> }
> 
> ```



**Example 2: Configuration with Application Identity Providers Only for IdP-Initiated SSO or Only for OAuth 2.0 SAML Bearer Flow**

> ### Source Code:  
> ```
> {
>     "configurationType": "Default",
>     "applicationIdentityProviders": {
>         "identityProviders": [
>             {
>                 "name": "OnlyForIdPInitiatedSSO",
>                 "description": "Example Description",
>                 "enabled": "true",
>                 "ssoUrl": "https://www.example.com",
>                 "ssoBinding": "HTTP-POST",
>                 "assertionConsumerService": "AssertionConsumerService",
>                 "sloUrl": "",
>                 "sloBinding": "HTTP-POST",
>                 "userIdSource": {
>                     "type": "subject",
>                     "value": ""
>                 },
>                 "userIdPrefix": "",
>                 "userIdSuffix": "",
>                 "signatureAlgorithm": "SHA-1",
>                 "signingCertificate": "<idp-certificate>",
>                 "assertionBasedAttributes": [
>                     {
>                         "assertionAttribute": "attribute",
>                         "principalAttribute": "principalAttribute"
>                     }
>                 ],
>                 "defaultAttributes": [
>                     {
>                         "defaultAttribute": "defaultAttr",
>                         "value": "values"
>                     }
>                 ],
>                 "assertionBasedGroups": [
>                     {
>                         "group": "Developers",
>                         "rules": [
>                             {
>                                 "assertionAttribute": "Position",
>                                 "operation": "regexp",
>                                 "value": "[.*]"
>                             }
>                         ]
>                     },
>                     {
>                         "group": "Users",
>                         "rules": [
>                             {
>                                 "assertionAttribute": "Position",
>                                 "operation": "regexp",
>                                 "value": "[.*]"
>                             }
>                         ]
>                     }
>                 ],
>                 "defaultGroups": [
>                     {
>                         "group": "Developers23"
>                     }
>                 ],
>                 "onlyForIdpInitiatedSSO": "true",
> 		 "onlyForOAuthSAMLBearerFlow": "false"
>             }
>         ]
>     }
> }
> 
> ```



**Example 3: Configuration for Principal Propagation**

> ### Source Code:  
> ```
> {
>     "configurationType": "Default",
>     "localServiceProvider": {
>         "name": "ExampleSPName",
>         "signingKey": "<private-key>",
>         "signingCertificate": "<public-certificiate>",
>         "principalPropagationEnabled": "true",
>         "forceAuthenticationEnabled": "false"
>     },
>     "applicationIdentityProviders": {
>         "identityProviders": []
>     }
> }
> 
> ```



**Example 4: Configuration for Cross-Subaccount Principal Propagation**

> ### Source Code:  
> ```
> {
>     "configurationType": "Default",
>     "localServiceProvider": {
>     "name": "ExampleSPName",
>         "signingKey": "<private-key>",
>         "signingCertificate": "<public-certificiate>",
>         "principalPropagationEnabled": "true",
>         "forceAuthenticationEnabled": "false"
>     },
>     "applicationIdentityProviders": {
>         "identityProviders": [
>             {
>                 "name": "ExampleOnlyForIdPInitiatedSSO",
>                 "description": "Example description",
>                 "enabled": "true",
>                 "ssoUrl": "https://www.example.com",
>                 "ssoBinding": "HTTP-POST",
>                 "assertionConsumerService": "AssertionConsumerService",
>                 "sloUrl": "",
>                 "sloBinding": "HTTP-POST",
>                 "userIdSource": {
>                     "type": "Attribute",
>                     "value": "UserId"
>                 },
>                 "userIdPrefix": "Company",
>                 "userIdSuffix": "Ltd.",
>                 "signatureAlgorithm": "SHA-256",
>                 "signingCertificate": "<idp-certificate>",
>                 "assertionBasedAttributes": [
>                     {
>                         "assertionAttribute": "First Name",
>                         "principalAttribute": "firstName"
>                     }
>                 ],
>                 "defaultAttributes": [
>                     {
>                         "defaultAttribute": "Company",
>                         "value": "Company Ltd."
>                     }
>                 ],
>                 "assertionBasedGroups": [
>                     {
>                         "group": "Manager",
>                         "rules": [
>                             {
>                                 "assertionAttribute": "Department",
>                                 "operation": "equals",
>                                 "value": "Team Manager"
>                             },
>                             {
>                                 "assertionAttribute": "Manager",
>                                 "operation": "regexp",
>                                 "value": "[.*]"
>                             }
>                         ]
>                     },
>                     {
>                         "group": "Developers",
>                         "rules": [
>                             {
>                                 "assertionAttribute": "Position",
>                                 "operation": "regexp",
>                                 "value": "[.*]"
>                             }
>                         ]
>                     }
>                 ],
>                 "defaultGroups": [
>                     {
>                         "group": "Developers"
>                     }
>                 ],
>                 "onlyForIdpInitiatedSSO": "true",
>                 "onlyForOAuthSAMLBearerFlow": "false"
>             }
>         ]
>     }
> }
> 
> ```



**Related Information**  


[Trust Management API Reference](https://api.sap.com/api/TrustManagementAPI/overview)

[Using Platform APIs](../30-development-neo/using-platform-apis-392af9d.md "Platform APIs are protected with OAuth 2.0 client credentials. Create an OAuth client and obtain an access token to call the platform API methods.")

