<!-- loio25e3cc6e3f1e402e850bb920204c76b3 -->

# Deletion

The processing of personal data is subject to applicable laws related to the deletion of this data when the specified, explicit, and legitimate purpose for processing this personal data has expired. If there is no longer a legitimate purpose that requires the retention and use of personal data, it must be deleted.



> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of the following technology portfolios: application development; process automation; integration; data, analytics, and enterprise planning; artificial intelligence. The platform offers users the ability to turn data into business value, compose end-to-end business processes, connect entire IT landscapes, and personalize, build and extend SAP applications. This reduces the overall total cost of ownership maintaining SAP landscapes and third-party software across end-to-end business processes.") :arrow_upper_right:.**



When deleting data in a data set, all referenced objects related to that data set must be deleted as well. Industry-specific legislation in different countries also needs to be taken into consideration in addition to general data protection laws. After the expiration of the longest retention period, the data must be deleted.

When accounts expire, we delete your data barring legal requirements that SAP retains your data. If your organization has separate retention requirements, you are responsible for saving this data before we terminate your account.

-   For trial accounts in the Cloud Foundry environment, your account expires after 365 days.
-   Productive accounts expire based on the terms of your contract.

To deactivate or delete users, see [Erasure](https://help.sap.com/viewer/6d6d63354d1242d185ab4830fc04feb1/Cloud/en-US/5ccec0b19422406fac24b9323294b980.html) in the SAP Cloud Identity Services documentation.

For SAP BTP Cloud Foundry environment, the User Account and Authentication service creates shadow users to issue tokens for their corresponding users. Data privacy regulations or policies may require you to delete this data, for example, when the user has left your organization.

For more information about deleting shadow users, see:

-   [Delete Shadow Users for Data Protection and Privacy Using the Cockpit](delete-shadow-users-for-data-protection-and-privacy-using-the-cockpit-893c5ac.md)

-   [Delete Shadow Users for Data Protection and Privacy Using APIs](delete-shadow-users-for-data-protection-and-privacy-using-apis-eb70f16.md)

    > ### Remember:  
    > When you delete a user at the Cloud Foundry level, SAP BTP doesn’t delete the corresponding shadow user at the subaccount level.
    > 
    > When you delete a user at the subaccount level, ensure that you delete the user at the Cloud Foundry level too. Otherwise, if the Cloud Foundry user logs on again, the system automatically creates the corresponding user at the subaccount level.
    > 
    > So ensure that you delete the shadow users on all levels.


For all other services which persist data, you can retrieve the data you stored with the same APIs, protocols, or languages which you used to store the data.

To view the services used in a global account, choose *Entitlements* in the navigation area.

SAP BTP Data Retention Manager is a service available for the Cloud Foundry environment that helps you to identify data subjects for deletion as well as maintain rules for residence and retention.

For more information, see [SAP BTP Data Retention Manager](https://help.sap.com/viewer/product/DATA_RETENTION_MANAGER).

We maintain backups of the data for disaster recovery. When your account is deleted, we may have this data in our backup system for the length of our backup cycle.

> ### Note:  
> If your data is stored outside SAP BTP, we cannot guarantee that your data does not get reintegrated if you are pushing such data to our systems. You are responsible for terminating such integrations.
> 
> We cannot restore data you have in your local system.

