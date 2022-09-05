<!-- loio52750a8f86bb428ca224daa4312d122e -->

# Protection from Web Attacks

To protect your applications from different kind of web attacks, Neo environment provides mechanisms for you to use with your applications.

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**



<a name="loio52750a8f86bb428ca224daa4312d122e__section_wnf_c5j_4kb"/>

## Cross-Site Scripting \(XSS\)

XSS attacks allow the attacker to inject malicious code into a web application. See [Protection from Cross-Site Scripting \(XSS\)](protection-from-cross-site-scripting-xss-e643316.md).



<a name="loio52750a8f86bb428ca224daa4312d122e__section_jp1_d5j_4kb"/>

## Cross-Site Request Forgery \(CSRF\)

With a CSRF attack, a malicious user tricks the victim’s browser into executing an HTTP request on behalf of the valid user. See [Protection from Cross-Site Request Forgery](protection-from-cross-site-request-forgery-1f5f34e.md).



<a name="loio52750a8f86bb428ca224daa4312d122e__section_qry_d5j_4kb"/>

## Slow HTTP Attacks

**Slow HTTP attacks** happen when the attacker sends very slowly content in the server request one at a time to a Web server. If an HTTP request is not complete, or if the transfer rate is very low, the server keeps its resources busy waiting for the rest of the data. When the server’s concurrent connection pool reaches its maximum, this creates a denial-of-service \(DoS\). Slow HTTP attacks are easy to execute because they require only minimal resources from the attacker.

> ### Tip:  
> We recommend that you configure your applications to support connection timeout suitable for your network setup and application use case. Although you cannot completely avoid the threat of slow HTTP attacks, using this configuration can lower the chance of successfully executed attacks. Make sure you don’t make connection timeout too small so you allow enough timeout for handling normal network latency.
> 
> Configuring connection timeout is done at deploy time \(using the `--connection-timeout` command parameter\). See [deploy](../50-administration-and-ops-neo/deploy-937db4f.md).

**Related Information**  


[Authorization and Trust Management in the Neo Environment](authorization-and-trust-management-in-the-neo-environment-e6b196a.md "The Neo environment of SAP BTP supports identity federation and single sign-on with external identity providers. The current section provides an overview of the supported scenarios.")

[Platform Identity Provider](platform-identity-provider-80edbe7.md "The platform identity provider is the user base for access to your SAP BTP subaccount in the Neo environment. The default user base is provided by SAP ID Service. You can switch to an Identity Authentication tenant if you want to use a custom user base.")

[OAuth 2.0 Service](oauth-2-0-service-e526ca3.md "Use OAuth 2.0 service on SAP BTP to protect applications in the Neo environment using the OAuth 2.0 protocol.")

[Keystore Service](keystore-service-a18327e.md "The Keystore Service provides a repository for cryptographic keys and certificates to the applications in the Neo environment of SAP BTP.")

[Audit Logging in the Neo Environment](audit-logging-in-the-neo-environment-02c3971.md "In this section you can find information for audit log functionalities in the SAP BTP Neo environment.")

[Principal Propagation](principal-propagation-f70fcf1.md "Exchange user ID information between systems or environments in SAP BTP.")

[Data Protection and Privacy](data-protection-and-privacy-7e513d3.md "Data protection is associated with numerous legal requirements and privacy concerns. In addition to compliance with general data protection and privacy acts, it is necessary to consider compliance with industry-specific legislation in different countries.")

