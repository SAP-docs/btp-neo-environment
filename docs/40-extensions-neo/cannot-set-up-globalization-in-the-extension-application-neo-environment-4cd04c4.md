<!-- loio4cd04c46713d45469a81fe77e8ec30b2 -->

# Cannot Set Up Globalization in the Extension Application \(Neo Environment\)

Cannot set up globalization in the extension application



> ### Caution:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/docs/btp/sap-business-technology-platform/sap-business-technology-platform?version=Cloud) .**

> ### Tip:  
> Additional IP outbound addresses will soon be used in all regions in the Neo environment. For more information, see [Additional IP Addresses Added to SAP BTP, Neo Runtime Regions](https://help.sap.com/whats-new/cf0cb2cb149647329b5d02aa96303f56?version=Cloud&Component=Region&Valid_as_Of=2026-11-02:2026-11-02). To subscribe to such notifications, see SAP Note [3513325](https://me.sap.com/notes/3513325).



<a name="loio4cd04c46713d45469a81fe77e8ec30b2__section_y2w_hh2_2cc"/>

## Issue/Symptom

You want to implement globalization \(internationalization/localization\) in your extension application and you are using the SAP SuccessFactors identity provider.



<a name="loio4cd04c46713d45469a81fe77e8ec30b2__section_gb1_lh2_2cc"/>

## Solution

You can switch the application language depending on the SAML locale attribute which is propagated to your Java application during login.

See:

-   Supported SAP SuccessFactors SAML attributes: [SuccessFactors SAML 2.0 Technical Details](https://help.sap.com/viewer/568fdf1f14f14fd089a3cd15194d19cc/LATEST/en-US/e4a8dc78bdfc443ca032cffa6dab13b5.html)
-   [Configure Trust to the SAML Identity Provider](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/dc618538d97610148155d97dcd123c24.html#loiob6cfc4bb4bff4ace90afc71b0962fcb5), step 5., *Assertion-based attributes* section.
-   Consume user attributes in a Java application: [User Attributes](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/9e2e0d7e91cc44e79901a756bf7b2d88.html)

**Option 2**

You can use the SAP SuccessFactors OData API.

If you get the current user profile \(\{odata\_api\_host\}/odata/v2/User\('<user\_id\>'\)\), there is a property called **defaultLocale** that you can use.

See:

-   OData API: [Developer Guide](https://help.sap.com/viewer/d599f15995d348a1b45ba5603e2aba9b/LATEST/en-US/c614402bdde3469792fd8f842670f82d.html)
-   [User entity documentation](https://help.sap.com/viewer/28bc3c8e3f214ab487ec51b1b8709adc/LATEST/en-US/5d848f7cffc5402a8dce50f7f254be7e.html)

