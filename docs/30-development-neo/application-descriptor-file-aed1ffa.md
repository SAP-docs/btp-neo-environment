<!-- loioaed1ffa3f3e741b3a4573c9e475aa2a4 -->

# Application Descriptor File

Using the application descriptor file you can configure the behavior of your HTML5 application.

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://launchpad.support.sap.com/#/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**

This descriptor file is named `neo-app.json`. The file must be created in the root folder of the HTML5 application repository and must have a valid JSON format.

With the descriptor file you can set the options listed under *Related Links*.

The application descriptor file must follow the following format. All settings are optional.

```json

{
    "authenticationMethod": "saml"|"none",
    "welcomeFile": "<path to welcome file>",
    "logoutPage": "<path to logout page>",
    "sendWelcomeFileRedirect": true|false,
    "routes": [
        {
            "path": "<application path to be mapped>",
            "target": {
                "type": "destination | service | application",
                "name": "<name of the destination> | <name of the service> | <name of the application or subscription>",
                "entryPath": "<path prepended to the request path>",
                "version": "<version to be referenced. Default is active version.>"
            },
            "description": "<description>"
        }
    ],
    "securityConstraints": [
        {
            "permission": "<permission name>",
            "description": "<permission description>",
            "protectedPaths": [
                "<path to be secured>",
                 ...
            ],
            "excludedPaths": [
                "<path to be excluded>",
                 ...
            ]
        }
    ],
    "cacheControl": [
        {
            "path": "<optional path of resources to be cached>",
            "directive": "none | public | private",
            "maxAge": <lifetime in seconds>
        }
    ],
    "headerWhiteList": [
        "<header1>",
        "<header2>",
         ...
    ]
}
```

All paths in the `neo-app.json` must be specified as plain paths, that is, paths with blanks or other special characters must include these characters literally. These special characters must be URI-encoded in HTTP requests.

**Related Information**  


[Information about: authenticationMethod](authentication-de16793.md "Authentication is the process of establishing and verifying the identity of a user as a prerequisite for accessing an application.")

[Information about: welcomeFile and sendWelcomeFileRedirect](welcome-file-4e9d92e.md "You can either display the default Welcome file or specify a different file as Welcome file.")

[Information about: routes with target type destination](accessing-rest-services-d6c8347.md "To connect your application to a REST service, configure routing to an HTTP destination in the application descriptor file.")

[Information about: routes to include SAPUI5 resources](accessing-sapui5-resources-d18a9b0.md "To access SAPUI5 resources in your HTML5 application, configure the SAPUI5 service routing in the application descriptor file.")

[Information about: routes to access the user API](accessing-the-user-api-1de599b.md "The User API service provides an API to query the details of the user that is currently logged on to the HTML5 application.")

[Information about: securityConstraints](authorization-a139548.md "To enforce authorization for an HTML5 application, permissions can be added to application paths.")

[Information about: cacheControl](cache-control-1814d36.md "To improve the performance of your application you can control the Cache-Control headers, which are returned together with the static resource of your application.")

[Information about: headerWhiteList](approving-http-headers-df89d9c.md "For security reasons not all HTTP headers are forwarded from the application to a backend or from the backend to the application.")

[Accessing Application Resources](accessing-application-resources-152cb75.md "To access resources from another HTML5 application or a subscription to an HTML5 application, you can map an application path to the corresponding application or subscription.")

