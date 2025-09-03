<!-- loio6fafbaa9508e4a0a94b1f7369efe03c2 -->

# Security Development

This section describes how you can implement security in your applications.

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/docs/btp/sap-business-technology-platform/sap-business-technology-platform?version=Cloud) .**

SAP BTP provides the following APIs for user management and authentication:


<table>
<tr>
<th valign="top">

Package

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

**User Management API**

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

`com.sap.security.um`

`com.sap.security.um.user` 

`com.sap.security.um.service`

</td>
<td valign="top">

The user management API can be used to create and delete users or update user information.

</td>
</tr>
<tr>
<td valign="top">

**Authentication API**

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

`com.sap.security.auth.login` 

</td>
<td valign="top">

The authentication API provides basic login modules and callback handlers implementations and a custom LoginContext implemenatation. It relies on the user management API to provide user information required during the authentication process.

</td>
</tr>
<tr>
<td valign="top">

**Password Storage API**

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

`com.sap.cloud.security.password` 

</td>
<td valign="top">

The password storage API allows users to securely persist passwords and key phrases, such as passwords for keystore files.

</td>
</tr>
<tr>
</tr>
<tr>
</tr>
</table>

**Related Information**  


[Authentication](authentication-e637f62.md#loioe637f62abb571014857cb0232adc43a7 "In the Neo environment, enable user authentication for access to your applications.")

[Authorizations](authorizations-85a19f0.md "")

[User Attributes](user-attributes-9e2e0d7.md "You can access user attributes using the User Management Java API (com.sap.security.um.user). It can be used to get and create users or to read and update their information.")

[Logout](logout-2eebf76.md "This topic describes how to enable users to log out from your applications.")

[OAuth 2.0 Authorization Code Grant](oauth-2-0-authorization-code-grant-b7b5893.md "Use OAuth 2.0 service in the Neo environment of SAP BTP to enable your cloud applications for authorization code grant flow. Authorization code grant is one of the basic flows specified in the OAuth 2.0 protocol.")

[Keystore Service](keystore-service-a18327e.md "The Keystore Service provides a repository for cryptographic keys and certificates to the applications in the Neo environment of SAP BTP.")

[Storing Passwords](storing-passwords-244dbc2.md)

[Protection from Cross-Site Request Forgery](protection-from-cross-site-request-forgery-1f5f34e.md "")

[Protection from Cross-Site Scripting \(XSS\)](protection-from-cross-site-scripting-xss-e643316.md "This document describes how to protect SAP BTP applications from XSS attacks.")

