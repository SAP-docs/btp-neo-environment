<!-- loio6fc4422591ea48d2bf8447ca85afb19f -->

# Uploading a Certificate Without Generating a CSR

Learn what to do if you ever need to upload a certificate from a remote location without having to run the `generate-csr` command. Keep in mind that this is not the recommended way of uploading a certificate to the SAP BTP, Neo environment.

To upload a valid certificate without generating a CSR, you must use the `--key-location` parameter in the [upload-domain-certificate](https://help.sap.com/docs/btp/sap-btp-neo-environment/upload-domain-certificate) command to upload the certificate's private key.

However, note that uploading a private key from a remote location poses a security risk. For that reason SAP recommends that you use only certificates that are based on CSRs generated via the [generate-csr](https://help.sap.com/docs/btp/sap-btp-neo-environment/generate-csr) command.

**Related Information**  


[Experiencing Issues When Uploading Certificates](experiencing-issues-when-uploading-certificates-2518a20.md "Use these troubleshooting steps for resolving common issues and errors related to the process of uploading certificates to the SAP BTP, Neo environment.")

[Troubleshooting Guide for Custom Domains in the Neo Environment](troubleshooting-guide-for-custom-domains-in-the-neo-environment-216e0ed.md "Use this troubleshooting guide to quickly identify and resolve issues with custom domains in the SAP BTP, Neo environment.")

