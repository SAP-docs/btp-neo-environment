<!-- loioa4f1d55c57b446fc8d66a9f59009225f -->

# Using SAML Bearer Assertion Authentication



<a name="loioa4f1d55c57b446fc8d66a9f59009225f__context_wm5_tss_scb"/>

## Context

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**

To be able to use SAML Bearer Assertion authentication, you need to configure both SAP S/4HANA Cloud and SAP BTP sides.

**Related Information**  


[SAML Bearer Assertion Authentication](https://help.sap.com/viewer/cca91383641e40ffbe03bdc78f00f681/Cloud/en-US/e51e152ceaeb4b75affe5f15c65dfe6c.html)

[Set Up SAP S/4HANA Cloud Side](using-saml-bearer-assertion-authentication-a4f1d55.md#loio3b5d869c98044f039b6d400def2c0f0d "")

[Set Up SAP BTP Side](using-saml-bearer-assertion-authentication-a4f1d55.md#loio4da2a4450422409a9b4b237a9858d3ea "")

<a name="loio3b5d869c98044f039b6d400def2c0f0d"/>

<!-- loio3b5d869c98044f039b6d400def2c0f0d -->

## Set Up SAP S/4HANA Cloud Side



<a name="loio3b5d869c98044f039b6d400def2c0f0d__context_atn_wrs_scb"/>

## Context

From the SAP S/4HANA Cloud side you need to maintain the communication settings to configure the connectivity between SAP S/4HANA Cloud and SAP BTP.

> ### Note:  
> Make sure you have assigned the appropriate business catalogs to the propagated business users in the SAP S/4HANA Cloud tenant.



<a name="loio3b5d869c98044f039b6d400def2c0f0d__steps_ovc_3pt_scb"/>

## Procedure

1.  Create a communication user. See [Maintain Communication Users](https://help.sap.com/viewer/f544846954f24b9183eddadcc41bdc3b/1808.500/en-US/eef80dda3867461c92ac1273689ed36f.html).

2.  Create a communication system. See [Maintain Communication Systems](https://help.sap.com/viewer/f544846954f24b9183eddadcc41bdc3b/1808.500/en-US/15663c157670410ca366623dff329396.html).

    1.  Log into the SAP Fiori launchpad in the SAP S/4HANA Cloud system.

    2.  Select the *Communication Systems* tile.

    3.  Choose *New* to create a new system.

    4.  Enter a system ID and a system name.

    5.  Choose *Create*.

    6.  In the *Technical Data* section, in the *Host Name* field, enter the host of the subaccount in SAP BTP. To find all available hosts in the Neo environment, see [Regions and Hosts Available for the Neo Environment](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/350356d1dc314d3199dca15bd2ab9b0e.html#loiod722f7cea9ec408b85db4c3dcba07b52).

    7.  Enable the OAuth Identity Provider by checking the box under *OAuth 2.0 Identity Provider*.

    8.  Upload the signing certificate. This certificate is created from the metadata file you downloaded from your subaccount in SAP BTP in [Optional: Configure Single-Sign On Manually](optional-configure-single-sign-on-manually-789a120.md), Step 8. Follow these steps to prepare the certificate and upload it.

        1.  Open the `metadata` file with an editor of your choice. For the next configuration steps you will need the value of the `X509Certificate` tag.

        2.  Create a new file and copy the content between the `<X509Certificate>` tags into this file.

        3.  Add `-----BEGIN CERTIFICATE-----` to the top and `-----END CERTIFICATE-----` to the end of the file.

        4.  Save as a `x509.cer` file.

        5.  Back in the *Communication Systems* application select *Upload Signing Certificate* and upload the certificate you created.


    9.  Choose *\+* \(Add\) under *User for Inbound Communication*.

    10. In the dialog box that appears, select *User Name and Password* from the *Authentication Method* drop-down list.

        The username corresponds to the communication user.

    11. Choose *OK* to confirm.

    12. Choose *Save*.


3.  Create a communication arrangement and select a communication scenario. See [Maintain Communication Arrangements](https://help.sap.com/viewer/f544846954f24b9183eddadcc41bdc3b/1808.500/en-US/fab3fd449cf74c6384622b98831e989e.html).

    > ### Note:  
    > When you have the communication arrangement created, choose *OAuth 2.0 Details*. Copy and save locally the fields and their values. You will need them when setting up the destination in the SAP BTP cockpit.


<a name="loio4da2a4450422409a9b4b237a9858d3ea"/>

<!-- loio4da2a4450422409a9b4b237a9858d3ea -->

## Set Up SAP BTP Side



<a name="loio4da2a4450422409a9b4b237a9858d3ea__prereq_yhj_m5w_3bb"/>

## Prerequisites

You have logged into the SAP BTP cockpit from the landing page for your subaccount.



<a name="loio4da2a4450422409a9b4b237a9858d3ea__steps_vhq_fww_3bb"/>

## Procedure

1.  In the cockpit, navigate to your subaccount.

2.  Choose *Connectivity* \> *Destinations* in the navigation panel.

3.  Create an HTTP destination as follows:

    To enable principal propagation, create an *OAuth2SAMLBearerAssertion* HTTP destination and configure its settings as follows:

    1.  Configure the basic settings:


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
        
        `OAuth2SAMLBearerAssertion`


        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        `Audience`


        
        </td>
        <td valign="top">
        
        This is the *SAML2 Audience* from the *OAuth 2.0 Details* in the communication arrangement. See [Set Up SAP S/4HANA Cloud Side](using-saml-bearer-assertion-authentication-a4f1d55.md#loio3b5d869c98044f039b6d400def2c0f0d), **step 3**.


        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        `Client Key`


        
        </td>
        <td valign="top">
        
        The name of the communication user you have in the SAP S/4HANA Cloud tenant.


        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        `Token Service URL`


        
        </td>
        <td valign="top">
        
        This is the *Token Service URL* from the *OAuth 2.0 Details* in the communication arrangement. See [Set Up SAP S/4HANA Cloud Side](using-saml-bearer-assertion-authentication-a4f1d55.md#loio3b5d869c98044f039b6d400def2c0f0d), **step 3**.


        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        `Token Service User`


        
        </td>
        <td valign="top">
        
        The name of the communication user you have in the SAP S/4HANA Cloud tenant.


        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        `Token Service Password`


        
        </td>
        <td valign="top">
        
        The password for the communication user.


        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        `System User`


        
        </td>
        <td valign="top">
        
        This parameter is not used, leave the field empty.


        
        </td>
        </tr>
        </table>
        
    2.  Configure the required additional property. To do so, in the *Additional Properties* panel, choose *New Property*, and enter the following property:


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
        
        `authnContextClassRef`


        
        </td>
        <td valign="top">
        
        `urn:oasis:names:tc:SAML:2.0:ac:classes:X509` 


        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        scope


        
        </td>
        <td valign="top">
        
        \(Optional\) This parameter restricts the APIs that can be used by the OAuth Client.

        -   If the scope parameter is omitted, then all APIs that are exposed for the OAuth Client can be used.

        -   If the scope parameter is maintained, then only the related APIS can be used by the OAuth Client.


        The value of the OAuth 2.0 scope parameter expressed as a list of space-delimited, case-sensitive strings.


        
        </td>
        </tr>
        </table>
        
    3.  Select the *Use default JDK truststore* checkbox.

4.  Save your entries.


