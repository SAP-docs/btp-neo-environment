<!-- loiof6365032efa7493383d413b882d94426 -->

# Generate OAuth X509 Key in SAP SuccessFactors



<a name="loiof6365032efa7493383d413b882d94426__prereq_edt_g2q_kcb"/>

## Prerequisites

You need to have permissions for the*Integration Center* in the SAP SuccessFactors system.



## Context

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/docs/btp/sap-business-technology-platform/sap-business-technology-platform?version=Cloud) .**

You have to generate the X.509 certificate in the SAP SuccessFactors system. Later on, you will add this certificate as a trusted identity provider in SAP BTP.



## Procedure

1.  Log on to the SAP SuccessFactors system, and go to the *Integration Center*.

2.  In the *Integration Center*, choose the *Security Center* tile and then choose the *OAuth X509 Keys*.

3.  Choose *Add* to create a new OAuth X509 key.

4.  In the *Configuration Name*, enter a name of your choice for the OAuth X509 key.

5.  In the *Common Name* field, replace the asterisk \(\*\) with the SAP SuccessFactors company ID.

6.  The *Description*, *Issued By*, *Organization*, *Organization Unit*, *Locality*, *State/Province*, and *Country*, *Valid for* fields are optional. You can fill them in as you like, there are no special requirements.

7.  Choose *Regenerate and Save*. Choose *OK* when you are asked to confirm this operation.

8.  Choose *Download X509 Certificate* and save the certificate on your local file system.

    > ### Note:  
    > By default, the name of the certificate is *<configuration\_name\>\_certificate.pem*.


