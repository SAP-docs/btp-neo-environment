<!-- loio98e655aacd1d4fc6a6ab23475b1afcd9 -->

# Using Custom Domains

SAP Custom Domain service allows subaccount owners to make their SAP BTP applications accessible via a custom domain that is different from the default one \(`hana.ondemand.com`\) - for example `www.myshop.com`.

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**

> ### Note:  
> If you want to configure a custom domain for a SAP Cloud Integration application, see [Configuring Custom Domains for SAP Cloud Integration](https://help.sap.com/viewer/368c481cd6954bdfa5d0435479fd4eaf/Cloud/en-US/7230b9ff41914cc0969223e6a020104b.html).

> ### Note:  
> Apex domains are not supported. For example, `myshop.com`.

By default, when you deploy an application on SAP BTP, Neo environment, you receive a unique URL to access it. For example, `www.mycompany1b23456c.hana.ondemand.com`. SAP Custom Domain service allows you to:

-   Customize this generic URL with a more comprehensible one \(for example, `www.mycompany.com`\) as well as customize the secure SSL connection to your application. This will make your company more recognizable on the Internet.

-   Configure single sign-on for easier access to your application.




## Prerequisites

To use a custom domain for your application, you must **fulfill a number of preliminary steps**. For more information about these steps, see [Prerequisites](prerequisites-cde2547.md).



## Scenario

After fulfilling the prerequisites, you can configure the custom domain on your own using console client commands for the Neo environment.

First, set up secure SSL communication to ensure that your domain is trusted and all application data is protected. Then, route the traffic to your application:

1.  [Create an SSL Host](configuring-custom-domains-77cf0e6.md#loio70f4d19d3dbd434aa9aa165d53e2896c) - the host holds the mapping between your chosen custom domain and the application on SAP BTP as well as the SSL configuration for secure communication through this custom domain.
2.  [Upload a Certificate](configuring-custom-domains-77cf0e6.md#loio55120d899d314e23ab8e33b4b388cea6) - it will be used as a server certificate on the SSL host.
3.  [Bind the Certificate to the SSL Host](configuring-custom-domains-77cf0e6.md#loio1d4248f3582a40cdb6f4a2439a55fb65).
4.  [Add the Custom Domain](configuring-custom-domains-77cf0e6.md#loiobf395cf25683491eabefadb4383ed7ff) - this maps the custom domain to the application URL.
5.  [Configure DNS](configuring-custom-domains-77cf0e6.md#loio004406e1c9a8441fb05a25f5f87d45b7)- you can create a CNAME mapping.
6.  [Configure Single Sign-On](configuring-custom-domains-77cf0e6.md#loio6b671d39f46c41d1bbd89b7e698fe384) - if you have a custom trust configuration in your subaccount, you need to enable single logout.

The configuration of custom domains has different setups related to the subscriptions of your subaccount. For more information about custom domains for applications that are part of a subscription, see [Custom Domains for Multitenant Applications](custom-domains-for-multitenant-applications-b2b5dcc.md).

**Related Information**  


[Prerequisites](prerequisites-cde2547.md "Before configuring an SAP custom domain, you need to perform some preliminary steps and fulfill a number of prerequisites.")

[Configuring Custom Domains](configuring-custom-domains-77cf0e6.md#loio77cf0e6cd32e496c9cc8eeac4bedde94 "To make sure that your domain is trusted and all application data is protected, you need to first set up secure SSL communication. The next step will then be to make your application accessible via the custom domain and route traffic to it.")

[Frequently Asked Questions](frequently-asked-questions-a226905.md "Answers to some of the most commonly asked questions about SAP Custom Domain service.")

[Guided Answers \(Neo Environment\)](https://ga.support.sap.com/dtp/viewer/index.html#/tree/2065/actions/26547:34945:27935)

[No Pain, No Gain. Get Started with SAP Custom Domain Service \(SAP Community Blog\)](https://blogs.sap.com/2019/01/30/no-pain-no-gain.-get-started-with-sap-cloud-platform-custom-domains/)

[Configuring Custom Domains for SAP Cloud Integration](https://help.sap.com/viewer/368c481cd6954bdfa5d0435479fd4eaf/Cloud/en-US/7230b9ff41914cc0969223e6a020104b.html)

[Configuring Custom Domains for SAP Cloud Portal service](https://help.sap.com/viewer/8422cb487c2146999a2a7dab9cc85cf7/Cloud/en-US/b5c7fa40ef394f28bf954eec5ed907d6.html)

