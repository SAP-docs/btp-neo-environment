<!-- loiode16793b391a4bcfae6096f34433de76 -->

# Authentication

Authentication is the process of establishing and verifying the identity of a user as a prerequisite for accessing an application.

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/docs/btp/sap-business-technology-platform/sap-business-technology-platform?version=Cloud) .**

By default an HTML5 application is protected with SAML2 authentication, which authenticates the user against the configured IdP.

An HTML5 application can also be protected by OpenID Connect \(OIDC\) authentication, which authenticates the user against the configured Identity Authentication service \(IAS\). For more information, see [OpenID Connect \(OIDC\) Authentication](../60-security-neo/openid-connect-oidc-authentication-084c6fb.md).

For public applications the authentication can be switched off using the following syntax:

```

"authenticationMethod": "saml" | "oidc" | "none"
```

> ### Example:  
> An example configuration that switches off authentication looks like this:
> 
> ```
> "authenticationMethod": "none"
> ```

> ### Note:  
> Even if authentication is disabled, authentication is still required for accessing inactive application versions.
> 
> To protect only parts of your application, set the `authenticationMethod` to "`none`" and define a security constraint for the paths you want to protect. If you want to enforce only authentication, but no additional authorization, define a security constraint without a permission \(see [Authorization](authorization-a139548.md)\).



## Handling Session Timeout

After 20 minutes of inactivity user sessions are invalidated. If the user tries to access an invalidated session, SAP BTP returns a logon page, where the user must log on again. If you are using SAML as a logon method, you cannot rely on the response code to find out whether the session has expired because it is either 200 or 302. To check whether the response requires a new logon, get the `com.sap.cloud.security.login` HTTP header and reload the page. For example:

```

jQuery(document).ajaxComplete(function(e, jqXHR) {
    if(jqXHR.getResponseHeader("com.sap.cloud.security.login")) {
        alert("Session is expired, page shall be reloaded.");
        window.location.reload();
    }
})

```

