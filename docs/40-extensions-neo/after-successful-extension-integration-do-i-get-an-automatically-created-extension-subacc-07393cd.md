<!-- loio07393cd4e83145688894a360e754f47c -->

# After Successful Extension Integration, Do I Get an Automatically Created Extension Subaccount? \(Neo Environment\)

After successful extension integration, do I get an automatically created extension subaccount?



<a name="loio07393cd4e83145688894a360e754f47c__section_s5b_3n2_2cc"/>

## Issue/Symptom

You are wondering if after a successful extension integration you get an automatically created extension subaccount.



<a name="loio07393cd4e83145688894a360e754f47c__section_gvm_kn2_2cc"/>

## Solution

No, you don't. You need to integrate the SAP SuccessFactors system either with a new dedicated subaccount that you create in advance, or you use an already existing subaccount. Have in mind that if you use an already existing subaccount, the identity provider might be changed after successful extension integration, and this might affect the Java/HTML5 applications that depend on the previous trust settings.

See [Create an Integration Token for SAP SuccessFactors](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6ef1e3bea61b4ad8a4ebf06637f43c96.html).

