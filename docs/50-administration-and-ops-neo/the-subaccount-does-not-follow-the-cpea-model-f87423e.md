<!-- loiof87423e3177c43a88083883b088532e3 -->

# The Subaccount Does Not Follow the CPEA Model

If your subaccount doesn't follow the consumption-based license model according to CPEA, take action depending on whether you have purchased a custom domain quota or not.

Do the following depending on whether you have purchased a custom domain quota or not:

-   If you have purchased a custom domain quota, verify the custom quota distribution.

    In general, one custom domain quota allows you to have one SSL host and up to four domain certificates. Now, let's take a look at a couple of examples:

    -   Output of the [list-ssl-hosts](https://help.sap.com/docs/btp/sap-btp-neo-environment/list-ssl-hosts) command

        Example: Let's assume that the owner of a global account has a custom domain quota of two. If there are two SSL hosts created for that specific subaccount, the quota will be maxed out in terms of SSL hosts.

    -   Output of the [list-domain-certificates](https://help.sap.com/docs/btp/sap-btp-neo-environment/list-domain-certificates) command

        Example: Once again, let's assume that there is a custom domain quota of two. In this case, there cannot be more than eight certificates in that same subaccount.


    > ### Note:  
    > If you want to check your currently available custom domain quota, see SAP KBA [2513220 - How to determine the number of the domain quota of your company](https://me.sap.com/notes/2513220).

-   If you haven't purchased any custom domain quota yet, you must acquire some.

    If you want to purchase a custom domain or you have reached the maximum amount of available quota, contact your local sales representative. See:

    -   SAP KBA [1660069 - How to contact SAP Contracts Department for contract-related questions or issues](https://me.sap.com/notes/1660069)

    -   SAP KBA [2626344 - Who is the SAP Account Manager/Executive for my company?](https://me.sap.com/notes/2626344)


    To check if you have any available custom domain quota, see SAP KBA [2513220 - How to determine the number of the domain quota of your company](https://me.sap.com/notes/2513220).

    One custom domain:

    -   Provides you with one custom domain quota.

    -   Grants you one SSL host.

    -   Allows you to generate as many as four certificate signing requests with the `generate-csr` command.

    -   Allows you to upload as many as four CA bundles.


    Remember that you can assign only one certificate to your SSL host.

    See [Using Custom Domains](https://help.sap.com/docs/btp/sap-btp-neo-environment/using-custom-domains).


**Related Information**  


[generate-csr](generate-csr-f02258d.md "Generates and returns a certificate signing request (CSR).")

[Experiencing Custom Domain Quota Issues](experiencing-custom-domain-quota-issues-a84860c.md "To start tackling any custom domain quota issues, first you need to know whether your subaccount follows the consumption-based license model according to the Cloud Platform Enterprise Agreement (CPEA).")

[Troubleshooting Guide for Custom Domains in the Neo Environment](troubleshooting-guide-for-custom-domains-in-the-neo-environment-216e0ed.md "Use this troubleshooting guide to quickly identify and resolve issues with custom domains in the SAP BTP, Neo environment.")

