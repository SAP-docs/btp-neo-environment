<!-- loio0c5ca8eb95214869bd1e8c5880f4b1b5 -->

# Logout Page

To trigger a logout of the logged-in user, you can configure a logout page in the application descriptor.

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of the following technology portfolios: application development; process automation; integration; data, analytics, and enterprise planning; artificial intelligence. The platform offers users the ability to turn data into business value, compose end-to-end business processes, connect entire IT landscapes, and personalize, build and extend SAP applications. This reduces the overall total cost of ownership maintaining SAP landscapes and third-party software across end-to-end business processes.") :arrow_upper_right:.**

When executing a request to the configured logout page, the server triggers a logout. This results in a response containing a logout request that is send to the identity provider \(IdP\) to invalidate the user's session on the IdP. After the user is logged out from the IdP, the configured logout page is called again. Now, the content of the logout page is served. The logout page is always unprotected, independent of the authentication method of the application and independent of additional security constraints. In case additional resources, for example, SAPUI5, are referenced from the logout page, those resources have to be unprotected as well.

For information on how to configure certain paths as unprotected, see [Authentication](authentication-de16793.md) and [Authorization](authorization-a139548.md).

Because non-active application versions always require authentication, a logout is only triggered for the active application version. For non-active application versions the logout page is served without triggering a logout.

To configure a logout page for your application, use the following format in the `neo-app.json` file:

```

...
    "logoutPage": "<path to logout page>"
...

```

> ### Example:  
> An example configuration of a logout page looks like this:
> 
> ```
> 
> ...
>     "logoutPage": "/logout.html"
> ...
> 
> ```

