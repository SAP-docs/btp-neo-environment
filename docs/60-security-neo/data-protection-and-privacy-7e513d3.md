<!-- loio7e513d31704a4a87831191e504ca850a -->

# Data Protection and Privacy

Data protection is associated with numerous legal requirements and privacy concerns. In addition to compliance with general data protection and privacy acts, it is necessary to consider compliance with industry-specific legislation in different countries.

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**

SAP provides specific features and functions to support compliance with regard to relevant legal requirements, including data protection. SAP does not give any advice on whether these features and functions are the best method to support company, industry, regional, or country-specific requirements. Furthermore, this information should not be taken as advice or a recommendation regarding additional features that would be required in specific IT environments. Decisions related to data protection must be made on a case-by-case basis, taking into consideration the given system landscape and the applicable legal requirements.

> ### Note:  
> SAP does not provide legal advice in any form. SAP software supports data protection compliance by providing security features and specific data protection-relevant functions. In many cases, compliance with applicable data protection and privacy laws will not be covered by a product feature. Definitions and other terms used in this document are not taken from a particular legal source.

> ### Caution:  
> The extent to which data protection is supported by technical means depends on secure system operation. Network security, security note implementation, adequate logging of system changes, and appropriate usage of the system are the basic technical requirements for compliance with data privacy legislation and other legislation.



<a name="loio7e513d31704a4a87831191e504ca850a__section_zfk_r3x_h2b"/>

## Generic Fields

You also need to make sure that no personal data enters the system in an uncontrolled or non-purpose related way, for example, in free-text fields, or customer extensions.



<a name="loio7e513d31704a4a87831191e504ca850a__section_bqk_4j2_5db"/>

## SAP BTP

This documentation covers personal data relating to SAP BTP accounts and data stored in databases by SAP BTP. SAP BTP offers a number of capabilities, that is, services, buildpacks, application, and so on. Here we cover the core platform. For more information about data protection and privacy for capabilities you have purchased, see the data protection and privacy documentation for those capabilities.

To view the services consumed by a global account:

1.  Navigate to the global account to which you'd like to view members.

    For more information, see [Navigate to Orgs and Spaces](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/5bf87353bf994819b8803e5910d8450f.html "To administer your Cloud Foundry environment, navigate to orgs, and spaces in the SAP BTP cockpit.") :arrow_upper_right:.

2.  In the navigation area, choose *Entitlements*.

This documentation is written with the data protection officer of a company in mind. The processes described here may be required for a data protection officer or an administrator of the user accounts for your tenants or even business users of the tenants. In particular the processes for business users are described here so that you in your role of data protection officer or account administrator can communicate them to your business users if required.

-   Global account users are stored in platform identity provider or a tenant of SAP Cloud Identity Services - Identity Authentication.
-   Platform users are stored in platform identity provider, a tenant of SAP Cloud Identity Services - Identity Authentication, or your own identity provider.
-   Business users are stored in a tenant of SAP Cloud Identity Services - Identity Authentication or your own identity provider.

**Related Information**  


[Authorization and Trust Management in the Neo Environment](authorization-and-trust-management-in-the-neo-environment-e6b196a.md "The Neo environment of SAP BTP supports identity federation and single sign-on with external identity providers. The current section provides an overview of the supported scenarios.")

[Platform Identity Provider](platform-identity-provider-80edbe7.md "The platform identity provider is the user base for access to your SAP BTP subaccount in the Neo environment. The default user base is provided by SAP ID Service. You can switch to an Identity Authentication tenant if you want to use a custom user base.")

[OAuth 2.0 Service](oauth-2-0-service-e526ca3.md "Use OAuth 2.0 service on SAP BTP to protect applications in the Neo environment using the OAuth 2.0 protocol.")

[Keystore Service](keystore-service-a18327e.md "The Keystore Service provides a repository for cryptographic keys and certificates to the applications in the Neo environment of SAP BTP.")

[Audit Logging in the Neo Environment](audit-logging-in-the-neo-environment-02c3971.md "In this section you can find information for audit log functionalities in the SAP BTP Neo environment.")

[Principal Propagation](principal-propagation-f70fcf1.md "Exchange user ID information between systems or environments in SAP BTP.")

[Protection from Web Attacks](protection-from-web-attacks-52750a8.md "To protect your applications from different kind of web attacks, Neo environment provides mechanisms for you to use with your applications.")

[Glossary for Data Protection and Privacy](glossary-for-data-protection-and-privacy-a57e0ab.md "The following terms are general to SAP products. Not all terms may be relevant for SAP BTP.")

[Change Logging and Read-Access Logging](change-logging-and-read-access-logging-93fac8d.md "Change logging records changes to personal data, while read-access logging records access to sensitive personal data. You may be required to gather this information for auditing purposes or legal requirements.")

[Personal Data Record](personal-data-record-817f6ac.md "A personal data record is a collection of data relating to a data subject. A data privacy specialist may be required to provide such a record or an application may offer a self-service.")

[Deletion](deletion-25e3cc6.md "The processing of personal data is subject to applicable laws related to the deletion of this data when the specified, explicit, and legitimate purpose for processing this personal data has expired. If there is no longer a legitimate purpose that requires the retention and use of personal data, it must be deleted.")

[Consent](consent-419c135.md "SAP BTP supports you in collecting and managing the consent of data subjects in the following ways:")

