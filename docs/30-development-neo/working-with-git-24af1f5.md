<!-- loio24af1f57105545a69bb4201ec23b151b -->

# Working with Git

The SAP Git service stores the sources of an HTML5 application in a Git repository.

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://launchpad.support.sap.com/#/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**

For each HTML5 application there is one Git repository. You can use any Git client to connect to the Git service. On your development machine you may, for example, use Native Git or Eclipse/EGit. The SAP Web IDE has a built-in Git client.



## Git URL

With this URL, you can access the Git repository using any Git client.

The URL of the Git repository is displayed under *Source Location* on the detail page of the repository. You can also view this URL together with other detailed information on the Git repository, including the repository URL and the latest commits, by choosing *HTML5 Applications* in the navigation area and then *Versioning*.



## Authentication

Access to the Git service is only granted to authenticated users. Any user who is a member of the subaccount that contains the HTML5 application and who has the *Administrator*, *Developer*, or *Support User* role has access to the Git repository. When sending requests, users have to authenticate themselves using their user name and password of the identity provider.



## Permissions

The permitted actions depend on the subaccount member role of the user:

Any authenticated user with the *Administrator*, *Developer*, or *Support User* role can read the Git repository. They have permission to:

-   Clone the repository.
-   Fetch commits and tags.

Write access is granted to users with the *Administrator* or *Developer* role. They have permission to:

-   Push commits if the branch pointer on the server is moved fast-forward.

    Otherwise, the commits need to be rebased locally so that they are successors of the tip of the branch the push is targeting.

-   Push tags, if no tag with the same name exists.

    Pushing a tag defines a new version of the HTML5 application. The version name is the same as the tag name.

-   Create a new branch.

    Currently, only commits in the master branch are visible in the SAP BTP cockpit.

-   Push commits initiated by a different author \(forge author identity\).

    Developers are not allowed to push commits committed by a different user \(forge committer identity\). The committer e-mail address in the commits they push must match the e-mail address they registered in the identity provider.

-   Developers cannot delete or move tags or delete branches.

Only users with the *Administrator* role have permission to:

-   Push commits committed by a different user \(forge committer identity\).
-   Forcefully push commits, for example, to rewrite the Git history of an HTML5 application.
-   Forcefully push tags, for example, to move the version of an HTML5 application to a different commit.
-   Delete tags or delete branches.

**Related Information**  


[Managing Member Authorizations in the Neo Environment](../50-administration-and-ops-neo/managing-member-authorizations-in-the-neo-environment-a1ab5c4.md "SAP BTP includes predefined platform roles that support the typical tasks performed by users when interacting with the platform. In addition, subaccount administrators can combine various scopes into a custom platform role that addresses their individual requirements.")

