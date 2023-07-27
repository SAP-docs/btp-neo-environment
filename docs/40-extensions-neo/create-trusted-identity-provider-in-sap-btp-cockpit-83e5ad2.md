<!-- loio83e5ad27cfbb4313a414c94073f72268 -->

# Create Trusted Identity Provider in SAP BTP Cockpit



<a name="loio83e5ad27cfbb4313a414c94073f72268__prereq_hpn_vjq_kcb"/>

## Prerequisites

You have created an OAuth X509 key and have saved the X509 certificate on your local file system. See [Generate OAuth X509 Key in SAP SuccessFactors](generate-oauth-x509-key-in-sap-successfactors-f636503.md).



## Context

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://launchpad.support.sap.com/#/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**

Register the certificate you downloaded when generating the OAuth X509 key in the SAP BTP cockpit.



## Procedure

1.  Go to the SAP BTP cockpit.

2.  Choose *Security* \> *Trust* \> *Application Identity Provider*.

3.  Choose *Add Trusted Identity Provider*.

4.  In the *Name* field, enter a name for the trusted identity provider.

5.  Find the certificate saved on your local file system and open it in a text editor. This is the certificate you downloaded when you created the OAuth X509 key. See [Generate OAuth X509 Key in SAP SuccessFactors](generate-oauth-x509-key-in-sap-successfactors-f636503.md).

6.  Copy the certificate content and paste it in the *Sigining Certificate* field.

7.  Select the *Only for IDP-Initiated SSO* checkbox.

    > ### Note:  
    > You don't need to change anything in the rest of the fields.

8.  Choose *Save*.


