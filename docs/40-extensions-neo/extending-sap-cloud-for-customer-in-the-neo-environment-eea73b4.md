<!-- loioeea73b48fe3e48e78f03a0a1394a064c -->

# Extending SAP Cloud for Customer in the Neo Environment

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/docs/btp/sap-business-technology-platform/sap-business-technology-platform?version=Cloud) .**

This section guides you through the configuration tasks that you need to perform to enable the Neo environment for developing extension applications for your SAP Cloud for Customer system.



<a name="loioeea73b48fe3e48e78f03a0a1394a064c__section_h3w_wdk_ndb"/>

## Overview

Extending SAP Cloud for Customer on SAP BTP allows you to implement additional workflows or modules on top of the SAP Cloud for Customer benefiting from out-of-the-box security, inherited data access governance, user interface embedding, and others.

In the SAP Cloud for Customer extensions scenarios, these are the important aspects:

-   The Extension Applications for SAP Cloud for Customer are hosted or subscribed in a dedicated subaccount in SAP BTP to ensure the consistency in the integration configuration between the two solutions. The purpose of the subaccount is to hold the common integration configurations for all extension applications.

-   The single sign-on configuration between SAP Cloud for Customer and SAP BTP ensures the secure and consistent data access for the extension application.

-   OAuth connectivity configuration for enabling the use of SAP Cloud for Customer OData APIs.

-   Configuration of the HTML mashups in SAP Cloud for Customer helps with embedding the extension application UI directly in the SAP Cloud for Customer screens and offers the same look and feel to the end users.




<a name="loioeea73b48fe3e48e78f03a0a1394a064c__section_dh4_ntk_ndb"/>

## Prerequisites

-   Your company has an enterprise account in the cloud platform. For more information about account types and purchasing an enterprise account, see:
    -   [Account Model](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/8ed4a705efa0431b910056c0acdbf377.html#loio8ed4a705efa0431b910056c0acdbf377 "Learn more about the different types of accounts on SAP BTP and how they relate to each other.") :arrow_upper_right:

    -   [Get an Enterprise Account](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/d61c2819034b48e68145c45c36acba6e.html#loio82f9ff522f754e26ae89e0cd7ec7aa11 "To use an enterprise account, you can either purchase a customer account, join the partner program to purchase a partner account, or self-register for an enterprise account to try out free tier service plans.") :arrow_upper_right:


-   You have a user account on the platform with administrative permissions for the enterprise account of your company and you can use the [Cloud Cockpit](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/e47748b5bb571014afedc70595804f3e.html).

-   If you need to configure single sign-on using the Identity Authentication service, you have to make sure that your company has license and a tenant for this SAP service. For more details, see the [Getting Started](https://help.sap.com/viewer/6d6d63354d1242d185ab4830fc04feb1/Cloud/en-US/31af7da133874e199a7df1d42905241b.html) section of the documentation for this service.
-   You have administrative permissions for the SAP Cloud for Customer system necessary for configuring the connectivity with external systems, in this case SAP BTP.



<a name="loioeea73b48fe3e48e78f03a0a1394a064c__section_c2w_qbf_l2b"/>

## Process Flow

You have to configure the cloud platform extension integration with SAP Cloud for Customer to enable the use of applications running on top of the platform from SAP Cloud for Customer.



### 1. Authentication and Principal Propagation

A single sign-on configuration between SAP Cloud for Customer and SAP BTP and the principal propagation enablement ensure the secure and consistent access for the extension solutions. If your solution requires system-to-system data access, with no user propagation, you can implement it using a user with Basic authentication and no principal propagation.

> ### Tip:  
> We recommend that you use SSO and OData access with principal propagation, to ensure that the data is accessed on behalf of the proper authorized user.

**Implementation with SSO and principal propagation**

When your scenario requires SSO and principal propagation, the SAP Cloud for Customer system and the SAP BTP subaccount \(where the extension application is deployed or subscribed\) have to trust each other and use one and the same identity provider. For more information, see [Configuring Single Sign-On](configuring-single-sign-on-625f2c3.md).

**Implementation without SSO and principal propagation**

If your scenario does not require SSO, principal propagation, or UI integration, you use a dedicated user and create an HTTP destination with Basic Authentication to configure the connectivity. For more information, see [Create and Configure the HTTP Destination](create-and-configure-the-http-destination-9292948.md).



### 2. Connectivity Between SAP BTP and SAP Cloud for Customer

When your extension application needs to do read and write operations from/to the SAP Cloud for Customer system, you have to configure the connectivity to enable the use of SAP Cloud for Customer OData APIs. You need such connectivity to be established also when you want to embed the UIs of the extension solution into the SAP Cloud for Customer user interface.

The connectivity configuration steps are required on both systems and can be implemented with the following options depending on the security mechanisms for protecting the connectivity:

**Using OAuth**

> ### Note:  
> OAuth can be used only when a common identity provider is configured for both systems.

-   On SAP Cloud for Customer side:

    -   [Configure OAuth Identity Provider in SAP Cloud for Customer](configure-oauth-identity-provider-in-sap-cloud-for-customer-ba893b5.md)

    -   [Configure the OAuth Client for OData Access](configure-the-oauth-client-for-odata-access-0ac0dc9.md)



-   On the SAP BTP side:

    -   Create an HTTP destination with OAuthSAMLBearerAssertion for authentication method. For more details, see [Create and Configure the HTTP Destination](create-and-configure-the-http-destination-9292948.md).



**Using Basic Authentication**

-   On SAP Cloud for Customer side:

    -   \(If not available\) Create a technical user with permissions to access the required SAP Cloud for Customer OData APIs and use it for the HTTP destination configuration when you choose Basic authentication for protecting the connectivity.



-   On the SAP BTP side:

    -   Create an HTTP destination with Basic authentication using the credentials of a technical user in the SAP Cloud for Customer system. For more details, see [Create and Configure the HTTP Destination](create-and-configure-the-http-destination-9292948.md).





### 3. User Interface Integration

The extension capabilities of SAP BTP allow developers to embed the user interface of the new solution in the SAP Cloud for Customer screens and this way to offer seamless end-user experience.

