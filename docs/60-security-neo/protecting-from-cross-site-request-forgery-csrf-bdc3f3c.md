<!-- loiobdc3f3c59a324be38c3e5a80dde2aa99 -->

# Protecting from Cross-Site Request Forgery \(CSRF\)

Cross-Site Request Forgery \(CSRF\) is another common type of attack on web applications.

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of the following technology portfolios: application development; process automation; integration; data, analytics, and enterprise planning; artificial intelligence. The platform offers users the ability to turn data into business value, compose end-to-end business processes, connect entire IT landscapes, and personalize, build and extend SAP applications. This reduces the overall total cost of ownership maintaining SAP landscapes and third-party software across end-to-end business processes.") :arrow_upper_right:.**

If an application connects to a REST service, the corresponding REST service must take measures to protect against CSRF. For REST services implemented on the SAP BTP a CSRF prevention filter may be used in the corresponding REST service. For more information about CSRF protection on the SAP BTP, see [Protection from Cross-Site Request Forgery](protection-from-cross-site-request-forgery-1f5f34e.md).

**Related Information**  


[Application Identity Provider](application-identity-provider-dc61853.md#loiodc618538d97610148155d97dcd123c24 "The application identity provider supplies the user base for your applications. For example, you can use your corporate identity provider for your applications. This is called identity federation. SAP BTP supports Security Assertion Markup Language (SAML) 2.0 for identity federation.")

