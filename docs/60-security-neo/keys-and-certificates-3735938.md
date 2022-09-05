<!-- loio3735938d1d1d4d04a0e976b9ad1799d5 -->

# Keys and Certificates

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**



<a name="loio3735938d1d1d4d04a0e976b9ad1799d5__section_N1001A_N10017_N10001"/>

## Overview

The Keystore Service provides a repository for cryptographic keys and certificates to the applications hosted on SAP BTP. By using the Keystore Service, the applications could easily retrieve keystores and use them in various cryptographic operations such as signing and verifying of digital signatures, encrypting and decrypting messages, and performing SSL communication.



<a name="loio3735938d1d1d4d04a0e976b9ad1799d5__section_N10027_N10017_N10001"/>

## Features

The SAP HANA Keystore Service stores and provides keystores encoded in the following formats:

-   Java Keystore \(JKS\)

    It supports password-based integrity validation for its content. Key entries are protected with password-based encryption. Password has to be specified in order to retrieve a key entry.

-   Extended Java Keystore \(JCEKS\)

    It provides the same functionality as the JKS format with stronger protection for private keys.

-   PKCS \#12 file \(P12\)

    This format supports password-based integrity validation for its content. Key entries are protected with password-based symmetric encryption. A password has to be specified in order to retrieve a key entry.

-   Privacy Enhanced Mail Certificate \(PEM\)

    It does not support integrity validation. Key entries are not protected with password.




<a name="loio3735938d1d1d4d04a0e976b9ad1799d5__section_N10047_N10017_N10001"/>

## Configuring Keystores

-   Local Server Configuration

    You can manage the keystores directly on the file system of the local server. Place the keystore files with **.jks**, **.pem**, **.jceks**, or **.p12** extension in the following folder: `<local server>/config_master/com.sap.cloud.crypto.keystore`.

-   Cloud Configuration

    You can manage the keystores via the SAP BTP console client. For more information, see [Keystore Console Commands](keystore-console-commands-20b6fbd.md).




<a name="loio3735938d1d1d4d04a0e976b9ad1799d5__section_N1008D_N10017_N10001"/>

## Keystore Search Order

The keystore service works with keystores available on the following levels:

-   Subscription level

    Keystores available for a certain application provided by another account.

-   Application level

    Keystores available for a certain application in a particular consumer account.

-   Account level

    Keystores available for all applications in a particular consumer account.


When searching for a keystore with a certain name, the keystore service will search on the different levels in following order: *Subscription level* \> *Application level* \> *Account level*.

Once a keystore with the specified name has been found at a certain location, further locations will no more be searched for.



<a name="loio3735938d1d1d4d04a0e976b9ad1799d5__section_N10073_N10017_N10001"/>

## Consuming the Keystore Service

To consume the Keystore Service, you need to add the following reference to your `web.xml` file:

```
<resource-ref>
   <res-ref-name>KeyStoreService</res-ref-name>
   <res-type>com.sap.cloud.crypto.keystore.api.KeyStoreService</res-type>
</resource-ref>
```

Then, in the code you can look up Keystore Service API via JNDI:

```
import com.sap.cloud.crypto.keystore.api.KeyStoreService;
...
KeyStoreService keystoreService = (KeyStoreService) new InitialContext().lookup("java:comp/env/KeyStoreService");

```

A keystore can be obtained by using the `getKeyStore()` method.

```
KeyStore keyStore = keystoreService.getKeyStore(keystoreName, keystorePassword);
```

For more information, see *Tutorial: Using the Keystore Service for Client Side HTTPS Connections*.

**Related Information**  


[Keystore Console Commands](keystore-console-commands-20b6fbd.md)

[Using the Keystore Service for Client Side HTTPS Connections](using-the-keystore-service-for-client-side-https-connections-38144cd.md)

