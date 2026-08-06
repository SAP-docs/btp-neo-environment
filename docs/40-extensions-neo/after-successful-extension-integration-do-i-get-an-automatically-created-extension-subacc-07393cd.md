<!-- loio07393cd4e83145688894a360e754f47c -->

# After Successful Extension Integration, Do I Get an Automatically Created Extension Subaccount? \(Neo Environment\)

After successful extension integration, do I get an automatically created extension subaccount?



> ### Caution:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/docs/btp/sap-business-technology-platform/sap-business-technology-platform?version=Cloud) .**

> ### Tip:  
> Additional IP outbound addresses will soon be used in all regions in the Neo environment. For more information, see [Additional IP Addresses Added to SAP BTP, Neo Runtime Regions](https://help.sap.com/whats-new/cf0cb2cb149647329b5d02aa96303f56?version=Cloud&Component=Region&Valid_as_Of=2026-11-02:2026-11-02). To subscribe to such notifications, see SAP Note [3513325](https://me.sap.com/notes/3513325).



<a name="loio07393cd4e83145688894a360e754f47c__section_s5b_3n2_2cc"/>

## Issue/Symptom

You are wondering if after a successful extension integration you get an automatically created extension subaccount.



<a name="loio07393cd4e83145688894a360e754f47c__section_gvm_kn2_2cc"/>

## Solution

No, you don't. You need to integrate the SAP SuccessFactors system either with a new dedicated subaccount that you create in advance, or you use an already existing subaccount. Have in mind that if you use an already existing subaccount, the identity provider might be changed after successful extension integration, and this might affect the Java/HTML5 applications that depend on the previous trust settings.

See [Create an Integration Token for SAP SuccessFactors](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6ef1e3bea61b4ad8a4ebf06637f43c96.html).

