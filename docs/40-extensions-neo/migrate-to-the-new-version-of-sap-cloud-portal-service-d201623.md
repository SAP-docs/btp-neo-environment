<!-- loiod2016237743b4142aea0b0ce71f32582 -->

# Migrate to the New Version of SAP Cloud Portal Service

If your extension integration uses the old version of SAP Cloud Portal service, you need to migrate to the new version to enable an enhanced extension administration flow and user experience.



## Context

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://launchpad.support.sap.com/#/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**

In the new SAP Cloud Portal service, there are two available site templates for the SAP BTP extensions for SAP SuccessFactors.

As of September 2016, SAP SuccessFactors Q3 2016 supports the new version of SAP Cloud Portal service by default. If you want to use the enhanced SAP Cloud Portal service functionality with extension integration configured before then, you need to enable it manually.



## Procedure

To enable the enhanced functionality of an extension integration that uses the old SAP Cloud Portal service, you refresh the respective extension integration with a particular subaccount in SAP BTP. For more information, see [Refresh the Extension Integration for SAP SuccessFactors](refresh-the-extension-integration-for-sap-successfactors-9d3f809.md).



## Results

In the *Extensions* tool in *SAP SuccessFactors* \> *Admin Center*, the Extension Directory link for the corresponding extension integration now points to the new SAP Cloud Portal service Admin Space.

You can now create extension sites using the enhanced functionality provided with the new SAP Cloud Portal service version. This version includes two site templates for the SAP SuccessFactors extensions for SAP SuccessFactors.

**Related Information**  


[Create an Extension Site](create-an-extension-site-9e3fc15.md "You create an extension site to integrate the extension application in SAP SuccessFactors.")

