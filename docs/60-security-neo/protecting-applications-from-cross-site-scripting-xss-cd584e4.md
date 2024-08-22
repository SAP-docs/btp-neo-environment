<!-- loiocd584e4c02054c6cb6360a439d6c8364 -->

# Protecting Applications from Cross-Site Scripting \(XSS\)

Cross-site scripting \(XSS\) is one of the most common types of malicious attacks on web applications.

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of the following technology portfolios: application development; process automation; integration; data, analytics, and enterprise planning; artificial intelligence. The platform offers users the ability to turn data into business value, compose end-to-end business processes, connect entire IT landscapes, and personalize, build and extend SAP applications. This reduces the overall total cost of ownership maintaining SAP landscapes and third-party software across end-to-end business processes.") :arrow_upper_right:.**

If an HTML5 application is connected to a REST service, the corresponding REST service must take measures to protect the application against this type of vulnerabilities. For REST services implemented on the SAP BTP a common output encoding library may be used to protect applications. For more information about XSS protection on the SAP BTP, see [Protection from Cross-Site Scripting \(XSS\)](protection-from-cross-site-scripting-xss-e643316.md).

