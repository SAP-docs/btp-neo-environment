<!-- loio3438252775d84bdfa211e79147561c99 -->

# Security, Neo Environment

Authorization and trust management, OAuth, key and certificate management, principal propagation and other security features in the Neo Environment.

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of the following technology portfolios: application development; process automation; integration; data, analytics, and enterprise planning; artificial intelligence. The platform offers users the ability to turn data into business value, compose end-to-end business processes, connect entire IT landscapes, and personalize, build and extend SAP applications. This reduces the overall total cost of ownership maintaining SAP landscapes and third-party software across end-to-end business processes.") :arrow_upper_right:.**



<a name="loio3438252775d84bdfa211e79147561c99__section_hv2_mkx_nvb"/>

## Security Recommendations

We provide a list with our recommendations for the configuration of our services. These recommendations help you to meet your compliance goals and secure your business.

See [SAP BTP, Neo Environment Security Recommendations](https://help.sap.com/docs/btp/sap-btp-neo-environment-security-recommendations-ed2ef9c59a8245c9b9505d6bf8305cfb/sap-btp-neo-environment-security-recommendations?version=Cloud).

Our customer success organization, uses these recommendations as a base to create a security baseline template.

For more information, go to [https://support.sap.com/sos](https://support.sap.com/sos) and choose *Media Library* \> *SAP CoE Security Services - Security Baseline Template*.



<a name="loio3438252775d84bdfa211e79147561c99__section_fdb_tjv_42b"/>

## Transport Layer Security \(TLS\) Connectivity Support

Neo environment uses encrypted communication channels based on HTTPS/TLS, supporting TLS version 1.2 or higher.

Make sure you use HTTP clients \(such as Web browsers\) that support TLS version 1.2 or higher for connecting.

In the TLS headers `x-scp-tls-version` and `x-scp-tls-cipher` returned by the Neo environment, the application receives information about the TLS version and cipher with which the connection is established.

