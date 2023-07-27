<!-- loioeb01a9f3ecad4a41a6033855ca61a9a8 -->

# Platform Authorization Management API

The Platform Authorization Management API allows you to manage the users authorized to access your subaccount in the Neo environment.

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://launchpad.support.sap.com/#/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**



The Platform Authorization Management API is implemented over the [System for Cross-domain Identity Management \(SCIM\)](https://tools.ietf.org/html/rfc7644) protocol. The HTTP requests that you send to this API need to be SCIM-compliant.



<a name="loioeb01a9f3ecad4a41a6033855ca61a9a8__section_rwy_yym_dtb"/>

## Using the API

**Prerequisites**

> ### Note:  
> This platform API is protected with *OAuth client credentials*.

1.  Create an OAuth client for platform API with required scopes \(for example, `readAccountMembers` and `manageAccountMembers`\). For the complete list and descriptions, see section *Platform Authorization Management* in [Platform Scopes](../50-administration-and-ops-neo/platform-scopes-f226074.md).
2.  Get an access token with the above scopes.

For more information, see [Using Platform APIs](../30-development-neo/using-platform-apis-392af9d.md).



**API URL**

```
https://api.<cloud platform host>/authorization/v1/platform/accounts/<subaccount>/Users
```

For the cloud platform host, see [Regions and Hosts Available for the Neo Environment](../10-concepts-neo/regions-and-hosts-available-for-the-neo-environment-d722f7c.md).

**API Reference**

See [Platform Authorization Management API Reference](https://api.sap.com/api/AccountMembersManagementAPI/resource).

**ServiceProviderConfig Endpoint**

```
https://api.<cloud platform host>/authorization/v1/platform/ServiceProviderConfig
```

By the SCIM specification, you can access this endpoint \(using HTTP GET\) to retrieve the API configuration and its supported features. This endpoint is unprotected.

**Filtering Users**

You can do two types of filtering: based on the user ID or the user base. For more information about changing and managing the user base, see [Platform Identity Provider](platform-identity-provider-80edbe7.md).

> ### Restriction:  
> Only the **eq** operator is supported for filtering. For more information, see [Section 3.4.2.2: Filtering](https://tools.ietf.org/html/rfc7644#section-3.4.2.2)

Use the following URL:

```
https://api.<cloud platform host>/authorization/v1/platform/accounts/<subaccount>/Users?filter=username eq "<user name>"
```

or

```
https://api.<cloud platform host>/authorization/v1/platform/accounts/<subaccount>/Users?filter=userbase eq "<user base>"
```

> ### Note:  
> The above two URLs are case insensitive. For more information, see [Section 7.8: Case-Insensitive Comparison and International Languages](https://tools.ietf.org/html/rfc7644#section-7.8) of the SCIM protocol specification.

The Platform Authorization Management API returns two types of user roles: `Predefined` and `Custom`. For more information about roles, see [Managing Roles](managing-roles-db8175b.md).

If a user comes from a custom user base \(that is, your custom Identity Authentication tenant, not SAP ID service\), the Platform Authorization Management API returns the user ID with a suffix `_<your Identity Authentication tenant>`.



<a name="loioeb01a9f3ecad4a41a6033855ca61a9a8__section_hcy_pqr_zbb"/>

## Examples

**Example 1: Getting the Attributes of a User Assigned to This Subaccount**

A prerequisite is having a valid OAuth access token with the required scopes. See [Using Platform APIs](../30-development-neo/using-platform-apis-392af9d.md).

1.  At application level, create an HTTP destination with the following information:

    -   Name=<your destination name\>

    -   URL=https://api.<cloud platform host\>/authorization/v1/platform/accounts/<subaccount\>/Users/<user ID\>

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
    URL url = new URL(value + "/accounts/<my subaccount>/Users/<userID>"); 
       
    HttpURLConnection urlConnection = (HttpURLConnection)url.openConnection();
    urlConnection.setRequestMethod("GET");
    urlConnection.setRequestProperty("Authorization", "Bearer <OAuth token ID>");
    urlConnection.connect();
    
    ```


A response returning the list of users could be:

```
{
            "id": "P1234567",
            "meta": {
                "created": "2019-01-16T18:01:57.105Z",
                "lastModified": "2019-01-16T18:01:57.105Z",
                "location": "https://api.hana.ondemand.com/authorization/v1/platform/accounts/myaccount/Users/P1234567"
            },
            "schemas": [
                "com:sap:cloud:security:platform:1.0:UserExt",
                "urn:ietf:params:scim:schemas:core:2.0:User"
            ],
            "userName": "P1234567",
            "name": {
                "familyName": "Smith",
                "givenName": "John"
            },
            "emails": [
                {
                    "value": "jsmith@mycompany.com",
                    "primary": true
                }
            ],
            "roles": [
                {
                    "value": "AccountAdministrator",
                    "primary": false
                },
                {
                    "value": "Developer",
                    "primary": false
                }
            ],
            "com:sap:cloud:security:platform:1.0:UserExt": {
                "userbase": "accounts.sap.com"
            }
}

```



**Example 2: Filtering Users by User Name**

A prerequisite is having a valid OAuth access token with the required scopes. See [Using Platform APIs](../30-development-neo/using-platform-apis-392af9d.md)

As with the previous example, you can use an HTTP destination object for convenience in managing your connections. For testing purposes, you can access directly the API using an HTTP GET request. Let's try to get all users with name P1234567. Then our HTTP URL looks like that:

```
https://api.<cloud platform host>/authorization/v1/platform/accounts/<subaccount>/Users?filter=username eq "P1234567"
```

A response returning the list of users with the same name available in different user bases could be:

```
{
"Resources": [
    {
        "id": "P1234567",
        "meta": {
            "created": "2019-02-12T13:54:14.604Z",
            "lastModified": "2019-02-12T13:54:14.604Z",
            "location": "https://api.hana.ondemand.com/authorization/v1/platform/accounts/<subaccount>/Users/P1234567"
        },
        "schemas": [
            "urn:sap:cloud:scim:schemas:extension:custom:2.0:UserExt",
            "urn:ietf:params:scim:schemas:core:2.0:User"
        ],
        "userName": "P1234567",
        "roles": [
            {
                "value": "AccountAdministrator",
                "primary": false,
                "type": "Predefined"
            },
            {
                "value": "Developer",
                "primary": false,
                "type": "Predefined"
            }
        ],
        "urn:sap:cloud:scim:schemas:extension:custom:2.0:UserExt": {
            "userbase": "ACCOUNTS.SAP.COM"
        }
    },
    {
        "id": "P1234567_ACCOUNTS400.SAP.COM",
        "meta": {
            "created": "2019-02-12T13:54:14.604Z",
            "lastModified": "2019-02-12T13:54:14.604Z",
            "location": "https://api.hana.ondemand.com/authorization/v1/platform/accounts/<subaccount>/Users/P1234567_ACCOUNTS400.SAP.COM"
        },
        "schemas": [
            "urn:sap:cloud:scim:schemas:extension:custom:2.0:UserExt",
            "urn:ietf:params:scim:schemas:core:2.0:User"
        ],
        "userName": "P1234567",
        "roles": [
            {
                "value": "AccountAdministrator",
                "primary": false,
                "type": "Predefined"
            },
            {
                "value": "Developer",
                "primary": false,
                "type": "Predefined"
            }
        ],
        "urn:sap:cloud:scim:schemas:extension:custom:2.0:UserExt": {
            "userbase": "ACCOUNTS400.SAP.COM"
        }
    },
    {
        "id": "P1234567_ACCOUNTS500.SAP.COM",
        "meta": {
            "created": "2019-02-12T13:54:14.604Z",
            "lastModified": "2019-02-12T13:54:14.604Z",
            "location": "https://api.hana.ondemand.com/authorization/v1/platform/accounts/<subaccount>/Users/P1234567_ACCOUNTS500.SAP.COM"
        },
        "schemas": [
            "urn:sap:cloud:scim:schemas:extension:custom:2.0:UserExt",
            "urn:ietf:params:scim:schemas:core:2.0:User"
        ],
        "userName": "P1234567",
        "roles": [
            {
                "value": "AccountAdministrator",
                "primary": false,
                "type": "Predefined"
            },
            {
                "value": "Developer",
                "primary": false,
                "type": "Predefined"
            }
        ],
        "urn:sap:cloud:scim:schemas:extension:custom:2.0:UserExt": {
            "userbase": "ACCOUNTS500.SAP.COM"
        }
    }
],
"totalResults": 3,
"itemsPerPage": 3,
"startIndex": 1,
"schemas": [
    "urn:ietf:params:scim:api:messages:2.0:ListResponse"
]
}


```

**Related Information**  


[Platform Authorization Management API Reference](https://api.sap.com/api/AccountMembersManagementAPI/resource)

[Using Platform APIs](../30-development-neo/using-platform-apis-392af9d.md "Platform APIs are protected with OAuth 2.0 client credentials. Create an OAuth client and obtain an access token to call the platform API methods.")

