<!-- loio0d7cf63b75a94f869895186a2d38db41 -->

# Enabling Client Certificate Authentication

You can enable the users for your Web application to authenticate using client certificates. This corresponds to the CERT and BASICCERT authentication methods supported in Java EE.

<a name="task_ds5_pmt_wn"/>

<!-- task\_ds5\_pmt\_wn -->

## Overview



## Prerequisites

\(For the mapping modes requiring certificate authorities\) You have a keystore defined. See [Keys and Certificates](keys-and-certificates-3735938.md).



## Context

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of the following technology portfolios: application development; process automation; integration; data, analytics, and enterprise planning; artificial intelligence. The platform offers users the ability to turn data into business value, compose end-to-end business processes, connect entire IT landscapes, and personalize, build and extend SAP applications. This reduces the overall total cost of ownership maintaining SAP landscapes and third-party software across end-to-end business processes.") :arrow_upper_right:.**

Using information in the client certificate, SAP BTP will map the certificate to a user name using the mapping mode you specify.

<a name="task_cm1_nmm_rv"/>

<!-- task\_cm1\_nmm\_rv -->

## 1. Configure Reverse Proxy to Request a Client Certificate



## Context

By default, SAP BTP supports SSL communication for Web applications through a reverse proxy that does not request a client certificate. To enable client certificate authentication, you need to configure the reverse proxy to request a client certificate.

Add `cert.hana.ondemand.com` as a platform domain. See [Using Platform Domains](../50-administration-and-ops-neo/using-platform-domains-a32d4cd.md#loioa32d4cd65be344439d9ed752f182e609).

For more information about the trusted certificate authorities \(CAs\) for SAP BTP, see [Trusted Certificate Authorities for Client Certificate Authentication](trusted-certificate-authorities-for-client-certificate-authentication-fe95707.md).

<a name="concept_xv5_md4_rv"/>

<!-- concept\_xv5\_md4\_rv -->

## 2. Protect Application Resources

In your Web application, use declarative or programmatic authentication to protect application resources.

Use one of the following two methods for client certificate authentication:

-   `CERT` - Users can authenticate only with client certificate.
-   `BASICCERT` - Users can authenticate either with client certificate or with user name and password.

If you use the declarative approach, you need to specify the authentication method in the application web.xml file. See [Declarative Authentication](authentication-e637f62.md#loioe36c712efa844e8199a9c4bd681cb4e0).

If you use the programmatic approach, specify the authentication method as a parameter for the login context creation. For more information, see [Programmatic Authentication](authentication-e637f62.md#loio778d8987e7714376977c190f6df379ad).

<a name="concept_rj3_3g4_rv"/>

<!-- concept\_rj3\_3g4\_rv -->

## 3. Define User Mapping

The user mapping defines how the user name is derived from the received client certificate. You configure user mapping using Java system properties.

Use the following system properties to define user mapping:

**System Properties for User Mappings**


<table>
<tr>
<th valign="top">

System Property

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

`com.sap.cloud.crypto.clientcert.mapping_mode`

</td>
<td valign="top">

\(Mandatory\) Defines how the received client certificate is interpreted.

</td>
</tr>
<tr>
<td valign="top">

`com.sap.cloud.crypto.clientcert.keystore_name`

</td>
<td valign="top">

Defines the name of the keystore used during the user mapping process, and it is mandatory for the mapping modes that use the keystore.

> ### Note:  
> Use a keystore that is available in the Keystore Service. See [Keys and Certificates](keys-and-certificates-3735938.md).

> ### Note:  
> Use the keystore name **without** the keystore file extension \(jks for example\).

> ### Note:  
> Depending on the value of the `com.sap.cloud.crypto.clientcert.mapping_mode` property,using the `com.sap.cloud.crypto.clientcert.keystore_name` property may be mandatory.



</td>
</tr>
</table>

For more information how to set the value of the system property, see [Configure VM Arguments](../50-administration-and-ops-neo/configure-vm-arguments-b82d392.md).

For more information about the particular values you need to set, see the table below.


<table>
<tr>
<th valign="top">

Mapping Mode

</th>
<th valign="top">

Description

</th>
<th valign="top">

How to Set

</th>
<th valign="top">

Example

</th>
</tr>
<tr>
<td valign="top">

CN

</td>
<td valign="top">

The user name equals the common name \(CN\) of the certificate’s subject.

</td>
<td valign="top">

Set the `com.sap.cloud.crypto.clientcert.mapping_mode` property with value CN.

In addition, if you want to accept certificates from trusted certificate authorities \(CAs\) only, set the `com.sap.cloud.crypto.clientcert.keystore_name` with a value the keystore name containing the trusted issuers.

> ### Note:  
> The client certificate is not accepted if its issuer is not in the keystore or is not in a chain trusted by this keystore, and then the authentication fails. For more information about the Keystore Service, see [Keys and Certificates](keys-and-certificates-3735938.md).

If you want to accept certificates from any issuer, skip setting the `com.sap.cloud.crypto.clientcert.keystore_name` property.

</td>
<td valign="top">

A client certificate with *cn=myuser,ou=security* as a subject is mapped to a *myuser* user name.

</td>
</tr>
<tr>
<td valign="top">

CN@issuer

</td>
<td valign="top">

For this mapping mode, the user name is defined as *<CN of the certificate’s subject\>@<keystore alias of the certificate’s issuer\>*. Use this mapping mode when you have certificates with identical CNs.

</td>
<td valign="top">

To use this mapping mode, you have to set the following system properties:

-   `com.sap.cloud.crypto.clientcert.mapping_mode` with a value *CN@Issuer*
-   `com.sap.cloud.crypto.clientcert.keystore_name` with a value the keystore name containing the trusted issuers

    The issuer is trusted if it is in the keystore or is part of a trusted certificate chain. A certificate chain is trusted if at least one of its issuers exists in the keystore.


> ### Note:  
> The client certificate is not accepted if its issuer is not in the keystore or is not in a chain trusted by this keystore, and then the authentication fails. For more information about setting the Keystore Service, see [Keys and Certificates](keys-and-certificates-3735938.md).



</td>
<td valign="top">

A client certificate with *CN=john, C=DE, O=SAP, OU=Development* as a subject and *CN=SSO CA, O=SAP* as an issuer is received. The specified keystore with trusted issuers contains the same issuer, *CN=SSO CA, O=SAP*, that has an *sso\_ca* alias. Then the user name is defined as *john@sso\_ca*.

</td>
</tr>
<tr>
<td valign="top">

wholeCert

</td>
<td valign="top">

For this mapping mode, the whole client certificate is compared with each entry in the specified keystore, and then the user name is defined as the alias of the matching entry.

</td>
<td valign="top">

To use this mapping mode, you have to set the following system properties:

-   `com.sap.cloud.crypto.clientcert.mapping_mode` with a value *wholeCert*
-   `com.sap.cloud.crypto.clientcert.keystore_name` with a value the keystore name containing the respective user certificates

> ### Note:  
> The client certificate is not accepted if no exact match is found in the specified keystore, and then the authentication fails. For more information about the Keystore Service, see [Keys and Certificates](keys-and-certificates-3735938.md).



</td>
<td valign="top">

The following client certificate is received:

`Subject:` *CN=john.miller, C=DE, O=SAP, OU=Development*

`Validity Start Date:` *March 19 09:04:32 2013 GMT*

`Validity End Date:` *March 19 09:04:32 2018 GMT*

…

The specified keystore contains the same certificate with an alias *john*. Then the user name is defined as *john*.

</td>
</tr>
<tr>
<td valign="top">

subjectAndIssuer

</td>
<td valign="top">

For this mapping mode, only the subject and issuer fields of the received client certificate are compared with the ones of each keystore entry, and then the user name is defined as the alias of the matching entry.

Use this mapping mode when you want authentication by validating only the certificate’s subject and issuer.

</td>
<td valign="top">

To use this mapping mode, you have to set the following system properties:

-   `com.sap.cloud.crypto.clientcert.mapping_mode` with a value *subjectAndIssuer*
-   `com.sap.cloud.crypto.clientcert.keystore_name` with a value the keystore name containing the respective user certificates

> ### Note:  
> The client certificate is not accepted if an entry with the same subject and issuer is missing in the specified keystore, and then the authentication fails. For more information about the Keystore Service, see [Keys and Certificates](keys-and-certificates-3735938.md).



</td>
<td valign="top">

A certificate with *CN=john.miller, C=DE, O=SAP, OU=Development* as a subject and *CN=SSO CA, O=SAP* as an issuer is received. The specified keystore contains a certificate with alias *john* that has the same subject and issuer fields. Then the user name is defined as *john*.

</td>
</tr>
</table>

<a name="task_fxt_x2z_52b"/>

<!-- task\_fxt\_x2z\_52b -->

## 4. Call the Application Using Client Certificate Authentication



<a name="task_fxt_x2z_52b__context_i5s_2yz_52b"/>

## Context

After you set up client certificate authentication, you need to use a special URL to call the application with that authentication type. You need to use the following URL pattern:

<code>https://&lt;my application&gt;<b>.cert</b>.&lt;SAP BTP region host&gt;/&lt;application resource&gt;</code>

> ### Note:  
> In comparison, the default application URL pattern at SAP BTP is:
> 
> <code>https://&lt;my application&gt;.&lt;SAP BTP region host&gt;/&lt;application resource&gt;</code>
> 
> So the difference is only in the <code><b>.cert</b></code> part.

For the available SAP BTP regions and their hosts, see [Regions](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/350356d1dc314d3199dca15bd2ab9b0e.html "You can deploy applications in different regions. Each region represents a geographical location (for example, Europe, US East) where applications, data, or services are hosted.") :arrow_upper_right:.

Example 1: You have an application running in the Europe \(Rot\) region. It has the following default application URL:

`https://bigideaX.hana.ondemand.com/exampleX`

To call the application with client certificate authentication, you need to use the following URL:

`https://bigideaX.cert.hana.ondemand.com/exampleX`

Example 2: You have an application running in the Canada \(Toronto\) region. It has the following default application URL:

`https://bigideaZ.ca1.hana.ondemand.com/exampleZ`

To call the application with client certificate authentication, you need to use the following URL:

`https://bigideaZ.cert.ca1.hana.ondemand.com/exampleZ`

