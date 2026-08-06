<!-- loio6867afd25a7f44628f228ea5cdb6386f -->

# The Certificate Is Already Uploaded

Learn why you are getting the error message ***Certificate \[mycertificatename\] already uploaded*** and what you can do to solve this problem.

> ### Caution:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/docs/btp/sap-business-technology-platform/sap-business-technology-platform?version=Cloud) .**

> ### Tip:  
> Additional IP outbound addresses will soon be used in all regions in the Neo environment. For more information, see [Additional IP Addresses Added to SAP BTP, Neo Runtime Regions](https://help.sap.com/whats-new/cf0cb2cb149647329b5d02aa96303f56?version=Cloud&Component=Region&Valid_as_Of=2026-11-02:2026-11-02). To subscribe to such notifications, see SAP Note [3513325](https://me.sap.com/notes/3513325).

You may see the ***\(!\) ERROR: Certificate \[mycertificatename\] already uploaded*** error message if you try to upload a signed SSL certificate that is based on an existing certificate signing request \(CSR\), without using the `--force` parameter.

You can use this parameter to overwrite your current certificate, for example, if your current certificate has expired, and you want to renew it with a new certificate based on an existing CSR. See [Using an Existing CSR](https://help.sap.com/docs/btp/sap-btp-neo-environment/update-expired-certificate#loiof16731619a134670ac99915b2049d8d5).

For more information about the `upload-domain-certificate` command, see [upload-domain-certificate](https://help.sap.com/docs/btp/sap-btp-neo-environment/upload-domain-certificate).

**Related Information**  


[Getting an Error Message](getting-an-error-message-a9d40a3.md "This section provides you with some of the most commonly received error messages and what you can do to handle them.")

[Troubleshooting Guide for Custom Domains in the Neo Environment](troubleshooting-guide-for-custom-domains-in-the-neo-environment-216e0ed.md "Use this troubleshooting guide to quickly identify and resolve issues with custom domains in the SAP BTP, Neo environment.")

