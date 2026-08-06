<!-- loioff70cd7535af4483a2af516dea5d8a52 -->

# Migrating a Custom Domain Setup to Another Region with Minimal Downtime

Follow these steps to minimize the downtime when migrating a custom domain configuration between regions.



## Context

> ### Caution:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/docs/btp/sap-business-technology-platform/sap-business-technology-platform?version=Cloud) .**

> ### Tip:  
> Additional IP outbound addresses will soon be used in all regions in the Neo environment. For more information, see [Additional IP Addresses Added to SAP BTP, Neo Runtime Regions](https://help.sap.com/whats-new/cf0cb2cb149647329b5d02aa96303f56?version=Cloud&Component=Region&Valid_as_Of=2026-11-02:2026-11-02). To subscribe to such notifications, see SAP Note [3513325](https://me.sap.com/notes/3513325).

If you want to migrate your custom domain configuration from one region to another region and you want to minimize the amount of downtime, follow these steps:



## Procedure

1.  Configure a custom domain in the new global account as per the standard configuration steps described in [Configuring Custom Domains](https://help.sap.com/docs/btp/sap-btp-neo-environment/configuring-custom-domains). Skip the Configure DNS step for now.

2.  Once you have completed the custom domain setup, switch the CNAME record in the DNS to point to the SSL host of the new global account. By doing this, you make sure that the custom domain starts working with the new setup.

    > ### Note:  
    > Keep in mind that some time is needed for the new DNS record to be updated worldwide.

3.  If the new custom domain setup is working fine one week after you’ve switched the traffic to the new SSL host, you can completely remove the old setup provided that you no longer need that setup. To do that, execute these commands in the following order:

    1.  Remove the trusted CA configurations from the old SSL host, if any, with[set-ssl-host](https://help.sap.com/docs/btp/sap-btp-neo-environment/set-ssl-host) and the `--ca-bundle` `<bundle_name>:none` parameter.

    2.  Unbind the domain certificate with [unbind-domain-certificate](https://help.sap.com/docs/btp/sap-btp-neo-environment/unbind-domain-certificate).

    3.  Remove all custom domain mappings with [remove-custom-domain](https://help.sap.com/docs/btp/sap-btp-neo-environment/remove-custom-domain).

    4.  Remove all certificates with [delete-domain-certificates](https://help.sap.com/docs/btp/sap-btp-neo-environment/delete-domain-certificate) and trusted CAs with [remove-ca](https://help.sap.com/docs/btp/sap-btp-neo-environment/remove-ca).

    5.  Remove the old SSL host with [delete-ssl-host](https://help.sap.com/docs/btp/sap-btp-neo-environment/delete-ssl-host).


    If you encounter any problems, [report a case](https://me.sap.com/home) and assign it to the BC-NEO-INFR component.


**Related Information**  


[How to Migrate a Custom Domain Between Global Accounts Within the Same Region](https://blogs.sap.com/2021/06/29/how-to-migrate-a-custom-domain-between-global-accounts)

[Regions and Hosts Available for the Neo Environment](https://help.sap.com/docs/btp/sap-btp-neo-environment/regions-and-hosts-available-for-neo-environment)

[Getting Support, Neo Environment](https://help.sap.com/docs/btp/sap-btp-neo-environment/getting-support-neo-environment)

[Troubleshooting Guide for Custom Domains in the Neo Environment](troubleshooting-guide-for-custom-domains-in-the-neo-environment-216e0ed.md "Use this troubleshooting guide to quickly identify and resolve issues with custom domains in the SAP BTP, Neo environment.")

