<!-- loiodbea343ebe184c26b6067daaabaa9ac6 -->

# Authorization Management API

The Authorization Management API allows you to manage user roles and groups, and their assignments in your applications.

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/docs/btp/sap-business-technology-platform/sap-business-technology-platform?version=Cloud) .**



> ### Note:  
> We strongly recommend that you use this API only for administration, not for runtime checks of authorizations. For the runtime checks, we recommend using `HttpServletRequest.isUserInRole(java.lang.String role)`. See [Authorizations](authorizations-85a19f0.md).

> ### Note:  
> HTML5 applications are using a more feature-rich authorization model, which allows to assign *permissions* on various *URI paths*. Those permissions are then mapped to SAP BTP *custom roles*. Since all HTML5 applications are run via a central app called *dispatcher* from the *services* account – all of them share the same custom roles and mappings. This the reason why when you are managing roles of HTML5 applications, in the API calls you need to use *dispatcher* for *appName* and *services* for *providerAccount* name.



<a name="loiodbea343ebe184c26b6067daaabaa9ac6__section_dtp_1mf_vtb"/>

## Using the API

**Prerequisites**

> ### Note:  
> This platform API is protected with *OAuth 2.0 client credentials*.

1.  Create an OAuth client for platform API with the required scopes for using the Authorization Management API \(for example, `readApplicationRoles`, `manageApplicationRoles`, `readAuthorizationSettings` and `manageAuthorizationSettings`\). For the complete list and descriptions, see section *Authorization Management* in [Platform Scopes](../50-administration-and-ops-neo/platform-scopes-f226074.md).
2.  Get an access token with the required scopes.

For more information, see [Using Platform APIs](../30-development-neo/using-platform-apis-392af9d.md).



**API URL**

`https://api.<cloud platform host>/authorization/v1/accounts/<subaccount>`

For the cloud platform host, see [Regions and Hosts Available for the Neo Environment](../10-concepts-neo/regions-and-hosts-available-for-the-neo-environment-d722f7c.md).



**API Reference**

See [Authorization Management API \(Reference\)](https://api.hana.ondemand.com/authorization/v1/documentation).



**Example: Accessing Roles**

1.  At application level, create an HTTP destination with the following information:

    -   Name=<your destination name\>

    -   URL=https://api.<cloud platform host\>/authorization/v1

    -   ProxyType=Internet

    -   Type=HTTP

    -   Authentication=NoAuthentication

    -   CloudConnectorVersion=2


    See [Create HTTP Destinations](https://help.sap.com/viewer/b865ed651e414196b39f8922db2122c7/Cloud/en-US/1e110da0ddd8453aaf5aed2485d84f25.html "Create HTTP destinations in the Destinations editor (SAP BTP cockpit).") :arrow_upper_right:.

2.  In your application, obtain an `HttpURLConnection` object that uses the destination.

    See [ConnectivityConfiguration API](https://help.sap.com/viewer/b865ed651e414196b39f8922db2122c7/Cloud/en-US/4da3b13c88ce4220bbd56a4361799668.html "All connectivity API packages are visible by default from all Web applications. Applications can consume the connectivity configuration via a JNDI lookup.") :arrow_upper_right:.

3.  With the object retrieved from the previous step, execute a GET call.

    ```
    //value is the URL property of the destination
    URL url = new URL(value + "/accounts/{account}/applications/{application}/roles"); 
       
    HttpURLConnection urlConnection = (HttpURLConnection)url.openConnection();
    urlConnection.setRequestMethod("GET");
    urlConnection.setRequestProperty("Authorization", "Bearer <token ID from previous step>");
    urlConnection.connect();
    
    ```


A response returning the roles could be:

```
{
    "roles": [
        {
            "name": "Developer",
            "type": "PREDEFINED",
            "applicationRole": true,
            "shared": true
        },
        {
            "name": "Administrator",
            "type": "PREDEFINED",
            "applicationRole": true,
            "shared": true
        }
    ]
}

```



<a name="loiodbea343ebe184c26b6067daaabaa9ac6__section_gf2_n1v_x1c"/>

## Rate Limits

Rate limits are used to limit the number of requests against this REST API. Requests may be throttled \(delayed\), and if there is a very high load also denied.

The following limits are available:

**Limit**

If this limit is **fully exceeded**, the service responds with '429 - Too many requests'.

The **rate limit** defined for the API is **100 requests** per minute per subaccount.

> ### Note:  
> Depending on the service health, this limit may be ignored or further reduced to keep the service operational.

**Related Information**  


[Authorization Management API Reference](https://api.hana.ondemand.com/authorization/v1/documentation)

[Using Platform APIs](../30-development-neo/using-platform-apis-392af9d.md "Platform APIs are protected with OAuth 2.0 client credentials. Create an OAuth client and obtain an access token to call the platform API methods.")

