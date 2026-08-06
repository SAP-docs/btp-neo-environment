<!-- loioc8e57f17cf854b29960ce1805806d91b -->

# Uploading a CA Bundle

Learn how to deal with error messages when uploading a CA bundle.

> ### Caution:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/docs/btp/sap-business-technology-platform/sap-business-technology-platform?version=Cloud) .**

> ### Tip:  
> Additional IP outbound addresses will soon be used in all regions in the Neo environment. For more information, see [Additional IP Addresses Added to SAP BTP, Neo Runtime Regions](https://help.sap.com/whats-new/cf0cb2cb149647329b5d02aa96303f56?version=Cloud&Component=Region&Valid_as_Of=2026-11-02:2026-11-02). To subscribe to such notifications, see SAP Note [3513325](https://me.sap.com/notes/3513325).

You are allowed to upload as many as four CA bundles per each SSL host.

If you receive an error message saying that you can't upload a specific CA bundle, choose one of the following options:

-   Upload your CA to an existing bundle. See [add-ca](https://help.sap.com/docs/btp/sap-btp-neo-environment/add-ca).

-   Delete any bundles you don't need. See [set-ssl-host](https://help.sap.com/docs/btp/sap-btp-neo-environment/set-ssl-host) command with the `--ca-bundle` parameter.

-   Increase your custom domain quota by purchasing a new custom domain from the [SAP BTP Service Marketplace](https://www.sap.com/products/technology-platform.html#capabilitiesPricing).


For more information about managing your CA bundles, see [Managing Client Certificate Authentication](https://help.sap.com/docs/btp/sap-btp-neo-environment/managing-client-certificate-authentication-for-custom-domains).

**Related Information**  


[Experiencing CA Bundle Issues](experiencing-ca-bundle-issues-4c26325.md "Use the following troubleshooting steps for resolving issues with CA bundles.")

[Troubleshooting Guide for Custom Domains in the Neo Environment](troubleshooting-guide-for-custom-domains-in-the-neo-environment-216e0ed.md "Use this troubleshooting guide to quickly identify and resolve issues with custom domains in the SAP BTP, Neo environment.")

