<!-- loio625f2c3e1ac541b39985e867d6b8a605 -->

# Configuring Single Sign-On

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**

You can configure the cloud platform extension integration with SAP Cloud for Customer to enable the use of applications running on top of the platform from SAP Cloud for Customer.



<a name="loio625f2c3e1ac541b39985e867d6b8a605__section_qfz_n5d_x1b"/>

## Using Identity Authentication

Identity Authentication service provides authentication, single sign-on, and on-premise integration. Identity Authentication service is closely integrated with SAP BTP, and it is offered as part of the platform.

To ensure the required security for accessing the extension applications, you need to configure the Single Sign-On between the SAP BTP extension subaccount and the SAP Cloud for Customer tenant using a SAML identity provider, for example Identity Authentication. The Single Sign-On requires both solutions to be configured as trusted SAML service providers for the Identity Authentication service and on the other side the Identity Authentication service to be configured as trusted identity provider for the two solutions.

In this scenario, the authentication to SAP Cloud for Customer extension applications is restricted to the authorized users. The identity of a user is verified by the identity provider, as specified by SAML 2.0. The identity provider, \(Identity Authentication\), stores a list of all users that are allowed to access the service provider \(SAP Cloud for Customer\) along with their credentials. The integration between the SAP Cloud for Customer and the Identity Authentication is based on trust configuration. When a user attempts to access SAP Cloud for Customer for the first time, the system redirects the user to the identity provider for identification. From then on, the user session is kept active, and the user is no longer prompted for credentials when he or she, for example, tries to use the extension application. This is called Single Sign-On \(SSO\).



<a name="loio625f2c3e1ac541b39985e867d6b8a605__section_bpd_r5d_x1b"/>

## Using Third-Party Identity Provider

You can use a third-party identity provider \(which means a different from Identity Authentication\) as well to ensure the required security for your landscape. In this case you also need to perform a few configuration tasks on all the sides - SAP BTP, SAP Cloud for Customer, and the identity provider that you are using.

**Related Information**  


[Configuring Single Sign-On Using Identity Authentication](configuring-single-sign-on-using-identity-authentication-a8a5c41.md "To ensure the required security for your landscape you need to perform a few configuration tasks on all the sides - SAP BTP, Identity Authentication and SAP Cloud for Customer.")

[Configuring Single Sign-On Using Third-Party Identity Provider](configuring-single-sign-on-using-third-party-identity-provider-0758c88.md "To ensure the required security for your landscape you need to perform a few configuration tasks on all the sides - SAP BTP, SAP Cloud for Customer, and the identity provider that you are using (if this provider is different from Identity Authentication, for which there is a dedicated section).")

