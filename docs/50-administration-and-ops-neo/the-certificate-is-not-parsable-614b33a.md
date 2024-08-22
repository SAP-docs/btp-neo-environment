<!-- loio614b33a33d8d40a6ab287defc1f68628 -->

# The Certificate Is Not Parsable

Learn why you are getting the error message ***Certificate \[mycertificatename\] in subaccount \[mysubaccountname\] is not parsable*** and what you can do to solve this problem.

You may see the ***\(!\) ERROR: Certificate \[mycertificatename\] in subaccount \[mysubaccountname\] is not parsable*** error message if the uploaded certificate is not in the correct format.

Make sure that you upload the certificate in PEM format according to the following template:

`-----BEGIN CERTIFICATE-----`

`Your certificate goes here.`

`-----END CERTIFICATE-----`

See SAP KBA [2701097 - ERROR: Certificate XXX in subaccount XXX is not parsable](https://me.sap.com/notes/2701097).

**Related Information**  


[Getting an Error Message](getting-an-error-message-a9d40a3.md "This section provides you with some of the most commonly received error messages and what you can do to handle them.")

[Troubleshooting Guide for Custom Domains in the Neo Environment](troubleshooting-guide-for-custom-domains-in-the-neo-environment-216e0ed.md "Use this troubleshooting guide to quickly identify and resolve issues with custom domains in the SAP BTP, Neo environment.")

