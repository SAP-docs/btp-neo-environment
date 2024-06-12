<!-- loio5af849ce877d44d3b6b861141ccabd13 -->

# Setting Entitlements Using the btp CLI

Use the SAP BTP command line interface \(btp CLI\) to set entitlements to define the functionality or permissions available for users of global accounts, directories, and subaccounts.

> ### Tip:  
> By default, all commands are executed in the global account you're logged into. To change this to a directory or subaccount, use `btp target`. See [Set a Target for Subsequent Commands with btp target](set-a-target-for-subsequent-commands-with-btp-target-720645a.md).


<table>
<tr>
<th valign="top">

Task

</th>
<th valign="top">

Run the command...

</th>
<th valign="top">

Command help

</th>
</tr>
<tr>
<td valign="top">

Get all the entitlements and quota assignments for a global account, directories, and subaccounts

</td>
<td valign="top">

`btp list accounts/entitlement`

> ### Restriction:  
> It is not possible to list the entitlements of a Neo subaccount with `btp list accounts/entitlements --subaccount <ID>`. You can, however, list the entitlements for a directory that includes Neo subaccounts with `btp list accounts/entitlements --directory <ID>`.



</td>
<td valign="top">

[btp list accounts/entitlement](https://help.sap.com/docs/BTP/btp-cli/btp-list-accounts-entitlement.html)

</td>
</tr>
<tr>
<td valign="top">

Assign or update an entitlement to a subaccount or a directory

</td>
<td valign="top">

`btp assign accounts/entitlement`

</td>
<td valign="top">

[btp assign accounts/entitlement](https://help.sap.com/docs/BTP/btp-cli/btp-assign-accounts-entitlement.html)

</td>
</tr>
</table>

**Related Information**  


[Working with Global Accounts, Directories, and Subaccounts Using the btp CLI](working-with-global-accounts-directories-and-subaccounts-using-the-btp-cli-85a683e.md "Use the SAP BTP command line interface (btp CLI) to manage operations with global accounts, directories, and subaccounts.")

[Working with Environments Using the btp CLI](working-with-environments-using-the-btp-cli-48db155.md "Use the SAP BTP command line interface (btp CLI) to manage runtime environment instances in a subaccount. For example, enable the Cloud Foundry environment by creating a Cloud Foundry org (environment instance).")

[Working with Multitenant Applications Using the btp CLI](working-with-multitenant-applications-using-the-btp-cli-c1b0fcc.md "Use the SAP BTP command line interface (btp CLI) to manage the multitenant applications to which a subaccount is entitled to subscribe.")

[Working with External Resource Providers Using the btp CLI](working-with-external-resource-providers-using-the-btp-cli-48d7688.md "Use the SAP BTP command line interface (btp CLI) to get details, or to create or delete resource provider instances in a global account.")

[Managing Trust from SAP BTP to an SAP Cloud Identity Services Tenant](managing-trust-from-sap-btp-to-an-sap-cloud-identity-services-tenant-6140107.md "SAP BTP supports identity federation. Its concept is to reuse the user bases of identity providers. To use a custom identity provider, your global account or subaccount in SAP BTP must have a trust relationship to the identity provider you want to use.")

[Managing Users and Their Authorizations Using the btp CLI](managing-users-and-their-authorizations-using-the-btp-cli-94bb593.md "User authorizations are managed by assigning role collections to users (for example, Subaccount Administrator). Use the SAP BTP command-line interface (btp CLI) to manage roles and role collections, and to assign role collections to users.")

[Managing Signing Keys for Access Tokens](managing-signing-keys-for-access-tokens-dfca1d3.md "Use the SAP BTP command line interface (btp CLI) to manage signing keys for access tokens in the subaccount.")

[Managing Security Settings](managing-security-settings-168dd75.md "Use the SAP BTP command line interface (btp CLI) to display and update the security settings for the subaccount.")

[Managing API Credentials for Calling REST APIs of SAP Authorization and Trust Management Service](managing-api-credentials-for-calling-rest-apis-of-sap-authorization-and-trust-manag-ce43eb5.md "Use the SAP BTP command line interface (btp CLI) to manage API credentials, which enable you to access the REST APIs of the SAP Authorization and Trust Management service.")

[Working with Resources of the SAP Service Manager Using the btp CLI](working-with-resources-of-the-sap-service-manager-using-the-btp-cli-fe6a53b.md "Use the SAP BTP command line interface to perform various operations related to your platforms, attached service brokers, service instances, and service bindings.")

[btp CLI Command Reference](https://help.sap.com/docs/BTP/btp-cli/intro.html)

[Entitlements and Quotas](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/00aa2c23479d42568b18882b1ca90d79.html "When you purchase an enterprise account, you’re entitled to use a specific set of resources, such as the amount of memory that can be allocated to your applications.") :arrow_upper_right:

