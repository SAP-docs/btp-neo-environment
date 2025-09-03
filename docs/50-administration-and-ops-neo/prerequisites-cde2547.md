<!-- loiocde25474fcc1424db48ad86eb2ba9502 -->

# Prerequisites

Before configuring an SAP custom domain, you need to perform some preliminary steps and fulfill a number of prerequisites.

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/docs/btp/sap-business-technology-platform/sap-business-technology-platform?version=Cloud) .**

> ### Note:  
> If you want to configure a custom domain for an SAP Cloud Integration application, see [Configuring Custom Domains for SAP Cloud Integration](https://help.sap.com/viewer/368c481cd6954bdfa5d0435479fd4eaf/Cloud/en-US/7230b9ff41914cc0969223e6a020104b.html).



## 1. Buy a custom domain quota

You need to have a quota for domains configured for your global account. One custom domain quota corresponds to one SSL host that you can use. For more information, see [Sign up for a Customer Account](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/d61c2819034b48e68145c45c36acba6e.html#loioa71a081b39e343e097046bf487f57af3 "A customer account is an enterprise account that allows you to host productive, business-critical applications with 24x7 support.") :arrow_upper_right:.

> ### Note:  
> Once you have the quota configured for your global account, you can use it in each of its subaccounts.

The following two steps involve external service providers - domain name registrar and certificate authority.

> ### Note:  
> The domain name and the server certificate for this domain are issued by external authorities and owned by the customer.



## 2. Choose and buy the domain names to be used by your applications

You need to come up with a list of custom domains and applications that you want to be served through them. For example, you may decide to have three custom domains: `test.myshop.com`, `preview.myshop.com`, `www.myshop.com` - for test, preview, and productive versions of your SAP BTP application.

The domain names are owned by the customer, not by SAP BTP. Therefore, you will need to buy the custom domain names that you have chosen from a registrar selling domain names.



## 3. Choose an SSL certificate

To make sure that your domain is trusted and all your application data is protected, you have to get an appropriate SSL certificate from a Certificate Authority \(CA\).

You need to decide on the number and type of domains you want to be protected by this certificate. One SSL host can hold one SSL certificate. One certificate can be valid for a number of domains and subdomains.

There are various types of SSL certificates. Depending on your needs, you can choose between:

-   **Standard certificate** - protects one domain \(for example, `www.myshop.com`\)
-   **Wildcard certificate** - secures multiple subdomains of a domain \(for example, `*.myshop.com` - this covers any subdomains of `myshop.com` - for example, `test.myshop.com`, `preview.myshop.com`, `www.myshop.com`\).

    > ### Note:  
    > Choosing the wildcard subdomain certificate ensures protection of all subdomains in your custom domain \(`*.myshop.com`\), but not the domain itself \(`myshop.com` cannot be used\).

    Using a wildcard certificate allows you to map a large number of subdomains mapped to a single SSL host. However, this feature comes with several disadvantages:

    -   If the certificate suffers from a security breach, it can affect all applications hosted on these subdomains.

    -   If the HTTP traffic is too massive, it may cause performance issues for all applications hosted on these subdomains.

        If there are too many custom domain mappings, consider using more SSL hosts to reduce the HTTP traffic load.


-   **Subject Alternative Name \(SAN\) certificate** - secures multiple domain names with a single certificate. This type allows you to use any number of different domain names or common names. For example, one certificate can support: `www.myshop.com`, `*.test.myshop.com`, `*.myshop.eu`, `www.myshop.de`.



<a name="loiocde25474fcc1424db48ad86eb2ba9502__section_a2c_qqf_scb"/>

## 4. Generate a CSR

To issue an SSL certificate and sign it with the CA of your choice, you need a certificate signing request \(CSR\). You must create the CSR using our `generate-csr` command. For more information, see [generate-csr](generate-csr-f02258d.md).

> ### Caution:  
> The CSR is valid only for the host on which it was generated and cannot be moved and downloaded. The host represents the region: for example, *hana.ondemand.com* for Europe; *us1.hana.ondemand.com* for the United States; *ap1.hana.ondemand.com* for Asia-Pacific, and so on.



<a name="loiocde25474fcc1424db48ad86eb2ba9502__section_of5_rqf_scb"/>

## 5. Issue the SSL certificate

Use the CA of your choice to sign the CSR. The certificate has to be in Privacy-enhanced Electronic Mail \(PEM\) format \(128 or 256 bits\) with private key \(2048-4096 bits\).

**Related Information**  


[Install the SAP BTP SDK for Neo Environment](../30-development-neo/install-the-sap-btp-sdk-for-neo-environment-7613843.md)

[Set Up the Console Client](../30-development-neo/set-up-the-console-client-7613dee.md)

[Using the Console Client](using-the-console-client-8900b22.md "You execute a console client command by entering neo <command name> with the appropriate parameters. To list all parameters available for the respective command, execute neo help <command name>.")

[Configuring Custom Domains](configuring-custom-domains-77cf0e6.md#loio77cf0e6cd32e496c9cc8eeac4bedde94 "To make sure that your domain is trusted and all application data is protected, you need to first set up secure SSL communication. The next step will then be to make your application accessible via the custom domain and route traffic to it.")

[Guided Answers \(Neo Environment\)](https://ga.support.sap.com/dtp/viewer/index.html#/tree/2065/actions/26547:34945:27935)

[Frequently Asked Questions](frequently-asked-questions-a226905.md "Answers to some of the most commonly asked questions about SAP Custom Domain service.")

