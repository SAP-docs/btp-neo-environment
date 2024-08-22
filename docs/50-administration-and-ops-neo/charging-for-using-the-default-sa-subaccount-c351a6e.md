<!-- loioc351a6eedf2e4ff0a0f28f3ed5859193 -->

# Charging for Using the DEFAULT\_SA Subaccount

The DEFAULT\_SA subaccount is a technical entity that allows the cockpit to display services charged at the global account level. The SAP Custom Domain service in the SAP BTP, Neo environment is one of these services.

Some SAP BTP services report their billing and usage at the global account level, and not at the subaccount level. Such is the case with the SAP Custom Domain service in SAP BTP, Neo environment. This service is listed on the *Costs and Usage* page in the SAP BTP cockpit under a subaccount with the name `REPORTED-AT-GLOBAL-ACCOUNT-LEVEL` and ID `DEFAULT_SA`.

If you haven't noticed this subaccount until now and you don't recognize it as one of your own, don't worry. This isn't a real subaccount, but rather a technical entity that allows the cockpit to display the services which are charged at the global account level.

For more information, check the *Understanding the Cost and Usage Views* section in [Monitoring Usage and Consumption Costs in Your Global Account](https://help.sap.com/docs/btp/sap-btp-neo-environment/monitoring-usage-and-consumption-costs-in-your-global-account?version=Cloud#understanding-the-cost-and-usage-views).

**Related Information**  


[Troubleshooting Guide for Custom Domains in the Neo Environment](troubleshooting-guide-for-custom-domains-in-the-neo-environment-216e0ed.md "Use this troubleshooting guide to quickly identify and resolve issues with custom domains in the SAP BTP, Neo environment.")

