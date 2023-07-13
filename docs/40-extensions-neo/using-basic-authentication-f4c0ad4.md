<!-- loiof4c0ad4a1c7d44e992826bb5c939c487 -->

# Using Basic Authentication



<a name="loiof4c0ad4a1c7d44e992826bb5c939c487__context_pxs_prs_scb"/>

## Context

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**

To be able to use Basic authentication, you need to configure both SAP S/4HANA Cloud and SAP BTP sides.

**Related Information**  


[Set Up SAP S/4 HANA Cloud Side](using-basic-authentication-f4c0ad4.md#loio541cff3e17f14f4b8d7157c2e40f0925 "")

[Set Up SAP BTP Side](using-basic-authentication-f4c0ad4.md#loio647b45d968384fe89260aeffaf782543 "")

 <a name="loio541cff3e17f14f4b8d7157c2e40f0925"/>

<!-- loio541cff3e17f14f4b8d7157c2e40f0925 -->

## Set Up SAP S/4 HANA Cloud Side



<a name="loio541cff3e17f14f4b8d7157c2e40f0925__context_atn_wrs_scb"/>

## Context

From the SAP S/4HANA Cloud side you need to maintain the communication settings to configure the connectivity between SAP S/4HANA Cloud and SAP BTP.



## Procedure

1.  Create a communication user. See [Maintain Communication Users](https://help.sap.com/viewer/f544846954f24b9183eddadcc41bdc3b/1808.500/en-US/eef80dda3867461c92ac1273689ed36f.html).

2.  Create a communication system. See [Maintain Communication Systems](https://help.sap.com/viewer/f544846954f24b9183eddadcc41bdc3b/1808.500/en-US/15663c157670410ca366623dff329396.html).

    1.  Log into the SAP Fiori launchpad in the SAP S/4HANA Cloud system.

    2.  Select the *Communication Systems* tile.

    3.  Choose *New* to create a new system.

    4.  Enter a system ID and a system name.

    5.  Choose *Create*.

    6.  Enter information about SAP BTP in the *Technical Data* section.

    7.  Choose *\+* \(Add\) under *User for Inbound Communication*.

    8.  In the dialog box that appears, select *User Name and Password* from the *Authentication Method* drop-down list.

        The username corresponds to the communication user.

    9.  Choose *OK* to confirm.

    10. Choose *Save*.


3.  Create a communication arrangement and select a communication scenario. See [Maintain Communication Arrangements](https://help.sap.com/viewer/f544846954f24b9183eddadcc41bdc3b/1808.500/en-US/fab3fd449cf74c6384622b98831e989e.html).


**Related Information**  


[Communication Management](https://help.sap.com/viewer/f544846954f24b9183eddadcc41bdc3b/1808.500/en-US/2e84a10c430645a88bdbfaaa23ac9ff7.html)

 <a name="loio647b45d968384fe89260aeffaf782543"/>

<!-- loio647b45d968384fe89260aeffaf782543 -->

## Set Up SAP BTP Side



<a name="loio647b45d968384fe89260aeffaf782543__prereq_yhj_m5w_3bb"/>

## Prerequisites

You have logged into the SAP BTP cockpit from the landing page for your subaccount.



## Context



<a name="loio647b45d968384fe89260aeffaf782543__steps_vhq_fww_3bb"/>

## Procedure

1.  In the cockpit, navigate to your subaccount.

2.  Choose *Connectivity* \> *Destinations* in the navigation panel.

3.  Create an HTTP destination as follows:

    Create an *BasicAuthentication* HTTP destination and configure its settings as follows:


    <table>
    <tr>
    <th valign="top">

    Parameter


    
    </th>
    <th valign="top">

    Value


    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
        `Name`


    
    </td>
    <td valign="top">
    
        Enter a meaningful name.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
        `Type`


    
    </td>
    <td valign="top">
    
        `HTTP`


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
        `Description`


    
    </td>
    <td valign="top">
    
        \(Optional\) Enter a meaningful description.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
        `URL`


    
    </td>
    <td valign="top">
    
        The service URL from the communication arrangement.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
        `Proxy Type`


    
    </td>
    <td valign="top">
    
        `Internet`


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
        `Authentication`


    
    </td>
    <td valign="top">
    
        `BasicAuthentication`


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
        `User`


    
    </td>
    <td valign="top">
    
        The name of the communication user you have in the SAP S/4HANA Cloud tenant.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
        `Password`


    
    </td>
    <td valign="top">
    
        The password for the communication user.


    
    </td>
    </tr>
    </table>
    
4.  Select the *Use default JDK truststore* checkbox.

5.  Save your entries.


