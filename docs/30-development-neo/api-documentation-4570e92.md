<!-- loio4570e92cd29e419dbeee4caa1ef90701 -->

# API Documentation

API documentation for the Neo environment.



> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of the following technology portfolios: application development; process automation; integration; data, analytics, and enterprise planning; artificial intelligence. The platform offers users the ability to turn data into business value, compose end-to-end business processes, connect entire IT landscapes, and personalize, build and extend SAP applications. This reduces the overall total cost of ownership maintaining SAP landscapes and third-party software across end-to-end business processes.") :arrow_upper_right:.**



[SAP HANA XS JavaScript Reference](https://help.sap.com/viewer/d89d4595fae647eabc14002c0340a999/2.0.02/en-US)

[SAP BTPSDK for iOS](https://help.sap.com/doc/978e4f6c968c4cc5a30f9d324aa4b1d7/Latest/en-US/Documents/index.html)



## REST APIs



### Lifecycle Management

[Java ALM API](https://api.sap.com/api/SAP_HCP_Lifecycle_Management)

[Reverse Proxy](https://api.sap.com/api/Reverse_Proxy)

[SAP Virtual Machine Service API \(Basic Authentication\)](https://api.sap.com/api/HCP_Virtual_Machines)

[SAP Virtual Machine Service API \(OAuth\)](https://api.sap.com/api/Virtual_Machines_OAuth)



### SAP Audit Log Service

[Audit Log Retrieval API for the Neo Environment](https://api.sap.com/api/AuditLogRetrievalAPI/resource)

[Audit Log Retention API for the Neo Environment](https://api.sap.com/api/AuditLogRetentionAPI/resource)

[Audit Log Retrieval API for the Cloud Foundry Environment](https://api.sap.com/api/CFAuditLogRetrievalAPI/resource)



### SAP Monitoring Service

[Alerting Channels API](https://api.sap.com/api/HCP_Alerting_v2)

[Checks API](https://api.sap.com/api/HCP_Monitoring_checks)

[Metrics API](https://api.sap.com/api/HCP_Monitoring_v2)



### SAP Application Logging Service

[Logs API](https://api.sap.com/api/HCP_Logging)

[Log Channels API](https://api.sap.com/api/HCP_Log_channels)



### Security

[Trust Management API](https://api.sap.com/api/TrustManagementAPI/overview)

[Authorization Management API](https://api.hana.ondemand.com/authorization/v1/documentation)

[Platform Authorization Management API](https://api.sap.com/api/AccountMembersManagementAPI/resource)

[Reverse Proxy API](https://api.sap.com/api/Reverse_Proxy/overview)

[Password Storage API](https://api.sap.com/api/SCP_PasswordStorage/resource)

[Keystore API](https://api.hana.ondemand.com/keystore/v1/documentation)



### More APIs

[SAP Business Accelerator Hub](https://api.sap.com/products/SAPCloudPlatform/apis/REST)



<a name="loio4570e92cd29e419dbeee4caa1ef90701__section_wfs_qgd_ndb"/>

## Java API Documentation for Neo Environment

The Java API documentation for the Neo environment is provided as part of the downloadable SDK archives. To get to it, do the following:

1.  Install the SDK for Neo environment of your choice. See [Install the SAP BTP SDK for Neo Environment](install-the-sap-btp-sdk-for-neo-environment-7613843.md).
2.  On your local machine, navigate to the folder of the archive you downloaded and extracted.
3.  Navigate to the *javadoc* folder, and open *index.html* in your Web browser.

**Related Information**  


[Java ALM API](java-alm-api-fc944d1.md#loiofc944d19af614052898b145deb2bee59 "The Java ALM service REST API provides functionality for managing the lifecycle of Java applications.")

[Audit Log Retrieval API Usage for the Neo Environment](../60-security-neo/audit-log-retrieval-api-usage-for-the-neo-environment-e4d818d.md "The audit log retrieval API allows you to retrieve the audit logs for your SAP BTP Neo environment account. It follows the OData 4.0 standard, providing the audit log results as OData with collection of JSON entities.")

[Audit Log Retention API Usage for the Neo Environment](../60-security-neo/audit-log-retention-api-usage-for-the-neo-environment-fb195bf.md "The audit log retention API allows you to view your currently active retention period for all the audit log data that is stored for your account.")

[Metrics REST API for Java Applications](https://help.sap.com/viewer/64f7d2b06c6b40a9b3097860c5930641/Cloud/en-US/14bbf239d9e44096bdd2278e7317012b.html "Use this REST API to get metrics for Java applications in the Neo environment.") :arrow_upper_right:

[Metrics REST API for HTML5 Applications](https://help.sap.com/viewer/64f7d2b06c6b40a9b3097860c5930641/Cloud/en-US/f62bdfc1fb7c45ccb1255c62d34bf967.html "Use the REST API to get metrics for your HTML5 applications that are running on SAP BTP in the Neo environment.") :arrow_upper_right:

[Metrics REST API for SAP HANA XS](https://help.sap.com/viewer/64f7d2b06c6b40a9b3097860c5930641/Cloud/en-US/9f02513389e64490a0652955fedce2ad.html "Use the REST API to get metrics for your SAP HANA XS applications and instances that are running in the Neo environment.") :arrow_upper_right:

[Metrics REST API for Database Systems](https://help.sap.com/viewer/64f7d2b06c6b40a9b3097860c5930641/Cloud/en-US/9f883c61f23b432f89bb108644e819ad.html "Use the REST API to get metrics for your database systems that are running in the Neo environment.") :arrow_upper_right:

[Checks REST API for Java Applications](https://help.sap.com/viewer/64f7d2b06c6b40a9b3097860c5930641/Cloud/en-US/1eb1807a091940b996fe4b2539b0efc3.html "Use the Checks API to retrieve, set, update, or delete custom checks or default check thresholds for Java applications in the Neo environment.") :arrow_upper_right:

[Checks REST API for HTML5 Applications](https://help.sap.com/viewer/64f7d2b06c6b40a9b3097860c5930641/Cloud/en-US/30ce97b33aa54e73b11528f94494f464.html "Use the Checks API to retrieve, set, update, or delete custom checks for HTML5 applications in the Neo environment.") :arrow_upper_right:

[Checks REST API for SAP HANA XS Applications](https://help.sap.com/viewer/64f7d2b06c6b40a9b3097860c5930641/Cloud/en-US/283da4c3ff37484d93b9dc683152b8bd.html "Use the Checks API to retrieve, set, update, or delete custom checks for HTML5 applications in the Neo environment.") :arrow_upper_right:

[Alerting](https://help.sap.com/viewer/64f7d2b06c6b40a9b3097860c5930641/Cloud/en-US/2f782d7f73304426b287f4b25e47f0b1.html "Configure a channel to receive alert notifications from SAP Monitoring service when your applications and database systems are in a problematic state or have recovered from such a state.") :arrow_upper_right:

[Logs API for Java and HTML5 Applications](https://help.sap.com/viewer/f88a032109f0429caea276fc6e3a95f9/Cloud/en-US/ceea93da98a84f4db5f269f2f19bda16.html "Use this REST API to get log files for Java and HTML5 applications in the Neo environment.") :arrow_upper_right:

[Log Channels API](https://help.sap.com/viewer/f88a032109f0429caea276fc6e3a95f9/Cloud/en-US/f328e89a926f4daf88bef6e01d762697.html "Use this REST API to configure a webhook channel to receive logs for a subaccount in the Neo environment.") :arrow_upper_right:

[Get Started: SAP Virtual Machine Service API (Neo Environment)](https://help.sap.com/viewer/c746ff81651e4b8fb6efc11146091016/Cloud/en-US/5867769a02f14458998af4f8d3b07483.html#loio5867769a02f14458998af4f8d3b07483 "Learn how to authorize yourself and execute your first requests with the SAP Virtual Machine service API for the Neo environment.") :arrow_upper_right:

[Consuming the Destination Configuration Service](https://help.sap.com/viewer/b865ed651e414196b39f8922db2122c7/Cloud/en-US/30a5e88495b349e4b073313897342189.html "Retrieve destination configurations for your cloud application in the Neo environment, in a secure and reliable way.") :arrow_upper_right:

