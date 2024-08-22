<!-- loiof734755fdd9944209b68c754dd42e118 -->

# The Certificate Does Not Upload

A certificate cannot upload successfully to the SAP BTP, Neo environment when it is expired, it is not generated correctly, or its name contains an unsupported character.



<a name="loiof734755fdd9944209b68c754dd42e118__section_ajl_hsb_ybc"/>

## The Certificate Has Expired or Is Not Generated Correctly

When you are uploading a certificate, you may see the ***\(!\) ERROR: Certificate with subject \[EMAILADDRESS=mymail@example.com, CN=test.mydomain.com, O=MyCompany, C=DE\] is not valid!*** error message if:

-   The certificate has expired. See [Update an Expired Certificate](https://help.sap.com/docs/btp/sap-btp-neo-environment/update-expired-certificate).

-   The certificate isn't generated correctly or it isn't signed by a certificate authority \(CA\).

    For more information about uploading a certificate, see [Upload a Certificate](https://help.sap.com/docs/btp/sap-btp-neo-environment/configuring-custom-domains#loio55120d899d314e23ab8e33b4b388cea6).


To solve this issue, generate the certificate again.



<a name="loiof734755fdd9944209b68c754dd42e118__section_ltk_zsb_ybc"/>

## The Certificate Name Contains an Unsupported Character

You renewed your certificate. You are trying to upload it via the console client:

```
neo upload-domain-certificate --account mysubaccount --user mymail@example.com --host us1.hana.ondemand.com --name my-renewed-cert.com --location C:\Desktop\my-renewed-cert.com.pem --force
```

Unfortunately, the operation does not complete successfully and you receive the following error message:

***\(!\) ERROR: Invalid value of parameter certificate name. The value must start with a letter and can only contain lowercase letters \(a-z\), uppercase letters \(A-Z\), numbers \(0-9\), underscores \( \_ \), and hyphens \(-\).***

> ### Note:  
> If you need help, provide the output of the command and attach the log directory `[C:\Neo\tools\log]`.

The issue here is that the certificate name \(my-renewed-cert.com\) contains the "." character, which isn't allowed. The certificate name must start with a letter and can only contain lowercase letters \(a-z\), uppercase letters \(A-Z\), numbers \(0-9\), underscores \( \_ \), and hyphens \(-\).

You can try out one of these two possible solutions:

-   [Report a case](https://me.sap.com/home) with component BC-NEO-INFR and request your private key. Once you have the private key, you can upload the certificate using the `--key-location` parameter. However, this operation poses a security risk if you're uploading a certificate from a remote location. See [upload-domain-certificate](https://help.sap.com/docs/btp/sap-btp-neo-environment/upload-domain-certificate).

-   Generate a new CSR and upload the newly signed certificate. See [Using a New CSR](https://help.sap.com/docs/btp/sap-btp-neo-environment/update-expired-certificate#loio7b3d0eda8f4149ad83f46d3472687ee8).


**Related Information**  


[Experiencing Issues When Uploading Certificates](experiencing-issues-when-uploading-certificates-2518a20.md "Use these troubleshooting steps for resolving common issues and errors related to the process of uploading certificates to the SAP BTP, Neo environment.")

[Troubleshooting Guide for Custom Domains in the Neo Environment](troubleshooting-guide-for-custom-domains-in-the-neo-environment-216e0ed.md "Use this troubleshooting guide to quickly identify and resolve issues with custom domains in the SAP BTP, Neo environment.")

