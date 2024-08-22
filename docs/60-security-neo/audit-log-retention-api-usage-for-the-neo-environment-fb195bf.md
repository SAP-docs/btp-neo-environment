<!-- loiofb195bf77801406c8c0da7e4d7d60832 -->

# Audit Log Retention API Usage for the Neo Environment

The audit log retention API allows you to view your currently active retention period for all the audit log data that is stored for your account.

The audit log data stored for your account will be retained for 201 days, after which it will be deleted.

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of the following technology portfolios: application development; process automation; integration; data, analytics, and enterprise planning; artificial intelligence. The platform offers users the ability to turn data into business value, compose end-to-end business processes, connect entire IT landscapes, and personalize, build and extend SAP applications. This reduces the overall total cost of ownership maintaining SAP landscapes and third-party software across end-to-end business processes.") :arrow_upper_right:.**

The length of the retention period comes from SAP specific requirements. Using the API, you can modify the default retention period for a customer retention period that corresponds to your legal, business, or other restrictions.

> ### Note:  
> The setup of a custom retention for the first time is related to data migration that could last for up to 24 hours. The audit log retention API may return ***inconsistency*** as a results from the migration during that time frame. All the audit logs written during the transition period are stored and are not lost. They would be visible after the initial transition stage is over. This however is not valid for all the subsequent changes in the retention period made for the same account.

The audit log retention API is protected with OAuth 2.0 client credentials.

It provides two OAuth scopes:

-   Read Audit Logs – allow usage of the Audit Log Retrieval API to retrieve audit logs;

-   Manage Audit Logs – allow usage of the Audit Log Retention API to read retention and set custom retention.


Create an OAuth client and obtain an access token to call the API methods. See [Using Platform APIs](../30-development-neo/using-platform-apis-392af9d.md).



<a name="loiofb195bf77801406c8c0da7e4d7d60832__section_ij5_sfq_hdb"/>

## Example: Get your currently active audit log retention period

To do this you have to execute a similar GET request:

```
https://api.<region host>/auditlog/v1/retention/accounts/<account>/AuditLogRetention
```

To authenticate, in the header provide the taken OAuth token similar to: "***Authorization: Bearer 41fce723412c6c18961f7e95d911ad37***"

The returned results is in a similar JSON format:

```
{ retention : <retention in days> } 
```



<a name="loiofb195bf77801406c8c0da7e4d7d60832__section_ugn_ktm_zdb"/>

## Example: Change your active retention period for the audit log data for your account

To do this change, you have to execute a similar POST request:

```
https://api.<region host>/auditlog/v1/retention/accounts/<account>/AuditLogRetention
```

To authenticate, in header provide the taken OAuth token similar to: "***Authorization: Bearer 41fce723412c6c18961f7e95d911ad37***"

With the following contents in the body part:

```
{ retention : <retention in days> } 
```

> ### Note:  
> Usage of audit log's custom retention period currently does not incur additional charges. This may change in the future and a fee based on the stored data volume and retention period can be applied.

**Related Information**  


[Audit Log Retention API](https://api.sap.com/api/AuditLogRetentionAPI/resource)

[API Documentation](../30-development-neo/api-documentation-4570e92.md "API documentation for the Neo environment.")

