<!-- loio0ad865e7795f4ceda45129c6a381aa92 -->

# Integrate the Extension Application with SAP SuccessFactors Intelligent Services

You can integrate the extension application to subscribe to an event defined in the SAP SuccessFactors system.

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of the following technology portfolios: application development; process automation; integration; data, analytics, and enterprise planning; artificial intelligence. The platform offers users the ability to turn data into business value, compose end-to-end business processes, connect entire IT landscapes, and personalize, build and extend SAP applications. This reduces the overall total cost of ownership maintaining SAP landscapes and third-party software across end-to-end business processes.") :arrow_upper_right:.**

With SAP BTP you can choose between the following integration flows that enable your extension application to consume events defined in the SAP SuccessFactors system:

-   OAuth 2.0 client credentials grant flow.

    This flow enables grant of an OAuth access token based on the client credentials only, without user interaction. See [Configure Integration Based on OAuth 2.0 Client Credentials](configure-integration-based-on-oauth-2-0-client-credentials-d5b6a7d.md) 

-   User propagation with SAML identity federation flow.

    This flow enables you to propagate the users from SAP SuccessFactors with SAML identity federation to your OAuth-protected extension application running on SAP BTP. See [Configure Integration Based on User Propagation with SAML Identity Federation](configure-integration-based-on-user-propagation-with-saml-identity-federation-2e4a9d5.md) 


