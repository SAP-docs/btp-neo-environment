<!-- loiode16793b391a4bcfae6096f34433de76 -->

# Authentication

Authentication is the process of establishing and verifying the identity of a user as a prerequisite for accessing an application.

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://launchpad.support.sap.com/#/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**

By default an HTML5 application is protected with SAML2 authentication, which authenticates the user against the configured IdP. For more information, see [Application Identity Provider](../60-security-neo/application-identity-provider-dc61853.md#loiodc618538d97610148155d97dcd123c24). For public applications the authentication can be switched off using the following syntax:

```

"authenticationMethod": "saml" | "none"
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

