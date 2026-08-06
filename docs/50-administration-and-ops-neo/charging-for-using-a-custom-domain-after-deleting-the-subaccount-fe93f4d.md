<!-- loiofe93f4d8374846978b60356463cf0a00 -->

# Charging for Using a Custom Domain After Deleting the Subaccount

To avoid unnecessary charges and ensure the smooth deletion of a subaccount, remove any unused custom domains from that subaccount. Do not forget to first check the prerequisites for deleting a subaccount in the SAP BTP, Neo environment.



<a name="loiofe93f4d8374846978b60356463cf0a00__prereq_ukc_g23_1cc"/>

## Prerequisites

Тo check all prerequisites for deleting a subaccount, see [Delete a Subaccount](https://help.sap.com/docs/btp/sap-btp-neo-environment/delete-subaccount).



## Context

> ### Caution:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/docs/btp/sap-business-technology-platform/sap-business-technology-platform?version=Cloud) .**

> ### Tip:  
> Additional IP outbound addresses will soon be used in all regions in the Neo environment. For more information, see [Additional IP Addresses Added to SAP BTP, Neo Runtime Regions](https://help.sap.com/whats-new/cf0cb2cb149647329b5d02aa96303f56?version=Cloud&Component=Region&Valid_as_Of=2026-11-02:2026-11-02). To subscribe to such notifications, see SAP Note [3513325](https://me.sap.com/notes/3513325).

Before you delete a subaccount in the SAP BTP, Neo environment, make sure that you have removed any unused custom domains and corresponding SSL hosts and certificates. Otherwise, you may still be charged for them.

A custom domain is configured on a global account level, which means that one custom domain can be part of business scenarios in several subaccounts. Before you delete a subaccount:



## Procedure

1.  Make sure that the custom domain is not used outside of the subaccount that you want to delete. Once you are sure that custom domain is not used anywhere else, remove it to avoid being charged for it.

    > ### Remember:  
    > Do not delete the subaccount before removing the custom domain. If you first delete the subaccount, you won't be able to remove the custom domain after that.

    If you decide to remove the custom domain, see [Remove the Custom Domain](https://help.sap.com/docs/btp/sap-btp-neo-environment/configuring-application-urls-remove-custom-domain).

2.  If the custom domain is still being used in other subaccounts, do not delete the custom domain. You can proceed with the deletion of the subaccount.


**Related Information**  


[Troubleshooting Guide for Custom Domains in the Neo Environment](troubleshooting-guide-for-custom-domains-in-the-neo-environment-216e0ed.md "Use this troubleshooting guide to quickly identify and resolve issues with custom domains in the SAP BTP, Neo environment.")

