<!-- loioba893b5161d34760989429c24b28f25b -->

# Configure OAuth Identity Provider in SAP Cloud for Customer

You need to add the SAP BTP service provider as a trusted OAuth identity provider.



## Context

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://launchpad.support.sap.com/#/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**



## Procedure

1.  In the SAP BTP cockpit, open the trust management setting of the subaccount. To do so, log on to the SAP BTP cockpit, select the region in which your subaccount is hosted, then select the global account that contains your subaccount, and then choose the tile of your subaccount. Choose *Security* \> *Trust*.

    1.  On the *Local Service Provider* tab page, choose *Edit* and select *Custom* from the dropdown list of the *Configuration Type* field.

    2.  Copy and save the entry from the *Local Provider Name* field.

    3.  Copy the entry from the *Signing Certificate* field, and save it in a file with the following format **<subaccount\>*\_signing.cer*, where *<subaccount\>* is the *Subaccount Name* from the *Subaccount Information* of your SAP BTP subaccount.


2.  Log on to your SAP Cloud for Customer system as an administrator. Go to *ADMINISTRATOR* \> *Common Tasks*. Choose *Configure OAuth 2.0 Identity Provider* \> *New OAuth2.0 Provider*, and configure the settings as follows:

    -   In the *Issuing Entity Name* field, paste the entry that you copied on **step 1b** \(the entry from the *Local Provider Name* field in the trust managing settings of the SAP BTP subaccount\).

    -   From the *Primary Signing Certificate* field, browse the **<subaccount\>*\_signing.cer* file that you saved on **step 1c**.
    -   Select the *E-Mail Address* checkbox.

3.  Choose *Submit*.


