<!-- loiod360a3d2af2d426d8243e44bd8ef6a30 -->

# Using Client Certificate Authentication



<a name="loiod360a3d2af2d426d8243e44bd8ef6a30__context_zkq_1wk_scb"/>

## Context

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**

To be able to use client certificate authentication, you need to configure both SAP S/4HANA Cloud and SAP BTP sides.

**Related Information**  


[Set Up SAP S/4HANA Cloud Side](using-client-certificate-authentication-d360a3d.md#loio8477e12f669b44feae3b77d7e47f1a18 "")

[Set Up SAP BTP Side](using-client-certificate-authentication-d360a3d.md#loio21d11edb36d148e49cec50fe4996ba00 "")

<a name="loio8477e12f669b44feae3b77d7e47f1a18"/>

<!-- loio8477e12f669b44feae3b77d7e47f1a18 -->

## Set Up SAP S/4HANA Cloud Side



## Context

To use client certificate authentication, you first start with creating and configuring the communication settings in the SAP S/4HANA Cloud tenant. To do that, you have to:



## Procedure

1.  Obtain a client certificate signed by a trusted certificate authority \(CA\) in *.pem* format. See [Keys and Certificates](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/3735938d1d1d4d04a0e976b9ad1799d5.html).

    You can find a list of the trusted CA in the SAP S/4HANA Cloud tenant using the **Maintain Certificate Trust List** application. See [Maintain Certificate Trust List](https://help.sap.com/viewer/f544846954f24b9183eddadcc41bdc3b/1808.500/en-US/2b3c3f1e4007472883abe5226e84f05f.html).

2.  Create a communication user and upload the public key. See [Maintain Communication Users](https://help.sap.com/viewer/f544846954f24b9183eddadcc41bdc3b/1808.500/en-US/eef80dda3867461c92ac1273689ed36f.html).

3.  Create a communication system and add the communication user as *User for Inbound Communication* with an authentication method SSL Client Certificate.

    1.  Log into the SAP Fiori launchpad in the SAP S/4HANA Cloud system.

    2.  Select the *Communication Systems* tile.

    3.  Choose *New* to create a new system.

    4.  Enter a system ID and a system name.

    5.  Choose *Create*.

    6.  Enter information about SAP BTP in the *Technical Data* section.

    7.  Choose *\+* \(Add\) under *User for Inbound Communication*.

    8.  In the dialog box that appears, select *SSL Client Certificate* from the *Authentication Method* drop-down list.

        The username corresponds to the communication user.

    9.  Choose *OK* to confirm.

    10. Choose *Save*.


4.  Create a communication arrangement using an existing or create a new scenario that supports client certificate authentication. See [Maintain Communication Arrangements](https://help.sap.com/viewer/f544846954f24b9183eddadcc41bdc3b/1808.500/en-US/fab3fd449cf74c6384622b98831e989e.html).

    You can use the already created communication system. The settings in the *Inbound Communication* section are filled in automatically. Save the value from the *URL* field, you will need it when creating a destination in the subaccount in SAP BTP.


<a name="loio21d11edb36d148e49cec50fe4996ba00"/>

<!-- loio21d11edb36d148e49cec50fe4996ba00 -->

## Set Up SAP BTP Side



<a name="loio21d11edb36d148e49cec50fe4996ba00__prereq_yhj_m5w_3bb"/>

## Prerequisites

You have logged into the SAP BTP cockpit from the landing page for your subaccount.



<a name="loio21d11edb36d148e49cec50fe4996ba00__steps_vhq_fww_3bb"/>

## Procedure

1.  In the cockpit, navigate to your subaccount.

2.  Choose *Connectivity* \> *Destinations* in the navigation panel.

3.  Create an HTTP destination as follows:

    To enable the support of SSO, create an *ClientCertificateAuthentication* HTTP destination and configure its settings as follows:


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
    
    `ClientCertificateAuthentication`
    
    </td>
    </tr>
    </table>
    
4.  Choose *Upload and Delete Certificate* link to upload your keystore. The keystore format .jks. When you finish uploading, choose Close.

    1.  From the *Key Store Location* drop-down menu, select your keystore.

    2.  In the *Key Store Password*, enter the keystore password.


5.  Select the *Use default JDK truststore* checkbox.

6.  Save your entries.


