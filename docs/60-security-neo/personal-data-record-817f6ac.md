<!-- loio817f6ac090184c0db64b43243bed40f9 -->

# Personal Data Record

A personal data record is a collection of data relating to a data subject. A data privacy specialist may be required to provide such a record or an application may offer a self-service.



> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**



To see the personal data that is used for membership management within SAP BTP, access the cloud cockpit.

1.  Navigate to the global account to which you'd like to view members.

    For more information, see [Navigate to Orgs and Spaces](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/5bf87353bf994819b8803e5910d8450f.html "To administer your Cloud Foundry environment, navigate to orgs, and spaces in the SAP BTP cockpit.") :arrow_upper_right:.

2.  In the navigation area, choose *Members*.

To see the personal data that is used for application logging within SAP BTP, access the cloud cockpit.

For more information, see [Using Logs in the Cockpit](https://help.sap.com/viewer/ee8e8a203e024bbb8c8c2d03fce527dc/Cloud/en-US/2555df65182c4b09a25e56fa3b57b0a8.html) or [Analyze Logs from the Cockpit](https://help.sap.com/viewer/ee8e8a203e024bbb8c8c2d03fce527dc/Cloud/en-US/c29e641662aa46429e0d15bccfb998e7.html) in the Application Logging service documentation.

If you do not use your own identity provider for identity federation, you can view the profiles available in SAP Cloud Identity Services - Identity Authentication.

For more information, see [Information Report](https://help.sap.com/viewer/6d6d63354d1242d185ab4830fc04feb1/Cloud/en-US/cb2c243f62b243edae7272bc23bacc70.html) in the SAP Cloud Identity Services - Identity Authentication documentation.

For SAP BTP Cloud Foundry environment, the User Account and Authentication service creates shadow users to issue tokens for their corresponding users.

For more information about viewing shadow users, see the [User Management \(SCIM\) API](https://api.sap.com/package/authtrustmgmnt) on SAP API Business Hub.

For all other services, which persist data, such as databases or document services, retrieve the data you stored with the same APIs, protocols, or languages you used to store the data.

To view the services used in a global account, choose *Entitlements* in the navigation area.

