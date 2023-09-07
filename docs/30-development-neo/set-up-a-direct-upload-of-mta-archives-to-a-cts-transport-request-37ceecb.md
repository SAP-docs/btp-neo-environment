<!-- loio37ceecb8a9dd4e63bbce42e3e2fab06c -->

# Set Up a Direct Upload of MTA Archives to a CTS+ Transport Request

Use the CTS+ Export Web Service to perform a transport of a multitarget application from one subaccount to another.



<a name="loio37ceecb8a9dd4e63bbce42e3e2fab06c__prereq_u2k_5hp_rcb"/>

## Prerequisites

-   You have activated and configured the CTS+ Export Web Service as described in [Activating and configuring CTS Export Web Service](https://help.sap.com/docs/SAP_DATA_SERVICES/62938f21156047718cae23da55f2b443/aa779d7c617143629a2c851f99eda4f1.html?version=4.2.7&language=en-US&q=active%20cts%20export).

    > ### Note:  
    > Make sure that you select the *Transport Channel Authentication and User ID / Password* as a provider security of the web service binding.

    Note the *Calculated Access URL* of the web service, which can be found in the transport settings.

    The *Calculated Access URL* follows the pattern `/sap/bc/srt/rfc/sap/export_cts_ws/<ABAP Client ID>/export_cts_ws/export_cts_ws`.

-   You have to define a user that is going to call the CTS+ Export Web Service. This user needs to have the following user roles:

    -   `SAP_BC_WEBSERVICE_CONSUMER`
    -   `SAP_CTS_PLUS`

    > ### Note:  
    > For more information about the CTS+ authorizations, see [1003674](https://me.sap.com/notes/1003674).

-   You have installed and configured the Cloud Connector, which is used to connect on-premise systems with the SAP BTP. For more information, see [Cloud Connector](https://help.sap.com/viewer/cca91383641e40ffbe03bdc78f00f681/Cloud/en-US/e6c7616abb5710148cfcf3e75d96d596.html).
-   You have exposed the CTS+ Export Web Service URLs as described in [Configure Access Control \(HTTP\)](https://help.sap.com/viewer/cca91383641e40ffbe03bdc78f00f681/Cloud/en-US/e7d4927dbb571014af7ef6ebd6cc3511.html).

    > ### Note:  
    > If you maintain a list of trusted applications and a principal propagation trust configuration, you have to authorize the application `services:slservice`.

-   Define the transport systems and route corresponding to your SAP BTP subaccounts. For more information, see [How To... Configure HCP for CTS](https://www.sap.com/documents/2016/07/bc3e9124-7d7c-0010-82c7-eda71af511fa.html)



## Context

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**



## Procedure

1.  In the SAP BTP cockpit, navigate to *Services* and enable the SAP BTP *Solution Lifecycle Management* service.

2.  Define the destinations leading to the on-premise systems. Navigate to *Services* \> *Solution Lifecycle Management* \> *Configure Destinations* \> *New Destination*.

3.  For the new destination configuration, enter the required parameters:

    -   Name: `TransportSystemCTS`

        > ### Note:  
        > This destination name is mandatory.

    -   Type: `HTTP`
    -   URL: `<Exposed URL of the system, taken from the Cloud Connector section, following the convention: https://<virtual host name>:<virtual port, such as 443>/<Calculated Access URL>>`

        > ### Example:  
        > `https://myctsplushost:443/sap/bc/srt/rfc/sap/export_cts_ws/001/export_cts_ws/export_cts_ws`

    -   Proxy Type: `OnPremise`
    -   Authentication: `BasicAuthentication`
    -   User: `<user name for the CTS+ on-premise system, which is configured in the Prerequisites section>`
    -   Password: `<password for the CTS+ on-premise system user>`

    You also have the following additional properties:

    -   \(Mandatory\) sourceSystemId: `<Name of the source node in the transport landscape, which has been defined in CTS+. That is typically the first node in the transport route and corresponds to the development subaccount in SAP BTP Neo environment.>`
    -   \(Optional\) chunkSizeMB: `<desired chunk size for the transported MTA>`

    > ### Note:  
    > You have to manually enter the attributes names, as they are not available in the drop-down list.




<a name="loio37ceecb8a9dd4e63bbce42e3e2fab06c__result_lkg_4yq_rcb"/>

## Results

For this feature to be consumed by the Cloud Platform Integration, see [Content Transport](https://help.sap.com/viewer/368c481cd6954bdfa5d0435479fd4eaf/Cloud/en-US/e3c79d65aa604b80992e20609881ad7a.html).

**Related Information**  


[Transporting Multitarget Applications with CTS+](transporting-multitarget-applications-with-cts-f598f69.md "You can enable transport of SAP BTP applications and application content that is available as Multitarget Applications (MTA) using the Enhanced Change and Transport System (CTS+).")

