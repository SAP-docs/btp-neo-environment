<!-- loioa2269055d0014c8d854b47d5db531a04 -->

# Frequently Asked Questions

Answers to some of the most commonly asked questions about SAP Custom Domain service.



> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**



<a name="loioa2269055d0014c8d854b47d5db531a04__section_bk1_4gx_mfb"/>

## How many domains \(URLs\) do I get to use for one custom domain?

For each custom domain that you purchase, you can create one SSL host and you can upload up to four certificates. Then, you can bind only one of these certificates to that SSL host for production purposes. The number of domains \(URLs\) that you can use with that single domain certificate depends on the certificate type:

-   If the certificate is issued for a specific domain name \(for example, `webshop.acme.com`\), you can use **one domain**.

-   If you use a wildcard certificate \(for example, \*.acme.com\), the certificate is valid for **all subdomains** of `acme.com`.

    > ### Note:  
    > Using a wildcard certificate allows you to map a large number of subdomains mapped to a single SSL host. However, this feature comes with several disadvantages:
    > 
    > -   If the certificate suffers from a security breach, it can affect all applications hosted on these subdomains.
    > 
    > -   If the HTTP traffic is too massive, it may cause performance issues for all applications hosted on these subdomains.
    > 
    >     If there are too many custom domain mappings, consider using more SSL hosts to reduce the HTTP traffic load.

-   If you use a Subject Alternative Names \(SAN\) certificate, you can use **many domains**. This type of certificate is usually used when multiple aliases of the same application are needed. For example, `www.acme.com`, `www.login.acme.com`.


> ### Note:  
> Each of these options has pros and cons. It's up to you to decide which type of certificate you are going to use.

For more information, see [Prerequisites](prerequisites-cde2547.md).



<a name="loioa2269055d0014c8d854b47d5db531a04__section_q3c_n24_nkb"/>

## How many certificates can I upload?

One custom domain quota allows you to upload up to four certificates. However, you can use only one of the uploaded certificates for production purposes.



<a name="loioa2269055d0014c8d854b47d5db531a04__section_i1w_y3w_mfb"/>

## I can't configure a custom domain for my SAP Cloud Integration application. What should I do?

For SAP Cloud Integration applications, there are some differences in the procedure. When you map the custom domain to the Cloud Integration URL, keep in mind that the URL consists of several URL elements. You can find these URL elements in the cockpit. For more information, see [Configuring Custom Domains for SAP Cloud Integration](https://help.sap.com/viewer/368c481cd6954bdfa5d0435479fd4eaf/Cloud/en-US/7230b9ff41914cc0969223e6a020104b.html).



<a name="loioa2269055d0014c8d854b47d5db531a04__section_hwv_x3h_2jb"/>

## After I configure a custom domain for my application, can I still use the default hana.ondemand.com URL?

It depends. The default `hana.ondemand.com` URL remains accessible **only if the application is part of a subscription**. This type of applications has the following URL format: `https://<application_name><provider_subaccount>-<consumer_subaccount>.<domain>`. If needed, you can disable the access to the default `hana.ondemand.com` URL with the `--disable-application-url` parameter of the [add-custom-domain](add-custom-domain-ebc5269.md) command. For more information, see [Custom Domains for Multitenant Applications](custom-domains-for-multitenant-applications-b2b5dcc.md).

In all other cases, the default `hana.ondemand.com` becomes inaccessible and cannot be used along with the configured custom domain URL.



<a name="loioa2269055d0014c8d854b47d5db531a04__section_owp_sfw_mfb"/>

## Is there a troubleshooting guide for custom domains?

Yes, there is. If you are facing a technical issue and you are not sure how to proceed, see [Guided Answers](https://ga.support.sap.com/dtp/viewer/index.html#/tree/2065/actions/26547:27935).

**Related Information**  


[Using Custom Domains](using-custom-domains-98e655a.md "SAP Custom Domain service allows subaccount owners to make their SAP BTP applications accessible via a custom domain that is different from the default one (hana.ondemand.com) - for example www.myshop.com.")

[Configuring Custom Domains](configuring-custom-domains-77cf0e6.md#loio77cf0e6cd32e496c9cc8eeac4bedde94 "To make sure that your domain is trusted and all application data is protected, you need to first set up secure SSL communication. The next step will then be to make your application accessible via the custom domain and route traffic to it.")

