<!-- loio6ef1e3bea61b4ad8a4ebf06637f43c96 -->

# Create an Integration Token for SAP SuccessFactors

You create an integration token required for the configuration of the extension integration between SAP BTP and SAP SuccessFactors.



## Prerequisites

To create an integration token, you need to have assigned to your user either the Administrator predefined role or a custom platform role with the following scopes for the subaccount which you want to integrate with your SAP SuccessFactors system:

-   readExtensionIntegration

-   manageExtensionIntegration

-   manageDestinations

-   manageApplicationRoleProvider

-   manageTrustSettings


For more information, see [Platform Scopes](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/f2260746ed8e446fafdeaaa8ab43e307.html) and [Manage Custom Platform Roles in the Neo Environment](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/ede5f721e78e4d678c87c8a200c564ca.html).



## Context

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**

To initiate the automated configuration for extending SAP SuccessFactors on SAP BTP, the SAP SuccessFactors administrators with Provisioning access need an integration token. It determines the subaccount in SAP BTP that will be integrated with your SAP SuccessFactors company, and with which your SAP SuccessFactors company will be linked.

> ### Note:  
> One SAP SuccessFactors company can be integrated with more than one subaccount, while one subaccount can be associated with exactly one SAP SuccessFactors company.

As an SAP BTP user with permissions for the respective subaccount, you create an integration token using the SAP BTP cockpit, and then pass it over to the SAP SuccessFactors administrator.



## Procedure

1.  In your Web browser, open the cockpit using the relevant URL for the region with which your customer subaccount is associated. For more information about the regions, see [Regions](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/350356d1dc314d3199dca15bd2ab9b0e.html).

2.  Select the relevant subaccount, and then choose *Integration Tokens* in the navigation area.

    > ### Note:  
    > This is the subaccount that is going to be associated with the SAP SuccessFactors system after a successful extension integration. You either use a new dedicated subaccount that you create in advance, or an already existing subaccount.

3.  In the *Integration Tokens* panel, choose *New Token*.

    The *New SAP SuccessFactors Token* dialog box opens.

4.  Select a trusted identity provider for single sign-on:

    -   If you already have a configured trusted third-party identity provider, or an SAP Cloud Identity Services - Identity Authentication tenant in your extension subaccount that is marked as default one, you can keep it. To do that, select *Use existing custom identity provider*.

    -   If you want to use the SAP SuccessFactors identity provider, select *Use SAP SuccessFactors identity provider*.

        > ### Note:  
        > If you select the *Use SAP SuccessFactors identity provider* option, after a successful integration, this identity provider will become the new default trust setting. This might affect Java/HTML5 applications that depend on the previous trust settings.


5.  Choose *Create* and then *OK*.

    Your newly created token appears in the list of integration tokens and its status is `ACTIVE`. In the *Integration Tokens* panel, you can view details such as the user who has created the token, the creation date and the expiration date. The token is valid for 7 days after it has been created.

    > ### Note:  
    > The integration token can be used only once. Once the integration token is used, it is no longer valid.

6.  \(Optional\) You can perform the following actions:

    -   To view the identity provider used for the applications in the subaccount where the token has been created, choose *Token details* in the *Actions* column on the row of the respective token.
    -   To delete an integration token, choose *Delete token* in the *Actions* column on the row of the respective token.




## Results

You have created an integration token which you can use to initiate the automated configuration for extending SAP SuccessFactors on SAP BTP.

> ### Note:  
> Make sure to use the integration token before its expiration date.



## Next Steps

You can now pass over the value of the token to the SAP SuccessFactors administrator who will be triggering the automated configuration for extending SAP SuccessFactors on SAP BTP.

