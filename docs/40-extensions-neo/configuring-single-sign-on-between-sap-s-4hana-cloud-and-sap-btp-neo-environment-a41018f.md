<!-- loioa41018fe263f4f078389ab08d3cf6115 -->

# Configuring Single Sign-On Between SAP S/4HANA Cloud and SAP BTP, Neo Environment

You configure the integration between SAP BTP, Neo environment and SAP S/4HANA Cloud to allow the SAP S/4HANA Cloud side-by-side extension applications to run on top of the cloud platform.



## Context

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**

Identity Authentication provides authentication, single sign-on \(SSO\), and on-premise integration. Identity Authentication service is closely integrated with SAP BTP, and it is offered as part of the platform.

To ensure the required security for accessing the applications, you need to configure SSO between the subaccount in SAP BTP and the SAP S/4HANA Cloud tenant using a SAML identity provider, for example Identity Authentication. The SSO requires both solutions to be configured as trusted SAML service providers for the Identity Authentication service, and at the same time, the Identity Authentication service to be configured as trusted identity provider for the two solutions.

> ### Note:  
> You own an SAP S/4HANA Cloud tenant with an Identity Authentication tenant configured. You need to use the same Identity Authentication tenant for your subaccount in SAP BTP.



<a name="loioa41018fe263f4f078389ab08d3cf6115__steps_lk3_www_4lb"/>

## Procedure

1.  Configure SSO between the subaccount in SAP BTP and the SAP S/4HANA Cloud tenant using Identity Authentication as an identity provider. For more information, see [Identity Authentication Tenant as an Application Identity Provider](../60-security-neo/identity-authentication-tenant-as-an-application-identity-provider-d3df5b4.md).




<a name="loioa41018fe263f4f078389ab08d3cf6115__result_bk5_hrx_4lb"/>

## Results

The trust will be established automatically upon registration on both the SAP BTP, Neo environment and the tenant for Identity Authentication service side with the following default configuration settings:

-   Principal propagation: disabled

    If needed, you can enable it. To do so, choose *Principal Propagation* \> *Enable*.

    If enabled, this option enables applications to propagate principal information to each other. Choose this value if you want to enable application-to-application SSO for applications running in the subaccount. Otherwise, set this option to *Disabled*.

-   *Login Name* name is not set as a logon identifier for your users. If needed, you can enable it. For more information, see [Configure Logon Identifiers](https://help.sap.com/viewer/6d6d63354d1242d185ab4830fc04feb1/Cloud/en-US/3adf1ff526d74486a93660cdb0b5d2dd.html?q=login%20name).


Alternatively, you can configure SSO between the Identity Authentication tenant and SAP BTP, Neo environment manually. For more information, see [Optional: Configure Single-Sign On Manually](optional-configure-single-sign-on-manually-789a120.md).

> ### Tip:  
> We recommend that you use the manual configuration only if the automated configuration is not possible. For example, if you are not authorized to access the Identity Authentication tenant.

