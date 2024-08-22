<!-- loio4d6131a5588f4562900b8f32632d6eeb -->

# Uploading Users to Identity Authentication

When you configure the Identity Authentication service as the SAML identity provider for your SAP Cloud for Customer system, you have to make sure that all users from SAP Cloud for Customer will have an identity record in the Identity Authentication service. For this purpose, you have to export the user details in a CSV file format and then use this CSV file to import these users into the Identity Authentication tenant of your company that will be used as the identity provider.



## Context

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of the following technology portfolios: application development; process automation; integration; data, analytics, and enterprise planning; artificial intelligence. The platform offers users the ability to turn data into business value, compose end-to-end business processes, connect entire IT landscapes, and personalize, build and extend SAP applications. This reduces the overall total cost of ownership maintaining SAP landscapes and third-party software across end-to-end business processes.") :arrow_upper_right:.**

To upload the users of your SAP Cloud for Customer company into Identity Authentication, you export the user base and import it into Identity Authentication in CSV format.



## Procedure

1.  Export the SAP Cloud for Customer users and save the data in CSV format. For more information, see [Exporting SAP Cloud for Customer Users](exporting-sap-cloud-for-customer-users-c35dd7c.md)

2.  Import the users \(user names and user IDs\) in the Identity Authentication tenant with the CSV file you have exported from your SAP Cloud for Customer system. For more information, see [Importing or Updating SAP Cloud for Customer Users in Identity Authentication](importing-or-updating-sap-cloud-for-customer-users-in-identity-authentication-0704d6c.md).


