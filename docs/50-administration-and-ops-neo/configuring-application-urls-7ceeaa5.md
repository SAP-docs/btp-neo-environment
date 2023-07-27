<!-- loio7ceeaa5e528140c48ae53b68433293ba -->

# Configuring Application URLs

By default, all applications running on SAP BTP are accessed on the *hana.ondemand.com* domain.

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://launchpad.support.sap.com/#/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**

The URL of an application deployed in the Neo environment is `https://<application><subaccount>.<domain>`. For example, if you deploy application 'demo' in subaccount 'myshop', the application URL will be: `https://demomyshop.hana.ondemand.com`.

According to your needs, you can change the default application URL by configuring application domains different from the default one: custom or platform domains.

You can configure application domains using the console client for the Neo environment.

Note that you can use either platform domains or custom domains.



## Custom Domains

Use custom domains if you want to make your applications accessible on your own domain different from *hana.ondemand.com* - for example,*www.myshop.com*. When a custom domain is used, the domain name as well as the server certificate for this domain are owned by the customer.



## Platform Domains

> ### Caution:  
> You can configure different platform domains only for Java applications.

By default, applications accessible on *hana.ondemand.com* are available on the Internet. Platform domains enable you to use additional features by using a platform URL different from the default one.

For example, you can use *svc.hana.ondemand.com* to hide the application from the Internet and access it only from other applications running on SAP BTP, or, *cert.hana.ondemand.com* if you want an application to use client-certificate authentication with the relevant SSL connection settings. The application URLs will be `https://demomyshop.svc.hana.ondemand.com` or, `https://demomyshop.cert.hana.ondemand.com`, respectively.

**Related Information**  


[Using Custom Domains](using-custom-domains-98e655a.md "SAP Custom Domain service allows subaccount owners to make their SAP BTP applications accessible via a custom domain that is different from the default one (hana.ondemand.com) - for example www.myshop.com.")

[Using Platform Domains](using-platform-domains-a32d4cd.md#loioa32d4cd65be344439d9ed752f182e609 "Using platform domains, you can configure the application network availability or authentication policy. You can achieve that by configuring the appropriate platform domain which will change the URL on which your application will be accessible.")

[Configuring Application URLs (Cloud Foundry environment)](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/e623e372e6174f81af2b9b8ef8f6d6d3.html "By default, all applications running on SAP BTP are accessed on the default landscape domain. According to your needs, you can change the default application URL by configuring additional application domains.") :arrow_upper_right:

