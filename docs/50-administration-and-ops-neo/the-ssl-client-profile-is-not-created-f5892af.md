<!-- loiof5892afeed7848a39a2ab18422737fe5 -->

# The SSL Client Profile Is Not Created

Learn why you are getting the error message ***Failed to create ssl client profile \[XXX\_<ssl-host\>\] for certificate \[XXX\_.Y.Z.pem\]!*** and what you can do to solve this problem.

You receive the ***\(!\) ERROR: Failed to create ssl client profile \[XXX\_<ssl-host\>\] for certificate \[XXX\_.Y.Z.pem\]!*** error message when you are in the process of configuring a custom domain and you run the `bind-domain-certificate` console command.

It's possible that the name of the certificate you use contains an unsupported character. Check if the name of your certificate contains any unsupported characters. The certificate name must start with a letter and can only contain lowercase letters \(a-z\), uppercase letters \(A-Z\), numbers \(0-9\), underscores \( \_ \), and hyphens \(-\).

See [generate-csr](https://help.sap.com/docs/btp/sap-btp-neo-environment/generate-csr) and SAP KBA [2812622 - ERROR: The provided private key and certificate do not match. Check again both files](https://me.sap.com/notes/2812622).

**Related Information**  


[bind-domain-certificate](https://help.sap.com/docs/btp/sap-btp-neo-environment/bind-domain-certificate)

[Getting an Error Message](getting-an-error-message-a9d40a3.md "This section provides you with some of the most commonly received error messages and what you can do to handle them.")

[Troubleshooting Guide for Custom Domains in the Neo Environment](troubleshooting-guide-for-custom-domains-in-the-neo-environment-216e0ed.md "Use this troubleshooting guide to quickly identify and resolve issues with custom domains in the SAP BTP, Neo environment.")

