<!-- loiofa6645e133f74544a44543226e933fc8 -->

# Commmon Errors with Basic Authentication in SAP ID Service



> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://launchpad.support.sap.com/#/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**



This section describes the error messages you may encounter when using BASIC authentication with SAP ID Service as an identity provider.

For more information about using BASIC authentication, see [Authentication](authentication-e637f62.md#loioe637f62abb571014857cb0232adc43a7).

**Error Messages**


<table>
<tr>
<th valign="top">

Error Message



</th>
<th valign="top">

Description



</th>
</tr>
<tr>
<td valign="top">

Your account is temporarily locked. It will be automatically unlocked in 60 minutes.



</td>
<td valign="top">

SAP ID Service has registered five unsuccessful login attempts for this account in a short time. For security reasons, your account is disabled for 60 minutes.



</td>
</tr>
<tr>
<td valign="top">

Password authentication is disabled for your account. Log in with a certificate.



</td>
<td valign="top">

The owner of this account has disabled password authentication using their user profile settings in SAP ID service.



</td>
</tr>
<tr>
<td valign="top">

Inactive account. Activate it via your account creation confirmation email



</td>
<td valign="top">

This is a new account and you haven’t activated it yet. You will receive an e-mail confirming your account creating, and containing an account activation link.



</td>
</tr>
<tr>
<td valign="top">

Login failed. Contact your administrator.



</td>
<td valign="top">

You cannot log in for a reason different from all others listed here.



</td>
</tr>
</table>

