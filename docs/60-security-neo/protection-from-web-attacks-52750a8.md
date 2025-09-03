<!-- loio52750a8f86bb428ca224daa4312d122e -->

# Protection from Web Attacks

To protect your applications from different kind of web attacks, Neo environment provides mechanisms for you to use with your applications.

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/docs/btp/sap-business-technology-platform/sap-business-technology-platform?version=Cloud) .**



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

