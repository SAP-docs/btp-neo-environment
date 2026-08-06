<!-- loiodf741234356541d08c34cc1fd1512758 -->

# Uploading an Intermediate Certificate

Learn how to organize the content in the certificate file before uploading it with the `upload-domain-certificate` command.

> ### Caution:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/docs/btp/sap-business-technology-platform/sap-business-technology-platform?version=Cloud) .**

> ### Tip:  
> Additional IP outbound addresses will soon be used in all regions in the Neo environment. For more information, see [Additional IP Addresses Added to SAP BTP, Neo Runtime Regions](https://help.sap.com/whats-new/cf0cb2cb149647329b5d02aa96303f56?version=Cloud&Component=Region&Valid_as_Of=2026-11-02:2026-11-02). To subscribe to such notifications, see SAP Note [3513325](https://me.sap.com/notes/3513325).

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

