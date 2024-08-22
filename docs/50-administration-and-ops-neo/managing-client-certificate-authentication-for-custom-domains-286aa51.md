<!-- loio286aa51837e74859be9bda4a529e960b -->

# Managing Client Certificate Authentication for Custom Domains

If you want your customers to use client certificates when they access your application on SAP BTP via a custom domain.

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of the following technology portfolios: application development; process automation; integration; data, analytics, and enterprise planning; artificial intelligence. The platform offers users the ability to turn data into business value, compose end-to-end business processes, connect entire IT landscapes, and personalize, build and extend SAP applications. This reduces the overall total cost of ownership maintaining SAP landscapes and third-party software across end-to-end business processes.") :arrow_upper_right:.**



<a name="loio286aa51837e74859be9bda4a529e960b__section_jnx_d1w_f2b"/>

## Prerequisites

Your have configured a custom domain for your application. For more information, see [Using Custom Domains](using-custom-domains-98e655a.md).



<a name="loio286aa51837e74859be9bda4a529e960b__section_yyg_m1w_f2b"/>

## Features

As an account administrator, you can:

-   Create and upload a list of trusted CA \(certificate authority\) certificates and assign that list to a previously created SSL host. For more information, see [add-ca](add-ca-c102abb.md).

-   Configure the SSL host to optionally or mandatorily require client certificate authentication. To do that, use the `--ca-bundle` parameter when executing the `set-ssl-host` command. For more information, see [set-ssl-host](set-ssl-host-2956975.md).


**Related Information**  


[add-ca](add-ca-c102abb.md "Uploads a trusted CA certificate and adds it to a certificate authority (CA) bundle. If you don't have a CA bundle yet, it will be created automatically.")

[list-cas](list-cas-99d2659.md "Lists trusted CA certificates in a bundle or bundles that are assigned to an SSL host or hosts.")

[remove-ca](remove-ca-55b61e4.md "Removes trusted CAs from a bundle or deletes a whole bundle and all certificates in it.")

[set-ssl-host](set-ssl-host-2956975.md "Configures and updates an SSL host. Allows you to replace an SSL certificate with a different one, manage TLS protocol versions, and configure a bundle of trusted CAs.")

