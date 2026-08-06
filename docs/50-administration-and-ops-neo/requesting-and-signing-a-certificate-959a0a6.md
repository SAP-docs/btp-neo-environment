<!-- loio959a0a63b885420a976afc9c0ed3fec8 -->

# Requesting and Signing a Certificate

Requesting and signing an SSL certificate is an important step in configuring a custom domain in the SAP BTP, Neo environment. Learn what you need to do to complete this step.

> ### Caution:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/docs/btp/sap-business-technology-platform/sap-business-technology-platform?version=Cloud) .**

> ### Tip:  
> Additional IP outbound addresses will soon be used in all regions in the Neo environment. For more information, see [Additional IP Addresses Added to SAP BTP, Neo Runtime Regions](https://help.sap.com/whats-new/cf0cb2cb149647329b5d02aa96303f56?version=Cloud&Component=Region&Valid_as_Of=2026-11-02:2026-11-02). To subscribe to such notifications, see SAP Note [3513325](https://me.sap.com/notes/3513325).

By default, the SSL certificate isn't issued or signed by SAP. When you configure a custom domain, it is recommended to generate a certificate signing request \(CSR\) using the `generate-csr` console command.

Here is a brief overview of the procedure for configuring a custom domain and the role of the SSL certificate:

1.  You generate a certificate signing request \(CSR\) using the `generate-csr` console command.

2.  After that, you send the generated CSR to a certificate authority \(CA\) of your choice.

3.  The CA signs and sends you back the SSL certificate.

4.  Then, you upload the signed certificate to SAP BTP and you bind it to the SSL host.


For more details, see [Configuring Custom Domains](configuring-custom-domains-77cf0e6.md#loio77cf0e6cd32e496c9cc8eeac4bedde94).

**Related Information**  


[generate-csr](generate-csr-f02258d.md "Generates and returns a certificate signing request (CSR).")

[Troubleshooting Guide for Custom Domains in the Neo Environment](troubleshooting-guide-for-custom-domains-in-the-neo-environment-216e0ed.md "Use this troubleshooting guide to quickly identify and resolve issues with custom domains in the SAP BTP, Neo environment.")

