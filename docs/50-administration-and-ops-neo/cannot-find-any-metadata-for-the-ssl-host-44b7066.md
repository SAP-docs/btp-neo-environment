<!-- loio44b70667c27244f7b3220c280fcf6d17 -->

# Cannot Find Any Metadata for the SSL Host

Learn why you are getting the error message ***Could not find metadata for ssl host \[\*.ssl.ondemand.com\]!*** and what you can do to solve this problem.



## Context

The metadata for your SSL host can't be found, because `EU1234568901234.ssl.ondemand.com` isn't the name of the host.

You may see the ***\(!\) ERROR: Could not find metadata for ssl host \[EU1234568901234.ssl.ondemand.com\]!*** error message when you try to bind your certificate to the SSL host by running the `bind-domain-certificate` command. To ensure that the binding is successful, enter the name of the SSL host in the `--ssl-host` parameter field.

To verify that you are using the correct SSL host name, follow these steps:



## Procedure

1.  Run the [list-ssl-hosts](https://help.sap.com/docs/btp/sap-btp-neo-environment/list-ssl-hosts) command:

    -   If you find your SSL host, copy the value of the `Name` property. In the example below, the name of the SSL host is "mysslhostname":

        ***\---------------------------------------------------------------------***

        ***Name : mysslhostname***

        ***Host : EU1234568901234.ssl.ondemand.com***

        ***Certificate : mycertificatename***

        ***\---------------------------------------------------------------------***

        > ### Note:  
        > You'll need the value of the `Host` property \(for example, `EU1234568901234.ssl.ondemand.com`\) later when you configure the DNS mapping of your application.

    -   If you don’t find your SSL host, create a new one by following the steps in [Create an SSL Host](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/77cf0e6cd32e496c9cc8eeac4bedde94.html#loio70f4d19d3dbd434aa9aa165d53e2896c).


2.  Now that you have the name of the host \(for example, mysslhostname\), run the `bind-domain-certificate` command.


**Related Information**  


[Getting an Error Message](getting-an-error-message-a9d40a3.md "This section provides you with some of the most commonly received error messages and what you can do to handle them.")

[Troubleshooting Guide for Custom Domains in the Neo Environment](troubleshooting-guide-for-custom-domains-in-the-neo-environment-216e0ed.md "Use this troubleshooting guide to quickly identify and resolve issues with custom domains in the SAP BTP, Neo environment.")

