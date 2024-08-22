<!-- loio6867afd25a7f44628f228ea5cdb6386f -->

# The Certificate Is Already Uploaded

Learn why you are getting the error message ***Certificate \[mycertificatename\] already uploaded*** and what you can do to solve this problem.

You may see the ***\(!\) ERROR: Certificate \[mycertificatename\] already uploaded*** error message if you try to upload a signed SSL certificate that is based on an existing certificate signing request \(CSR\), without using the `--force` parameter.

You can use this parameter to overwrite your current certificate, for example, if your current certificate has expired, and you want to renew it with a new certificate based on an existing CSR. See [Using an Existing CSR](https://help.sap.com/docs/btp/sap-btp-neo-environment/update-expired-certificate#loiof16731619a134670ac99915b2049d8d5).

For more information about the `upload-domain-certificate` command, see [upload-domain-certificate](https://help.sap.com/docs/btp/sap-btp-neo-environment/upload-domain-certificate).

**Related Information**  


[Getting an Error Message](getting-an-error-message-a9d40a3.md "This section provides you with some of the most commonly received error messages and what you can do to handle them.")

[Troubleshooting Guide for Custom Domains in the Neo Environment](troubleshooting-guide-for-custom-domains-in-the-neo-environment-216e0ed.md "Use this troubleshooting guide to quickly identify and resolve issues with custom domains in the SAP BTP, Neo environment.")

