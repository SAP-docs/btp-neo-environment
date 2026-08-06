<!-- loioaf535bf0cfb54a0baed252e6458a8fb9 -->

# The Custom Domain Cannot Be Configured Using an Apex Domain

Apex domains are not supported for custom domains in the SAP BTP, Neo environment. Learn why this is the case and what actions you can take to configure your custom domain in this environment.

> ### Caution:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/docs/btp/sap-business-technology-platform/sap-business-technology-platform?version=Cloud) .**

> ### Tip:  
> Additional IP outbound addresses will soon be used in all regions in the Neo environment. For more information, see [Additional IP Addresses Added to SAP BTP, Neo Runtime Regions](https://help.sap.com/whats-new/cf0cb2cb149647329b5d02aa96303f56?version=Cloud&Component=Region&Valid_as_Of=2026-11-02:2026-11-02). To subscribe to such notifications, see SAP Note [3513325](https://me.sap.com/notes/3513325).

The SAP Custom Domain service in the Neo environment does not support apex domains. Apex domains, also known as root domains, do not contain any subdomains. For example, `myshop.com`.

**Next Steps**:

To configure a custom domain, you need to use at least one subdomain. Examples: `www.myshop.com`, `test.myshop.com`, `login.preview.myshop.com`

**Related Information**  


[The Custom Domain Is Not Working As Expected](the-custom-domain-is-not-working-as-expected-bd64a01.md "Find the reason why your custom domain in the SAP BTP, Neo environment is not working as expected.")

[Troubleshooting Guide for Custom Domains in the Neo Environment](troubleshooting-guide-for-custom-domains-in-the-neo-environment-216e0ed.md "Use this troubleshooting guide to quickly identify and resolve issues with custom domains in the SAP BTP, Neo environment.")

