<!-- loiod7923adc2a284b148f59494ac0d18aa6 -->

# Security

This section describes the security aspects that are relevant for SAP Solutions Lifecycle Management Service.



<a name="loiod7923adc2a284b148f59494ac0d18aa6__section_dsb_xyb_zwb"/>

## Application Logging

Application logs capture the technical flow of the code. They log exceptions and the technical reasons behind them. They are deleted in 7 days.



<a name="loiod7923adc2a284b148f59494ac0d18aa6__section_t3p_zyb_zwb"/>

## SAP Solutions Lifecycle Management Service Roles

To operate a solution you require at least one of the following roles in your subaccount:

-   Default role *Administrator*

-   Default role *Developer*

-   A custom role with all following permissions: `manageMultiTargetApplication`, `readMultiTargetApplication`, `readJavaApplications`, and `manageJavaApplications`.

    For more information about custom roles, see [Managing Roles](https://help.sap.com/docs/btp/sap-btp-neo-environment/managing-roles?locale=en-US&version=Cloud) and [Manage Custom Platform Roles](https://help.sap.com/docs/btp/sap-btp-neo-environment/manage-custom-platform-roles?locale=en-US&version=Cloud).




<a name="loiod7923adc2a284b148f59494ac0d18aa6__section_pvb_pyc_zwb"/>

## Identity and Access Management

SAP BTP standard security concepts are incorporated to protect the SAP Solutions Lifecycle Management Service to avoid unauthorized access. Applications that use SAP Solutions Lifecycle Management Service are responsible for authorizing calls to the API instances.



<a name="loiod7923adc2a284b148f59494ac0d18aa6__section_kdl_1hd_zwb"/>

## Network and Communication Security

SAP Solutions Lifecycle Management Service uses the HTTPS protocol to encrypt communication between the service and calling application.



<a name="loiod7923adc2a284b148f59494ac0d18aa6__section_djv_dhd_zwb"/>

## Data Protection and Privacy

For general information about data protection and privacy on SAP BTP, see the SAP BTP documentation under [Data Protection and Privacy](https://help.sap.com/docs/btp/sap-business-technology-platform/data-protection-and-privacy?version=Cloud).

The following topics are related to data protection and require appropriate technical and organizational measures:

-   Access control.
-   Separation by purpose: Is subject to the organizational model implemented and must be applied as part of the authorization concept.



<a name="loiod7923adc2a284b148f59494ac0d18aa6__section_urm_43d_zwb"/>

## Personal Data processed by SAP Solutions Lifecycle Management Service

SAP Solutions Lifecycle Management Service records all tenant processes related to Solutions management like deployments, subscriptions, updates and remove operations. They’re recorded together with the user who performs the action and the time when it was done. Doing so, the user is identified by its user ID, maintained in the configured identity provider, and used during login. Sensitive personal data isn’t processed by the service.

SAP Solutions Lifecycle Management Service stores file names, and displays them in the logs. In addition, the service transfers files to the connected deployment services. Do not use any personal data in names of files that are uploaded to the service. This is also true for MTA extension descriptors.



<a name="loiod7923adc2a284b148f59494ac0d18aa6__section_cvw_fkd_zwb"/>

## Personal Data Encapsulation

SAP Solutions Lifecycle Management Service ensures that tenant-specific content is stored in a separate schema so that this data isn’t visible in other tenants.



<a name="loiod7923adc2a284b148f59494ac0d18aa6__section_yvk_yqd_zwb"/>

## Deletion of Personal Data

The tenant-specific and user-specific persistency as done by SAP Solutions Lifecycle Management Service is related to the lifecycle of the tenant subscribed to the service. The records are required to fulfill auditability requirements. The deletion of all data is performed as part of the offboarding process or no longer than 7 days after record is done.

