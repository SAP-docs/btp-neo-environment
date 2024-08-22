<!-- loio959a0a63b885420a976afc9c0ed3fec8 -->

# Requesting and Signing a Certificate

Requesting and signing an SSL certificate is an important step in configuring a custom domain in the SAP BTP, Neo environment. Learn what you need to do to complete this step.

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

