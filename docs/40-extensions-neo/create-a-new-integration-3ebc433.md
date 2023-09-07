<!-- loio3ebc43359906404b974cd793cd05a71a -->

# Create a New Integration



<a name="loio3ebc43359906404b974cd793cd05a71a__prereq_g2v_sny_kcb"/>

## Prerequisites

-   You have created an OAuth client in SAP BTP. See [Create OAuth Client in SAP BTP](create-oauth-client-in-sap-btp-67f43e2.md).

-   You have created an outbound OAuth Configuration in SAP SuccessFactors. See [Create Outbound OAuth Configuration in SAP SuccessFactors](create-outbound-oauth-configuration-in-sap-successfactors-2fcdea4.md).




## Context

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**

If you want your extension application to receive notifications from your SAP SuccessFactors system, you need to subscribe this application to a dedicated event. Using the Intelligent Services Center, you create and configure an integration for this specific event.



## Procedure

1.  Log on to the SAP SuccessFactors system, and go to the *Intelligent Services Center*.

2.  Search for an event and choose it from the list. The event opens in a dedicated page.

3.  Select an already existing flow or create a new one from the menu on the left.

4.  In the *Activities* section on the right, choose *Integration*. A new dialog opens.

5.  Choose *Create New Integration*.

    -   For the *Destination Type*, choose *REST*. This means that the extension application that will receive notifications by this event is a REST service.

    -   For the *Format*, choose *JSON*. This means that the notifications will be sent to the REST service in a JSON format.


6.  Choose *Create*. The *Create New Integration Services* page appears.

7.  In the *Create New Integration Services* page, in the *Options* tab, enter a name for the new integration and a description. Choose *Next*.

8.  In the *Configure Fields* tab, you describe the JSON schema of the events which will be sent to the extension application REST API. Choose *Next*.

9.  Configure the settings in the *Response Fields* and *Filter* tabs according to your scenario.

    -   For the *Response Fields* tab, see [Using Configure Fields Tab](https://help.sap.com/viewer/60ba370328e0485797adde67aee846a0/LATEST/en-US/441dd33bd9ff4facaa4ccd9d0970408e.html).

    -   For the *Filter* tab, see [Filter and Sort](https://help.sap.com/viewer/60ba370328e0485797adde67aee846a0/LATEST/en-US/e3d79b3999e84ee7aad3e4f243847d3b.html).


10. Choose *Next*.

11. In the *Destination Settings* tab, set the following configurations:

    1.  In the *REST API URL* field, enter the REST endpoint URL of your application that will be called when the event notification is sent.

    2.  In the *Authentication Type* field, select *OAuth*.
    3.  In the *OAuth Configurations* field, select the outbound OAuth client credential s configuration you already have form the drop-down menu. See [Create Outbound OAuth Configuration in SAP SuccessFactors](create-outbound-oauth-configuration-in-sap-successfactors-c9546f4.md).
    4.  Choose *Next*.


12. In the *Review and Run* tab, choose *Save* and then *Run Now*.


