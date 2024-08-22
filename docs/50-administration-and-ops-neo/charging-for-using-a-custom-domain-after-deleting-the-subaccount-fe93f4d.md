<!-- loiofe93f4d8374846978b60356463cf0a00 -->

# Charging for Using a Custom Domain After Deleting the Subaccount

To avoid unnecessary charges and ensure the smooth deletion of a subaccount, remove any unused custom domains from that subaccount. Do not forget to first check the prerequisites for deleting a subaccount in the SAP BTP, Neo environment.



<a name="loiofe93f4d8374846978b60356463cf0a00__prereq_ukc_g23_1cc"/>

## Prerequisites

Тo check all prerequisites for deleting a subaccount, see [Delete a Subaccount](https://help.sap.com/docs/btp/sap-btp-neo-environment/delete-subaccount).



## Context

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

