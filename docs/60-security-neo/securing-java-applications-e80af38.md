<!-- loioe80af38cbb57101495e2cd74c44af674 -->

# Securing Java Applications

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**



<a name="loioe80af38cbb57101495e2cd74c44af674__section_N10016_N10013_N10001"/>

## SAML 2.0 Authentication

SAP BTP uses the Security Assertion Markup Language \(SAML\) 2.0 protocol for authentication and single sign-on.

By default, SAP BTP is configured to use SAP ID service as identity provider \(IdP\), as specified in SAML 2.0. You can configure trust to your custom IdP, to provide access to the cloud using your own user database.



<a name="loioe80af38cbb57101495e2cd74c44af674__section_N10027_N10013_N10001"/>

## Java EE Identity and Access Management

SAP ID Service provides Identity and Access Management for Java EE Web applications hosted on SAP BTP through the mechanisms described in Java EE Servlet specification and through dedicated APIs.



<a name="loioe80af38cbb57101495e2cd74c44af674__section_N10034_N10013_N10001"/>

## Protecting Applications from Cross-Site Scripting \(XSS\)

Cross-site Scripting \(XSS\) is one of the most common types of malicious attacks to Web applications. In order to help protecting against this type of attacks, SAP BTP provides a common output encoding library to be used from applications.



<a name="loioe80af38cbb57101495e2cd74c44af674__section_77C5C78D95314EBBA1849E1CF3CFDB84"/>

## Protecting from Cross-Site Request Forgery \(CSRF\)

Cross-Site Request Forgery \(CSRF\) is another common type of attack to Web applications. You can protect applications running on SAP BTP from CSRF, based on the Tomcat Prevention Filter.

