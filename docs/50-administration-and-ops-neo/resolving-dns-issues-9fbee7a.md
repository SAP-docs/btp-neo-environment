<!-- loio9fbee7a27112401a9ef9ac5ffd6bb764 -->

# Resolving DNS Issues

Use these troubleshooting steps to identify and fix DNS issues related to your custom domain in the SAP BTP, Neo environment.



## Context

Errors in the DNS mapping configuration may lead to unintended redirects to other applications. The most common error is using an incorrect SSL host URL of type `*.ssl.ondemand.com` when creating the DNS record.

Causes of this error may include the following:

-   A typo in the SSL host URL.

-   A different SSL host URL has been used that causes your custom domain to redirect you to another application.


Try the following steps:



## Procedure

1.  Run the [list-ssl-hosts](https://help.sap.com/docs/btp/sap-btp-neo-environment/list-ssl-hosts) command and check the available SSL host URLs:

    ***SSL hosts for subaccount 'mysubaccount': 2. Account quota: 2***

    ***\---------------------------------------------------------------------***

    ***Name : testapp***

    ***Host : EU0000000000000.ssl.ondemand.com***

    ***Certificate : testappcert***

    ***CA bundle : <none\>***

    ***Client cert : <none\>***

    ***\---------------------------------------------------------------------***

    ***Name : prodapp***

    ***Host : EU1234568901234.ssl.ondemand.com***

    ***Certificate : prodappcert***

    ***CA bundle : prodappbundle***

    ***Client cert : request***

    ***\---------------------------------------------------------------------***

2.  Make a note of the SSL host URLs and verify them using the network tools of your choice.

    Ping your custom domain, for example, demo.prodapp.com. You should see the SSL host URL that you use for production purposes, which redirects to your production application. In this case, the URL is `EU1234568901234.ssl.ondemand.com`. If the SSL host URL is different \(for example, `EU0000000000000.ssl.ondemand.com`\), then you may have mixed them up earlier.

    Some network tools also let you verify that DNS records are configured correctly.

3.  \(Optional\) If the DNS mapping is missing, configure your DNS accordingly.


**Related Information**  


[The Custom Domain Is Not Working As Expected](the-custom-domain-is-not-working-as-expected-bd64a01.md "Find the reason why your custom domain in the SAP BTP, Neo environment is not working as expected.")

[Troubleshooting Guide for Custom Domains in the Neo Environment](troubleshooting-guide-for-custom-domains-in-the-neo-environment-216e0ed.md "Use this troubleshooting guide to quickly identify and resolve issues with custom domains in the SAP BTP, Neo environment.")

