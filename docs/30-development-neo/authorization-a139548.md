<!-- loioa139548b21954e319a2a351e993bac40 -->

# Authorization

To enforce authorization for an HTML5 application, permissions can be added to application paths.

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**

In the cockpit, you can create custom roles and assign them to the defined permissions. If a user accesses an application path that starts with a path defined for a permission, the system checks if the current user is a member of the assigned role. If no role is assigned to a defined permission only subaccount members with developer permission or administrator permission have access to the protected resource.

Permissions are only effective for the active application version. To protect non-active application versions, the default permission `NonActiveApplicationPermission` is defined by the system for every HTML5 application. This default permission must not be defined in the `neo-app.json` file but is available automatically for each HTML5 application.

If only authentication is required for a path, but no authorization, a security constraint can be added without a permission.

A security constraint applies to the directory and its sub-directories defined in the `protectedPaths` field, except for paths that are explicitly excluded in the `excludedPaths` field. The `excludedPath` field supports pattern matching. If a path specified ends with a slash character \(/\) all resources in the given directory and its sub-directories are excluded. You can also specify the path to be excluded using wildcards, for example, the path `**.html` excludes all resources ending with `.html` from the security constraint.

To define a security constraint, use the following format in the `neo-app.json` file:

```json

...
    "securityConstraints": [
        {
            "permission": "<permission name>",
            "description": "<permission description>",
            "protectedPaths": [
                "<path to be secured>"
            ],
            "excludedPaths": [
                "<path to be excluded>",
                 ...
            ]
        }
    ]
...

```

> ### Example:  
> An example configuration that restricts a complete application to the `accessUserData` permission, with the exception of all paths starting with `"/logout"`, looks like this:
> 
> ```json
> 
> ...
>     "securityConstraints": [
>         {
>             "permission": "accessUserData",
>             "description": "Access User Data",
>             "protectedPaths": [
>                 "/"
>             ],
>             "excludedPaths": [
>                 "/logout/**"
>             ]
>         }
>     ]
> ...
> 
> ```

**Related Information**  


[Managing Roles and Permissions](../50-administration-and-ops-neo/managing-roles-and-permissions-d128e67.md "Resources of an HTML5 application can be protected by permissions. The application developer defines the permissions in the application descriptor file.")

