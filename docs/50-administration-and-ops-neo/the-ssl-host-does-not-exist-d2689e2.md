<!-- loiod2689e29d1304e82ba5df23310d45ef1 -->

# The SSL Host Does Not Exist

Learn why you are getting the error message ***SSL host '\*.ssl.ondemand.com' does not exist*** and what you can do to solve this problem.



## Context

When you receive the ***\(!\) ERROR: SSL host 'EU1234568901234.ssl.ondemand.com' does not exist*** error message, note that `EU1234568901234.ssl.ondemand.com` isn't the name of the host.

You may see this error when you try to bind your certificate to the SSL host by running the[bind-domain-certificate](https://help.sap.com/docs/btp/sap-btp-neo-environment/bind-domain-certificate) command.To ensure that the binding is successful, enter the name of the SSL host in the `--ssl-host` parameter field.

To verify that you are using the correct SSL host name, follow these steps:



## Procedure

1.  Run the `list-ssl-hosts` command:

    -   If you find your SSL host, copy the value of the `Name` property; in the example below "mysslhostname":

        ***\---------------------------------------------------------------------***

        ***Name : mysslhostname***

        ***Host : EU1234568901234.ssl.ondemand.com***

        ***Certificate : mycertificatename***

        ***\---------------------------------------------------------------------***

        Note: You'll need the value of the Host property \(for example, `EU1234568901234.ssl.ondemand.com`\) later when you configure the DNS mapping of your application.

    -   If you don’t find your SSL host, create a new one by following the steps in [Create an SSL Host](https://help.sap.com/docs/btp/sap-btp-neo-environment/configuring-custom-domains#loio70f4d19d3dbd434aa9aa165d53e2896c).


2.  Now that you have the name of the host \(for example, mysslhostname\), execute the `bind-domain-certificate` command.


**Related Information**  


[Getting an Error Message](getting-an-error-message-a9d40a3.md "This section provides you with some of the most commonly received error messages and what you can do to handle them.")

[Troubleshooting Guide for Custom Domains in the Neo Environment](troubleshooting-guide-for-custom-domains-in-the-neo-environment-216e0ed.md "Use this troubleshooting guide to quickly identify and resolve issues with custom domains in the SAP BTP, Neo environment.")

