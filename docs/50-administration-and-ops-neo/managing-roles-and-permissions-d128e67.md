<!-- loiod128e6796cf94bb187d4bbf69419e2f5 -->

# Managing Roles and Permissions

Resources of an HTML5 application can be protected by permissions. The application developer defines the permissions in the application descriptor file.

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**

To grant a user the permission to access a protected resource, you can either assign a custom role or one of the predefined virtual roles to such a permission. The following predefined virtual roles are available:

-   `AccountAdministrator` is equivalent to the list of subaccount members with administrator permission.
-   `AccountDeveloper` is equivalent to the list of subaccount members with developer permission.
-   `Everyone` is equivalent to all authenticated users of the configured Identity Provider.

`AccountDeveloper` and `AccountAdministrator` require SAP IdP to be configured as identity provider. If you want to use the `AccountDeveloper` or `AccountAdministrator` role together with a custom IDP, create those roles as custom roles and assign the corresponding user manually.

The role assignments are only effective for the active application version. To protect non-active application versions, the default permission `NonActiveApplicationPermission` is defined by the system for every HTML5 application. You can assign a role to this default permission to restrict access to the non-active version of the application.

As long as no other role is assigned to a permission, only subaccount members with developer or administrator permission have access to the protected resource. This is also true for the default permission `NonActiveApplicationPermission`.

You can create roles in the cockpit using either of these panels:

-   *HTML5 Applications*: [Using the HTML5 Applications Panel](using-the-html5-applications-panel-e302036.md)
-   *Subscriptions*: [Using the Subscriptions Panel](using-the-subscriptions-panel-f4737cf.md)

> ### Note:  
> An HTML5 application’s own permissions also apply when the application is reached from another HTML5 application \(see [Accessing Application Resources](../30-development-neo/accessing-application-resources-152cb75.md)\). Previously, only the permissions of the HTML5 application that was accessed first were considered. If you need time to assign the proper roles, you can temporarily switch back to the previous behavior by unchecking *Always Apply Permissions* in the cockpit.

**Related Information**  


[Authorization](../30-development-neo/authorization-a139548.md "To enforce authorization for an HTML5 application, permissions can be added to application paths.")

