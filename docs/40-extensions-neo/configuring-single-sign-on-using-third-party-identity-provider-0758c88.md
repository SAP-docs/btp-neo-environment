<!-- loio0758c8811a0541699bed2942b3bd3654 -->

# Configuring Single Sign-On Using Third-Party Identity Provider

To ensure the required security for your landscape you need to perform a few configuration tasks on all the sides - SAP BTP, SAP Cloud for Customer, and the identity provider that you are using \(if this provider is different from Identity Authentication, for which there is a dedicated section\).



## Context

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**



## Procedure

1.  Set up trust between your identity provider and SAP Cloud for Customer system.

    For more information, see section **Configure Your Solution for Single Sign-On** in the [SAP Cloud for Customer Security Guide](https://help.sap.com/doc/5ec18cc14cb041bba15eb64e52227387/CLOUD/en-US/C4CSecurityGuide.pdf).

2.  Set up trust between your identity provider and SAP BTP.

    For more information, see [Application Identity Provider](../60-security-neo/application-identity-provider-dc61853.md#loiodc618538d97610148155d97dcd123c24).


