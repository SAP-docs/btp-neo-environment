<!-- loio3cc9c49e90a848eabbd7ca040c67d18a -->

# Authorization

HTML5 applications may be protected by permissions.

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of the following technology portfolios: application development; process automation; integration; data, analytics, and enterprise planning; artificial intelligence. The platform offers users the ability to turn data into business value, compose end-to-end business processes, connect entire IT landscapes, and personalize, build and extend SAP applications. This reduces the overall total cost of ownership maintaining SAP landscapes and third-party software across end-to-end business processes.") :arrow_upper_right:.**

Permissions for an HTML5 application are defined in the application descriptor file. For more information about how to define permissions for an HTML5 application, see [Authorization](../30-development-neo/authorization-a139548.md).

Permissions defined in the application descriptor are only effective for the active application version. To protect non-active application versions, the default permission `NonActiveApplicationPermission` is defined by the system for every HTML5 application.

To assign users to a permission of an HTML5 application, a role must be assigned to the corresponding permission. As a result, all users who are assigned to the role get the corresponding permission. Roles are not application-specific but can be reused across multiple HTML5 applications. For more information about creating roles and assigning roles to permissions, see [Managing Roles and Permissions](../50-administration-and-ops-neo/managing-roles-and-permissions-d128e67.md).

> ### Note:  
> HTML5 application permissions can only protect the access to the REST service through the HTML5 application. If the REST service is otherwise accessible on the Internet or a corporate network, it must implement its own authentication and authorization concept..

