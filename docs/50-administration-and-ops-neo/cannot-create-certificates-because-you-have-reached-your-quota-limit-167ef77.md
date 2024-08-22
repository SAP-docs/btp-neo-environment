<!-- loio167ef774845a44cea340c67c522473ba -->

# Cannot Create Certificates Because You Have Reached Your Quota Limit

Learn why you are getting the error message ***Cannot create certificates because you have reached your quota limit*** and what you can do to solve this problem.



## Context

You may receive the ***\(!\) ERROR: Cannot create certificates because you have reached your quota limit*** error message if you try to generate a certificate signing request \(CSR\).

Depending on the number of custom domains you've purchased, you can generate a limited number of certificate signing requests \(CSRs\) using the[generate-csr](https://help.sap.com/docs/btp/sap-btp-neo-environment/generate-csr) command. You can delete the certificates that you no longer use by following these steps:



## Procedure

1.  Run the [list-domain-certificates](https://help.sap.com/docs/btp/sap-btp-neo-environment/list-domain-certificates) and [list-ssl-hosts](https://help.sap.com/docs/btp/sap-btp-neo-environment/list-ssl-hosts) commands.

    To free quota, compare the output of both commands and delete the certificates that aren’t in use or that you don’t need. You can delete a certificate using the[delete-domain-certificate](https://help.sap.com/docs/btp/sap-btp-neo-environment/delete-domain-certificate) command.

2.  Run the `generate-csr` command.


**Related Information**  


[SAP KBA 2675626 - "Cannot create certificates because you have reached your quota limit" during certificate creation](https://me.sap.com/notes/2675626)

[Getting an Error Message](getting-an-error-message-a9d40a3.md "This section provides you with some of the most commonly received error messages and what you can do to handle them.")

[Troubleshooting Guide for Custom Domains in the Neo Environment](troubleshooting-guide-for-custom-domains-in-the-neo-environment-216e0ed.md "Use this troubleshooting guide to quickly identify and resolve issues with custom domains in the SAP BTP, Neo environment.")

