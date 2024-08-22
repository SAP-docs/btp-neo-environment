<!-- loiodf741234356541d08c34cc1fd1512758 -->

# Uploading an Intermediate Certificate

Learn how to organize the content in the certificate file before uploading it with the `upload-domain-certificate` command.

You are about to upload an SSL certificate using the `upload-domain-certificate` command.

The file that holds the certificate data can contain:

-   An SSL certificate:

    `-----BEGIN CERTIFICATE-----`

    `Your SSL certificate goes here.`

    `-----END CERTIFICATE-----`

-   An SSL certificate followed by an intermediate certificate:

    `-----BEGIN CERTIFICATE-----`

    `Your SSL certificate goes here.`

    `-----END CERTIFICATE-----` 

    `-----BEGIN CERTIFICATE-----`

    `Your intermediate certificate goes here.`

    `-----END CERTIFICATE-----`


If you want to upload an intermediate certificate with `upload-domain-certificate`, make sure that it goes after the SSL certificate in the certificate file.

**Related Information**  


[Experiencing Issues When Uploading Certificates](experiencing-issues-when-uploading-certificates-2518a20.md "Use these troubleshooting steps for resolving common issues and errors related to the process of uploading certificates to the SAP BTP, Neo environment.")

[Troubleshooting Guide for Custom Domains in the Neo Environment](troubleshooting-guide-for-custom-domains-in-the-neo-environment-216e0ed.md "Use this troubleshooting guide to quickly identify and resolve issues with custom domains in the SAP BTP, Neo environment.")

