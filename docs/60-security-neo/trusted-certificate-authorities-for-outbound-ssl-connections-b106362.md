<!-- loiob106362a8607444db7d2c6c9acdd4668 -->

# Trusted Certificate Authorities for Outbound SSL Connections

List of certificate authorities trusted by the virtual machines running the applications.



> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/docs/btp/sap-business-technology-platform/sap-business-technology-platform?version=Cloud) .**



The virtual machines for applications trust the below-listed certificate authorities \(CAs\) by default. This means that the external HTTPS services which use X.509 server certificates \(which are issued by those CAs\), are trusted by default. No trust needs to be configured manually.

For SSL connections to services which use different certificate issuers, you need to configure trust to use the keystore service of the platform. For more information, see [Using the Keystore Service for Client Side HTTPS Connections](using-the-keystore-service-for-client-side-https-connections-38144cd.md).



Trusted certificate authorities:


<table>
<tr>
<th valign="top">

Certificate Alias

</th>
<th valign="top">

Certificate Name

</th>
<th valign="top">

Certificate SHA1

</th>
</tr>
<tr>
<td valign="top">

actalisauthenticationrootca \[jdk\]

</td>
<td valign="top">

CN=Actalis Authentication Root CA, O=Actalis S.p.A./03358520967, L=Milan, C=IT

</td>
<td valign="top">

F3:73:B3:87:06:5A:28:84:8A:F2:F3:4A:CE:19:2B:DD:C7:8E:9C:AC

</td>
</tr>
<tr>
<td valign="top">

affirmtrustcommercialca \[jdk\]

</td>
<td valign="top">

CN=AffirmTrust Commercial, O=AffirmTrust, C=US

</td>
<td valign="top">

F9:B5:B6:32:45:5F:9C:BE:EC:57:5F:80:DC:E9:6E:2C:C7:B2:78:B7

</td>
</tr>
<tr>
<td valign="top">

affirmtrustnetworkingca \[jdk\]

</td>
<td valign="top">

CN=AffirmTrust Networking, O=AffirmTrust, C=US

</td>
<td valign="top">

29:36:21:02:8B:20:ED:02:F5:66:C5:32:D1:D6:ED:90:9F:45:00:2F

</td>
</tr>
<tr>
<td valign="top">

affirmtrustpremiumca \[jdk\]

</td>
<td valign="top">

CN=AffirmTrust Premium, O=AffirmTrust, C=US

</td>
<td valign="top">

D8:A6:33:2C:E0:03:6F:B1:85:F6:63:4F:7D:6A:06:65:26:32:28:27

</td>
</tr>
<tr>
<td valign="top">

affirmtrustpremiumeccca \[jdk\]

</td>
<td valign="top">

CN=AffirmTrust Premium ECC, O=AffirmTrust, C=US

</td>
<td valign="top">

B8:23:6B:00:2F:1D:16:86:53:01:55:6C:11:A4:37:CA:EB:FF:C3:BB

</td>
</tr>
<tr>
<td valign="top">

amazonrootca1 \[jdk\]

</td>
<td valign="top">

CN=Amazon Root CA 1, O=Amazon, C=US

</td>
<td valign="top">

8D:A7:F9:65:EC:5E:FC:37:91:0F:1C:6E:59:FD:C1:CC:6A:6E:DE:16

</td>
</tr>
<tr>
<td valign="top">

amazonrootca2 \[jdk\]

</td>
<td valign="top">

CN=Amazon Root CA 2, O=Amazon, C=US

</td>
<td valign="top">

5A:8C:EF:45:D7:A6:98:59:76:7A:8C:8B:44:96:B5:78:CF:47:4B:1A

</td>
</tr>
<tr>
<td valign="top">

amazonrootca3 \[jdk\]

</td>
<td valign="top">

CN=Amazon Root CA 3, O=Amazon, C=US

</td>
<td valign="top">

0D:44:DD:8C:3C:8C:1A:1A:58:75:64:81:E9:0F:2E:2A:FF:B3:D2:6E

</td>
</tr>
<tr>
<td valign="top">

amazonrootca4 \[jdk\]

</td>
<td valign="top">

CN=Amazon Root CA 4, O=Amazon, C=US

</td>
<td valign="top">

F6:10:84:07:D6:F8:BB:67:98:0C:C2:E2:44:C2:EB:AE:1C:EF:63:BE

</td>
</tr>
<tr>
<td valign="top">

atostrustedroot2011

</td>
<td valign="top">

C=DE, O=Atos, CN=Atos TrustedRoot 2011

</td>
<td valign="top">

2B:B1:F5:3E:55:0C:1D:C5:F1:D4:E6:B7:6A:46:4B:55:06:02:AC:21

</td>
</tr>
<tr>
<td valign="top">

buypassclass2ca \[jdk\]

</td>
<td valign="top">

CN=Buypass Class 2 Root CA, O=Buypass AS-983163327, C=NO

</td>
<td valign="top">

49:0A:75:74:DE:87:0A:47:FE:58:EE:F6:C7:6B:EB:C6:0B:12:40:99

</td>
</tr>
<tr>
<td valign="top">

buypassclass3ca \[jdk\]

</td>
<td valign="top">

CN=Buypass Class 3 Root CA, O=Buypass AS-983163327, C=NO

</td>
<td valign="top">

DA:FA:F7:FA:66:84:EC:06:8F:14:50:BD:C7:C2:81:A5:BC:A9:64:57

</td>
</tr>
<tr>
<td valign="top">

camerfirmachambersca \[jdk\]

</td>
<td valign="top">

CN=Chambers of Commerce Root - 2008, O=AC Camerfirma S.A., SERIALNUMBER=A82743287, L=Madrid \(see current address at www.camerfirma.com/address\), C=EU

</td>
<td valign="top">

78:6A:74:AC:76:AB:14:7F:9C:6A:30:50:BA:9E:A8:7E:FE:9A:CE:3C

</td>
</tr>
<tr>
<td valign="top">

certainlyroote1 \[jdk\]

</td>
<td valign="top">

CN=Certainly Root E1, O=Certainly, C=US

</td>
<td valign="top">

F9:E1:6D:DC:01:89:CF:D5:82:45:63:3E:C5:37:7D:C2:EB:93:6F:2B

</td>
</tr>
<tr>
<td valign="top">

certainlyrootr1 \[jdk\]

</td>
<td valign="top">

CN=Certainly Root R1, O=Certainly, C=US

</td>
<td valign="top">

A0:50:EE:0F:28:71:F4:27:B2:12:6D:6F:50:96:25:BA:CC:86:42:AF

</td>
</tr>
<tr>
<td valign="top">

certignaca \[jdk\]

</td>
<td valign="top">

CN=Certigna, O=Dhimyotis, C=FR

</td>
<td valign="top">

B1:2E:13:63:45:86:A4:6F:1A:B2:60:68:37:58:2D:C4:AC:FD:94:97

</td>
</tr>
<tr>
<td valign="top">

certignarootca \[jdk\]

</td>
<td valign="top">

CN=Certigna Root CA, OU=0002 48146308100036, O=Dhimyotis, C=FR

</td>
<td valign="top">

2D:0D:52:14:FF:9E:AD:99:24:01:74:20:47:6E:6C:85:27:27:F5:43

</td>
</tr>
<tr>
<td valign="top">

certumca \[jdk\]

</td>
<td valign="top">

CN=Certum CA, O=Unizeto Sp. z o.o., C=PL

</td>
<td valign="top">

62:52:DC:40:F7:11:43:A2:2F:DE:9E:F7:34:8E:06:42:51:B1:81:18

</td>
</tr>
<tr>
<td valign="top">

certumtrustednetworkca \[jdk\]

</td>
<td valign="top">

CN=Certum Trusted Network CA, OU=Certum Certification Authority, O=Unizeto Technologies S.A., C=PL

</td>
<td valign="top">

07:E0:32:E0:20:B7:2C:3F:19:2F:06:28:A2:59:3A:19:A7:0F:06:9E

</td>
</tr>
<tr>
<td valign="top">

chunghwaepkirootca \[jdk\]

</td>
<td valign="top">

OU=ePKI Root Certification Authority, O="Chunghwa Telecom Co., Ltd.", C=TW

</td>
<td valign="top">

67:65:0D:F1:7E:8E:7E:5B:82:40:A4:F4:56:4B:CF:E2:3D:69:C6:F0

</td>
</tr>
<tr>
<td valign="top">

comodoaaaca \[jdk\]

</td>
<td valign="top">

CN=AAA Certificate Services, O=Comodo CA Limited, L=Salford, ST=Greater Manchester, C=GB

</td>
<td valign="top">

D1:EB:23:A4:6D:17:D6:8F:D9:25:64:C2:F1:F1:60:17:64:D8:E3:49

</td>
</tr>
<tr>
<td valign="top">

comodoeccca \[jdk\]

</td>
<td valign="top">

CN=COMODO ECC Certification Authority, O=COMODO CA Limited, L=Salford, ST=Greater Manchester, C=GB

</td>
<td valign="top">

9F:74:4E:9F:2B:4D:BA:EC:0F:31:2C:50:B6:56:3B:8E:2D:93:C3:11

</td>
</tr>
<tr>
<td valign="top">

comodorsaca

</td>
<td valign="top">

CN=COMODO RSA Certification Authority, O=COMODO CA Limited, L=Salford, ST=Greater Manchester, C=GB

</td>
<td valign="top">

AF:E5:D2:44:A8:D1:19:42:30:FF:47:9F:E2:F8:97:BB:CD:7A:8C:B4

</td>
</tr>
<tr>
<td valign="top">

digicertassuredidg2 \[jdk\]

</td>
<td valign="top">

CN=DigiCert Assured ID Root G2, OU=www.digicert.com, O=DigiCert Inc, C=US

</td>
<td valign="top">

A1:4B:48:D9:43:EE:0A:0E:40:90:4F:3C:E0:A4:C0:91:93:51:5D:3F

</td>
</tr>
<tr>
<td valign="top">

digicertassuredidg3 \[jdk\]

</td>
<td valign="top">

CN=DigiCert Assured ID Root G3, OU=www.digicert.com, O=DigiCert Inc, C=US

</td>
<td valign="top">

F5:17:A2:4F:9A:48:C6:C9:F8:A2:00:26:9F:DC:0F:48:2C:AB:30:89

</td>
</tr>
<tr>
<td valign="top">

digicertassuredidrootca

</td>
<td valign="top">

CN=DigiCert Assured ID Root CA, OU=www.digicert.com, O=DigiCert Inc, C=US

</td>
<td valign="top">

05:63:B8:63:0D:62:D7:5A:BB:C8:AB:1E:4B:DF:B5:A8:99:B2:4D:43

</td>
</tr>
<tr>
<td valign="top">

digicertcseccrootg5 \[jdk\]

</td>
<td valign="top">

CN=DigiCert CS ECC P384 Root G5, O="DigiCert, Inc.", C=US

</td>
<td valign="top">

84:35:73:11:2A:3B:31:93:44:E5:E4:EC:AB:C9:F2:6C:7C:D5:4D:07

</td>
</tr>
<tr>
<td valign="top">

digicertcsrsarootg5 \[jdk\]

</td>
<td valign="top">

CN=DigiCert CS RSA4096 Root G5, O="DigiCert, Inc.", C=US

</td>
<td valign="top">

5E:EE:D8:6F:A3:7C:67:52:30:64:2F:55:C8:4D:DB:F6:7C:D3:3C:80

</td>
</tr>
<tr>
<td valign="top">

digicertglobalrootca\_g2

</td>
<td valign="top">

CN=DigiCert Global Root G2, OU=www.digicert.com, O=DigiCert Inc, C=US

</td>
<td valign="top">

DF:3C:24:F9:BF:D6:66:76:1B:26:80:73:FE:06:D1:CC:8D:4F:82:A4

</td>
</tr>
<tr>
<td valign="top">

digicertglobalrootcalss2\_g3

</td>
<td valign="top">

CN=DigiCert Global Root CA, OU=www.digicert.com, O=DigiCert Inc, C=US

</td>
<td valign="top">

A8:98:5D:3A:65:E5:E5:C4:B2:D7:D6:6D:40:C6:DD:2F:B1:9C:54:36

</td>
</tr>
<tr>
<td valign="top">

digicertglobalrootg3 \[jdk\]

</td>
<td valign="top">

CN=DigiCert Global Root G3, OU=www.digicert.com, O=DigiCert Inc, C=US

</td>
<td valign="top">

7E:04:DE:89:6A:3E:66:6D:00:E6:87:D3:3F:FA:D9:3B:E8:3D:34:9E

</td>
</tr>
<tr>
<td valign="top">

digicerthighassuranceevrootca

</td>
<td valign="top">

CN=DigiCert High Assurance EV Root CA, OU=www.digicert.com, O=DigiCert Inc, C=US

</td>
<td valign="top">

5F:B7:EE:06:33:E2:59:DB:AD:0C:4C:9A:E6:D3:8F:1A:61:C7:DC:25

</td>
</tr>
<tr>
<td valign="top">

digicerttlseccrootg5 \[jdk\]

</td>
<td valign="top">

CN=DigiCert TLS ECC P384 Root G5, O="DigiCert, Inc.", C=US

</td>
<td valign="top">

17:F3:DE:5E:9F:0F:19:E9:8E:F6:1F:32:26:6E:20:C4:07:AE:30:EE

</td>
</tr>
<tr>
<td valign="top">

digicerttlsrsarootg5 \[jdk\]

</td>
<td valign="top">

CN=DigiCert TLS RSA4096 Root G5, O="DigiCert, Inc.", C=US

</td>
<td valign="top">

A7:88:49:DC:5D:7C:75:8C:8C:DE:39:98:56:B3:AA:D0:B2:A5:71:35

</td>
</tr>
<tr>
<td valign="top">

digicerttrustedrootg4 \[jdk\]

</td>
<td valign="top">

CN=DigiCert Trusted Root G4, OU=www.digicert.com, O=DigiCert Inc, C=US

</td>
<td valign="top">

DD:FB:16:CD:49:31:C9:73:A2:03:7D:3F:C8:3A:4D:7D:77:5D:05:E4

</td>
</tr>
<tr>
<td valign="top">

dtrustclass3ca2 \[jdk\]

</td>
<td valign="top">

CN=D-TRUST Root Class 3 CA 2 2009, O=D-Trust GmbH, C=DE

</td>
<td valign="top">

58:E8:AB:B0:36:15:33:FB:80:F7:9B:1B:6D:29:D3:FF:8D:5F:00:F0

</td>
</tr>
<tr>
<td valign="top">

dtrustclass3ca2ev \[jdk\]

</td>
<td valign="top">

CN=D-TRUST Root Class 3 CA 2 EV 2009, O=D-Trust GmbH, C=DE

</td>
<td valign="top">

96:C9:1B:0B:95:B4:10:98:42:FA:D0:D8:22:79:FE:60:FA:B9:16:83

</td>
</tr>
<tr>
<td valign="top">

emsigneccrootcag3 \[jdk\]

</td>
<td valign="top">

CN=emSign ECC Root CA - G3, O=eMudhra Technologies Limited, OU=emSign PKI, C=IN

</td>
<td valign="top">

30:43:FA:4F:F2:57:DC:A0:C3:80:EE:2E:58:EA:78:B2:3F:E6:BB:C1

</td>
</tr>
<tr>
<td valign="top">

emsignrootcag1 \[jdk\]

</td>
<td valign="top">

CN=emSign Root CA - G1, O=eMudhra Technologies Limited, OU=emSign PKI, C=IN

</td>
<td valign="top">

8A:C7:AD:8F:73:AC:4E:C1:B5:75:4D:A5:40:F4:FC:CF:7C:B5:8E:8C

</td>
</tr>
<tr>
<td valign="top">

emsignrootcag2 \[jdk\]

</td>
<td valign="top">

CN=emSign Root CA - G2, O=eMudhra Technologies Limited, OU=emSign PKI, C=IN

</td>
<td valign="top">

1E:65:77:B9:CF:70:D0:17:CA:E1:BD:A1:35:1D:47:25:A9:73:C0:6D

</td>
</tr>
<tr>
<td valign="top">

entrust\_ca\_2048

</td>
<td valign="top">

CN=Entrust.net Certification Authority \(2048\), OU=\(c\) 1999 Entrust.net Limited, OU=www.entrust.net/CPS\_2048 incorp. by ref. \(limits liab.\), O=Entrust.net

</td>
<td valign="top">

50:30:06:09:1D:97:D4:F5:AE:39:F7:CB:E7:92:7D:7D:65:2D:34:31

</td>
</tr>
<tr>
<td valign="top">

entrust\_ev\_ca

</td>
<td valign="top">

CN=Entrust Root Certification Authority, OU="\(c\) 2006 Entrust, Inc.", OU=www.entrust.net/CPS is incorporated by reference, O="Entrust, Inc.", C=US

</td>
<td valign="top">

B3:1E:B1:B7:40:E3:6C:84:02:DA:DC:37:D4:4D:F5:D4:67:49:52:F9

</td>
</tr>
<tr>
<td valign="top">

entrust\_g2\_ca

</td>
<td valign="top">

CN=Entrust Root Certification Authority - G2, OU="\(c\) 2009 Entrust, Inc. - for authorized use only", OU=See www.entrust.net/legal-terms, O="Entrust, Inc.", C=US

</td>
<td valign="top">

8C:F4:27:FD:79:0C:3A:D1:66:06:8D:E8:1E:57:EF:BB:93:22:72:D4

</td>
</tr>
<tr>
<td valign="top">

entrustrootcaec1 \[jdk\]

</td>
<td valign="top">

CN=Entrust Root Certification Authority - EC1, OU="\(c\) 2012 Entrust, Inc. - for authorized use only", OU=See www.entrust.net/legal-terms, O="Entrust, Inc.", C=US

</td>
<td valign="top">

20:D8:06:40:DF:9B:25:F5:12:25:3A:11:EA:F7:59:8A:EB:14:B5:47

</td>
</tr>
<tr>
<td valign="top">

entrustrootcag4 \[jdk\]

</td>
<td valign="top">

CN=Entrust Root Certification Authority - G4, OU="\(c\) 2015 Entrust, Inc. - for authorized use only", OU=See www.entrust.net/legal-terms, O="Entrust, Inc.", C=US

</td>
<td valign="top">

14:88:4E:86:26:37:B0:26:AF:59:62:5C:40:77:EC:35:29:BA:96:01

</td>
</tr>
<tr>
<td valign="top">

gd-class2-root

</td>
<td valign="top">

OU=Go Daddy Class 2 Certification Authority, O="The Go Daddy Group, Inc.", C=US

</td>
<td valign="top">

27:96:BA:E6:3F:18:01:E2:77:26:1B:A0:D7:77:70:02:8F:20:EE:E4

</td>
</tr>
<tr>
<td valign="top">

gd\_intermediate

</td>
<td valign="top">

SERIALNUMBER=07969287, CN=Go Daddy Secure Certification Authority, OU=http://certificates.godaddy.com/repository, O="GoDaddy.com, Inc.", L=Scottsdale, ST=Arizona, C=US

</td>
<td valign="top">

7C:46:56:C3:06:1F:7F:4C:0D:67:B3:19:A8:55:F6:0E:BC:11:FC:44

</td>
</tr>
<tr>
<td valign="top">

gdroot-g2

</td>
<td valign="top">

CN=Go Daddy Root Certificate Authority - G2, O="GoDaddy.com, Inc.", L=Scottsdale, ST=Arizona, C=US

</td>
<td valign="top">

47:BE:AB:C9:22:EA:E8:0E:78:78:34:62:A7:9F:45:C2:54:FD:E6:8B

</td>
</tr>
<tr>
<td valign="top">

geotrust\_pca\_g3\_root

</td>
<td valign="top">

CN=GeoTrust Primary Certification Authority - G3, OU=\(c\) 2008 GeoTrust Inc. - For authorized use only, O=GeoTrust Inc., C=US

</td>
<td valign="top">

03:9E:ED:B8:0B:E7:A0:3C:69:53:89:3B:20:D2:D9:32:3A:4C:2A:FD

</td>
</tr>
<tr>
<td valign="top">

geotrustglobalca

</td>
<td valign="top">

CN=GeoTrust Global CA, O=GeoTrust Inc., C=US

</td>
<td valign="top">

DE:28:F4:A4:FF:E5:B9:2F:A3:C5:03:D1:A3:49:A7:F9:96:2A:82:12

</td>
</tr>
<tr>
<td valign="top">

geotrustprimaryca

</td>
<td valign="top">

CN=GeoTrust Primary Certification Authority, O=GeoTrust Inc., C=US

</td>
<td valign="top">

32:3C:11:8E:1B:F7:B8:B6:52:54:E2:E2:10:0D:D6:02:90:37:F0:96

</td>
</tr>
<tr>
<td valign="top">

geotrustprimarycag2 \[jdk\]

</td>
<td valign="top">

CN=GeoTrust Primary Certification Authority - G2, OU=\(c\) 2007 GeoTrust Inc. - For authorized use only, O=GeoTrust Inc., C=US

</td>
<td valign="top">

8D:17:84:D5:37:F3:03:7D:EC:70:FE:57:8B:51:9A:99:E6:10:D7:B0

</td>
</tr>
<tr>
<td valign="top">

geotrustuniversalca

</td>
<td valign="top">

CN=GeoTrust Universal CA, O=GeoTrust Inc., C=US

</td>
<td valign="top">

E6:21:F3:35:43:79:05:9A:4B:68:30:9D:8A:2F:74:22:15:87:EC:79

</td>
</tr>
<tr>
<td valign="top">

globalsignca

</td>
<td valign="top">

CN=GlobalSign Root CA, OU=Root CA, O=GlobalSign nv-sa, C=BE

</td>
<td valign="top">

B1:BC:96:8B:D4:F4:9D:62:2A:A8:9A:81:F2:15:01:52:A4:1D:82:9C

</td>
</tr>
<tr>
<td valign="top">

globalsigne46 jdk

</td>
<td valign="top">

CN=GlobalSign Root E46, O=GlobalSign nv-sa, C=BE

</td>
<td valign="top">

39:B4:6C:D5:FE:80:06:EB:E2:2F:4A:BB:08:33:A0:AF:DB:B9:DD:84

</td>
</tr>
<tr>
<td valign="top">

globalsigneccrootcar4 \[jdk\]

</td>
<td valign="top">

CN=GlobalSign, O=GlobalSign, OU=GlobalSign ECC Root CA - R4

</td>
<td valign="top">

69:69:56:2E:40:80:F4:24:A1:E7:19:9F:14:BA:F3:EE:58:AB:6A:BB

</td>
</tr>
<tr>
<td valign="top">

globalsigneccrootcar5 \[jdk\]

</td>
<td valign="top">

CN=GlobalSign, O=GlobalSign, OU=GlobalSign ECC Root CA - R5

</td>
<td valign="top">

1F:24:C6:30:CD:A4:18:EF:20:69:FF:AD:4F:DD:5F:46:3A:1B:69:AA

</td>
</tr>
<tr>
<td valign="top">

globalsigneccrootcar6

</td>
<td valign="top">

CN=GlobalSign, O=GlobalSign, OU=GlobalSign Root CA - R6

</td>
<td valign="top">

80:94:64:0E:B5:A7:A1:CA:11:9C:1F:DD:D5:9F:81:02:63:A7:FB:D1

</td>
</tr>
<tr>
<td valign="top">

globalsignr3ca

</td>
<td valign="top">

CN=GlobalSign, O=GlobalSign, OU=GlobalSign Root CA - R3

</td>
<td valign="top">

D6:9B:56:11:48:F0:1C:77:C5:45:78:C1:09:26:DF:5B:85:69:76:AD

</td>
</tr>
<tr>
<td valign="top">

globalsignr46 jdk

</td>
<td valign="top">

CN=GlobalSign Root R46, O=GlobalSign nv-sa, C=BE

</td>
<td valign="top">

53:A2:B0:4B:CA:6B:D6:45:E6:39:8A:8E:C4:0D:D2:BF:77:C3:A2:90

</td>
</tr>
<tr>
<td valign="top">

gtsrootcar1 \[jdk\]

</td>
<td valign="top">

CN=GTS Root R1, O=Google Trust Services LLC, C=US

</td>
<td valign="top">

E5:8C:1C:C4:91:3B:38:63:4B:E9:10:6E:E3:AD:8E:6B:9D:D9:81:4A

</td>
</tr>
<tr>
<td valign="top">

gtsrootcar2 \[jdk\]

</td>
<td valign="top">

CN=GTS Root R2, O=Google Trust Services LLC, C=US

</td>
<td valign="top">

9A:44:49:76:32:DB:DE:FA:D0:BC:FB:5A:7B:17:BD:9E:56:09:24:94

</td>
</tr>
<tr>
<td valign="top">

gtsrootecccar3 \[jdk\]

</td>
<td valign="top">

CN=GTS Root R3, O=Google Trust Services LLC, C=US

</td>
<td valign="top">

ED:E5:71:80:2B:C8:92:B9:5B:83:3C:D2:32:68:3F:09:CD:A0:1E:46

</td>
</tr>
<tr>
<td valign="top">

gtsrootecccar4 \[jdk\]

</td>
<td valign="top">

CN=GTS Root R4, O=Google Trust Services LLC, C=US

</td>
<td valign="top">

77:D3:03:67:B5:E0:0C:15:F6:0C:38:61:DF:7C:E1:3B:92:46:4D:47

</td>
</tr>
<tr>
<td valign="top">

haricaeccrootca2015 \[jdk\]

</td>
<td valign="top">

CN=Hellenic Academic and Research Institutions ECC RootCA 2015, O=Hellenic Academic and Research Institutions Cert. Authority, L=Athens, C=GR

</td>
<td valign="top">

9F:F1:71:8D:92:D5:9A:F3:7D:74:97:B4:BC:6F:84:68:0B:BA:B6:66

</td>
</tr>
<tr>
<td valign="top">

haricarootca2015 \[jdk\]

</td>
<td valign="top">

CN=Hellenic Academic and Research Institutions RootCA 2015, O=Hellenic Academic and Research Institutions Cert. Authority, L=Athens, C=GR

</td>
<td valign="top">

01:0C:06:95:A6:98:19:14:FF:BF:5F:C6:B0:B6:95:EA:29:E9:12:A6

</td>
</tr>
<tr>
<td valign="top">

identrustcommercial \[jdk\]

</td>
<td valign="top">

CN=IdenTrust Commercial Root CA 1, O=IdenTrust, C=US

</td>
<td valign="top">

DF:71:7E:AA:4A:D9:4E:C9:55:84:99:60:2D:48:DE:5F:BC:F0:3A:25

</td>
</tr>
<tr>
<td valign="top">

identrustpublicca \[jdk\]

</td>
<td valign="top">

CN=IdenTrust Public Sector Root CA 1, O=IdenTrust, C=US

</td>
<td valign="top">

BA:29:41:60:77:98:3F:F4:F3:EF:F2:31:05:3B:2E:EA:6D:4D:45:FD

</td>
</tr>
<tr>
<td valign="top">

letsencryptisrgx1 \[jdk\]

</td>
<td valign="top">

CN=ISRG Root X1, O=Internet Security Research Group, C=US

</td>
<td valign="top">

CA:BD:2A:79:A1:07:6A:31:F2:1D:25:36:35:CB:03:9D:43:29:A5:E8

</td>
</tr>
<tr>
<td valign="top">

letsencryptisrgx2 \[jdk\]

</td>
<td valign="top">

CN=ISRG Root X2, O=Internet Security Research Group, C=US

</td>
<td valign="top">

BD:B1:B9:3C:D5:97:8D:45:C6:26:14:55:F8:DB:95:C7:5A:D1:53:AF

</td>
</tr>
<tr>
<td valign="top">

luxtrustglobalroot2ca \[jdk\]

</td>
<td valign="top">

CN=LuxTrust Global Root 2, O=LuxTrust S.A., C=LU

</td>
<td valign="top">

1E:0E:56:19:0A:D1:8B:25:98:B2:04:44:FF:66:8A:04:17:99:5F:3F

</td>
</tr>
<tr>
<td valign="top">

microsoftecc2017 \[jdk\]

</td>
<td valign="top">

CN=Microsoft ECC Root Certificate Authority 2017, O=Microsoft Corporation, C=US

</td>
<td valign="top">

99:9A:64:C3:7F:F4:7D:9F:AB:95:F1:47:69:89:14:60:EE:C4:C3:C5

</td>
</tr>
<tr>
<td valign="top">

microsoftrsa2017 \[jdk\]

</td>
<td valign="top">

CN=Microsoft RSA Root Certificate Authority 2017, O=Microsoft Corporation, C=US

</td>
<td valign="top">

73:A5:E6:4A:3B:FF:83:16:FF:0E:DC:CC:61:8A:90:6E:4E:AE:4D:74

</td>
</tr>
<tr>
<td valign="top">

quovadisrootca1g3 \[jdk\]

</td>
<td valign="top">

CN=QuoVadis Root CA 1 G3, O=QuoVadis Limited, C=BM

</td>
<td valign="top">

1B:8E:EA:57:96:29:1A:C9:39:EA:B8:0A:81:1A:73:73:C0:93:79:67

</td>
</tr>
<tr>
<td valign="top">

quovadisrootca2 \[jdk\]

</td>
<td valign="top">

CN=QuoVadis Root CA 2, O=QuoVadis Limited, C=BM

</td>
<td valign="top">

CA:3A:FB:CF:12:40:36:4B:44:B2:16:20:88:80:48:39:19:93:7C:F7

</td>
</tr>
<tr>
<td valign="top">

quovadisrootca2g3 \[jdk\]

</td>
<td valign="top">

CN=QuoVadis Root CA 2 G3, O=QuoVadis Limited, C=BM

</td>
<td valign="top">

09:3C:61:F3:8B:8B:DC:7D:55:DF:75:38:02:05:00:E1:25:F5:C8:36

</td>
</tr>
<tr>
<td valign="top">

quovadisrootca3 \[jdk\]

</td>
<td valign="top">

CN=QuoVadis Root CA 3, O=QuoVadis Limited, C=BM

</td>
<td valign="top">

1F:49:14:F7:D8:74:95:1D:DD:AE:02:C0:BE:FD:3A:2D:82:75:51:85

</td>
</tr>
<tr>
<td valign="top">

quovadisrootca3g3 \[jdk\]

</td>
<td valign="top">

CN=QuoVadis Root CA 3 G3, O=QuoVadis Limited, C=BM

</td>
<td valign="top">

48:12:BD:92:3C:A8:C4:39:06:E7:30:6D:27:96:E6:A4:CF:22:2E:7D

</td>
</tr>
<tr>
<td valign="top">

sapcloudrootca

</td>
<td valign="top">

CN=SAP Cloud Root CA, O=SAP SE, L=Walldorf, C=DE

</td>
<td valign="top">

6D:80:92:77:4A:F2:D5:ED:AE:3A:5C:99:D6:56:93:1C:21:97:A9:50

</td>
</tr>
<tr>
<td valign="top">

sapglobalrootca \[jdk\]

</td>
<td valign="top">

CN=SAP Global Root CA, O=SAP AG, L=Walldorf, C=DE

</td>
<td valign="top">

0A:B6:2A:F4:7F:E5:59:84:7D:79:8A:1F:C4:E1:7F:67:FD:7E:82:4C

</td>
</tr>
<tr>
<td valign="top">

secomscrootca2 \[jdk\]

</td>
<td valign="top">

OU=Security Communication RootCA2, O="SECOM Trust Systems CO.,LTD.", C=JP

</td>
<td valign="top">

5F:3B:8C:F2:F8:10:B3:7D:78:B4:CE:EC:19:19:C3:73:34:B9:C7:74

</td>
</tr>
<tr>
<td valign="top">

sectigocodesignroote46 \[jdk\]

</td>
<td valign="top">

CN=Sectigo Public Code Signing Root E46, O=Sectigo Limited, C=GB

</td>
<td valign="top">

BB:EF:5C:4C:11:48:97:70:F5:86:FB:30:7D:14:32:91:30:7F:11:9A

</td>
</tr>
<tr>
<td valign="top">

sectigocodesignrootr46 \[jdk\]

</td>
<td valign="top">

CN=Sectigo Public Code Signing Root R46, O=Sectigo Limited, C=GB

</td>
<td valign="top">

CC:BB:F9:E1:48:5A:F6:3C:E4:7A:BF:8E:9E:64:8C:25:04:FC:31:9D

</td>
</tr>
<tr>
<td valign="top">

sectigotlsroote46 \[jdk\]

</td>
<td valign="top">

CN=Sectigo Public Server Authentication Root E46, O=Sectigo Limited, C=GB

</td>
<td valign="top">

EC:8A:39:6C:40:F0:2E:BC:42:75:D4:9F:AB:1C:1A:5B:67:BE:D2:9A

</td>
</tr>
<tr>
<td valign="top">

sectigotlsrootr46 \[jdk\]

</td>
<td valign="top">

CN=Sectigo Public Server Authentication Root R46, O=Sectigo Limited, C=GB

</td>
<td valign="top">

AD:98:F9:F3:E4:7D:75:3B:65:D4:82:B3:A4:52:17:BB:6E:F5:E4:38

</td>
</tr>
<tr>
<td valign="top">

securetrustca \[jdk\]

</td>
<td valign="top">

CN=SecureTrust CA, O=SecureTrust Corporation, C=US

</td>
<td valign="top">

87:82:C6:C3:04:35:3B:CF:D2:96:92:D2:59:3E:7D:44:D9:34:FF:11

</td>
</tr>
<tr>
<td valign="top">

sslrooteccca \[jdk\]

</td>
<td valign="top">

CN=SSL.com Root Certification Authority ECC, O=SSL Corporation, L=Houston, ST=Texas, C=US

</td>
<td valign="top">

C3:19:7C:39:24:E6:54:AF:1B:C4:AB:20:95:7A:E2:C3:0E:13:02:6A

</td>
</tr>
<tr>
<td valign="top">

sslrootevrsaca \[jdk\]

</td>
<td valign="top">

CN=SSL.com EV Root Certification Authority RSA R2, O=SSL Corporation, L=Houston, ST=Texas, C=US

</td>
<td valign="top">

74:3A:F0:52:9B:D0:32:A0:F4:4A:83:CD:D4:BA:A9:7B:7C:2E:C4:9A

</td>
</tr>
<tr>
<td valign="top">

sslrootrsaca \[jdk\]

</td>
<td valign="top">

CN=SSL.com Root Certification Authority RSA, O=SSL Corporation, L=Houston, ST=Texas, C=US

</td>
<td valign="top">

B7:AB:33:08:D1:EA:44:77:BA:14:80:12:5A:6F:BD:A9:36:49:0C:BB

</td>
</tr>
<tr>
<td valign="top">

ssltlsrootecc2022 \[jdk\]

</td>
<td valign="top">

CN=SSL.com TLS ECC Root CA 2022, O=SSL Corporation, C=US

</td>
<td valign="top">

9F:5F:D9:1A:54:6D:F5:0C:71:F0:EE:7A:BD:17:49:98:84:73:E2:39

</td>
</tr>
<tr>
<td valign="top">

ssltlsrootrsa2022 \[jdk\]

</td>
<td valign="top">

CN=SSL.com TLS RSA Root CA 2022, O=SSL Corporation, C=US

</td>
<td valign="top">

EC:2C:83:40:72:AF:26:95:10:FF:0E:F2:03:EE:31:70:F6:78:9D:CA

</td>
</tr>
<tr>
<td valign="top">

starfieldclass2ca \[jdk\]

</td>
<td valign="top">

OU=Starfield Class 2 Certification Authority, O="Starfield Technologies, Inc.", C=US

</td>
<td valign="top">

AD:7E:1C:28:B0:64:EF:8F:60:03:40:20:14:C3:D0:E3:37:0E:B5:8A

</td>
</tr>
<tr>
<td valign="top">

starfieldrootg2ca \[jdk\]

</td>
<td valign="top">

CN=Starfield Root Certificate Authority - G2, O="Starfield Technologies, Inc.", L=Scottsdale, ST=Arizona, C=US

</td>
<td valign="top">

B5:1C:06:7C:EE:2B:0C:3D:F8:55:AB:2D:92:F4:FE:39:D4:E7:0F:0E

</td>
</tr>
<tr>
<td valign="top">

starfieldservicesrootg2ca \[jdk\]

</td>
<td valign="top">

CN=Starfield Services Root Certificate Authority - G2, O="Starfield Technologies, Inc.", L=Scottsdale, ST=Arizona, C=US

</td>
<td valign="top">

92:5A:8F:8D:2C:6D:04:E0:66:5F:59:6A:FF:22:D8:63:E8:25:6F:3F

</td>
</tr>
<tr>
<td valign="top">

swisssigngoldg2ca

</td>
<td valign="top">

CN=SwissSign Gold CA - G2, O=SwissSign AG, C=CH

</td>
<td valign="top">

D8:C5:38:8A:B7:30:1B:1B:6E:D4:7A:E6:45:25:3A:6F:9F:1A:27:61

</td>
</tr>
<tr>
<td valign="top">

swisssignplatinumg2ca

</td>
<td valign="top">

CN=SwissSign Platinum CA - G2, O=SwissSign AG, C=CH

</td>
<td valign="top">

56:E0:FA:C0:3B:8F:18:23:55:18:E5:D3:11:CA:E8:C2:43:31:AB:66

</td>
</tr>
<tr>
<td valign="top">

swisssignsilverg2ca

</td>
<td valign="top">

CN=SwissSign Silver CA - G2, O=SwissSign AG, C=CH

</td>
<td valign="top">

9B:AA:E5:9F:56:EE:21:CB:43:5A:BE:25:93:DF:A7:F0:40:D1:1D:CB

</td>
</tr>
<tr>
<td valign="top">

teliarootcav2 \[jdk\]

</td>
<td valign="top">

CN=Telia Root CA v2, O=Telia Finland Oyj, C=FI

</td>
<td valign="top">

B9:99:CD:D1:73:50:8A:C4:47:05:08:9C:8C:88:FB:BE:A0:2B:40:CD

</td>
</tr>
<tr>
<td valign="top">

teliasonerarootcav1 \[jdk\]

</td>
<td valign="top">

CN=TeliaSonera Root CA v1, O=TeliaSonera

</td>
<td valign="top">

43:13:BB:96:F1:D5:86:9B:C1:4E:6A:92:F6:CF:F6:34:69:87:82:37

</td>
</tr>
<tr>
<td valign="top">

thawteclass3

</td>
<td valign="top">

OU=Class 3 Public Primary Certification Authority, O="VeriSign, Inc.", C=US

</td>
<td valign="top">

A1:DB:63:93:91:6F:17:E4:18:55:09:40:04:15:C7:02:40:B0:AE:6B

</td>
</tr>
<tr>
<td valign="top">

thawteprimaryrootcag2 \[jdk\]

</td>
<td valign="top">

CN=thawte Primary Root CA - G2, OU="\(c\) 2007 thawte, Inc. - For authorized use only", O="thawte, Inc.", C=US

</td>
<td valign="top">

AA:DB:BC:22:23:8F:C4:01:A1:27:BB:38:DD:F4:1D:DB:08:9E:F0:12

</td>
</tr>
<tr>
<td valign="top">

thawteprimaryrootcag3

</td>
<td valign="top">

CN=thawte Primary Root CA - G3, OU="\(c\) 2008 thawte, Inc. - For authorized use only", OU=Certification Services Division, O="thawte, Inc.", C=US

</td>
<td valign="top">

F1:8B:53:8D:1B:E9:03:B6:A6:F0:56:43:5B:17:15:89:CA:F3:6B:F2

</td>
</tr>
<tr>
<td valign="top">

thawteprimaryrootcag4

</td>
<td valign="top">

CN=thawte Primary Root CA - G4, OU="\(c\) 2012 thawte, Inc. - For authorized use only", OU=Certification Services Division, O="thawte, Inc.", C=US

</td>
<td valign="top">

FA:7C:FB:B2:47:42:77:63:43:1B:7E:6D:75:81:2A:49:CC:8D:30:E4

</td>
</tr>
<tr>
<td valign="top">

thawteroot

</td>
<td valign="top">

CN=thawte Primary Root CA, OU="\(c\) 2006 thawte, Inc. - For authorized use only", OU=Certification Services Division, O="thawte, Inc.", C=US

</td>
<td valign="top">

91:C6:D6:EE:3E:8A:C8:63:84:E5:48:C2:99:29:5C:75:6C:81:7B:81

</td>
</tr>
<tr>
<td valign="top">

ttelesecglobalrootclass2ca \[jdk\]

</td>
<td valign="top">

CN=T-TeleSec GlobalRoot Class 2, OU=T-Systems Trust Center, O=T-Systems Enterprise Services GmbH, C=DE

</td>
<td valign="top">

59:0D:2D:7D:88:4F:40:2E:61:7E:A5:62:32:17:65:CF:17:D8:94:E9

</td>
</tr>
<tr>
<td valign="top">

ttelesecglobalrootclass3ca \[jdk\]

</td>
<td valign="top">

CN=T-TeleSec GlobalRoot Class 3, OU=T-Systems Trust Center, O=T-Systems Enterprise Services GmbH, C=DE

</td>
<td valign="top">

55:A6:72:3E:CB:F2:EC:CD:C3:23:74:70:19:9D:2A:BE:11:E3:81:D1

</td>
</tr>
<tr>
<td valign="top">

twcaglobalrootca \[jdk\]

</td>
<td valign="top">

CN=TWCA Global Root CA, OU=Root CA, O=TAIWAN-CA, C=TW

</td>
<td valign="top">

9C:BB:48:53:F6:A4:F6:D3:52:A4:E8:32:52:55:60:13:F5:AD:AF:65

</td>
</tr>
<tr>
<td valign="top">

usertrusteccca \[jdk\]

</td>
<td valign="top">

CN=USERTrust ECC Certification Authority, O=The USERTRUST Network, L=Jersey City, ST=New Jersey, C=US

</td>
<td valign="top">

D1:CB:CA:5D:B2:D5:2A:7F:69:3B:67:4D:E5:F0:5A:1D:0C:95:7D:F0

</td>
</tr>
<tr>
<td valign="top">

usertrustrsaca \[jdk\]

</td>
<td valign="top">

CN=USERTrust RSA Certification Authority, O=The USERTRUST Network, L=Jersey City, ST=New Jersey, C=US

</td>
<td valign="top">

2B:8F:1B:57:33:0D:BB:A2:D0:7A:6C:51:F7:0E:E9:0D:DA:B9:AD:8E

</td>
</tr>
<tr>
<td valign="top">

verisignclass1\_g1

</td>
<td valign="top">

OU=Class 1 Public Primary Certification Authority, O="VeriSign, Inc.", C=US

</td>
<td valign="top">

90:AE:A2:69:85:FF:14:80:4C:43:49:52:EC:E9:60:84:77:AF:55:6F

</td>
</tr>
<tr>
<td valign="top">

verisignclass2\_g2

</td>
<td valign="top">

OU=VeriSign Trust Network, OU="\(c\) 1998 VeriSign, Inc. - For authorized use only", OU=Class 2 Public Primary Certification Authority - G2, O="VeriSign, Inc.", C=US

</td>
<td valign="top">

B3:EA:C4:47:76:C9:C8:1C:EA:F2:9D:95:B6:CC:A0:08:1B:67:EC:9D

</td>
</tr>
<tr>
<td valign="top">

verisignclass3\_g1

</td>
<td valign="top">

OU=Class 3 Public Primary Certification Authority, O="VeriSign, Inc.", C=US

</td>
<td valign="top">

74:2C:31:92:E6:07:E4:24:EB:45:49:54:2B:E1:BB:C5:3E:61:74:E2

</td>
</tr>
<tr>
<td valign="top">

verisignclass3\_g2

</td>
<td valign="top">

OU=VeriSign Trust Network, OU="\(c\) 1998 VeriSign, Inc. - For authorized use only", OU=Class 3 Public Primary Certification Authority - G2, O="VeriSign, Inc.", C=US

</td>
<td valign="top">

85:37:1C:A6:E5:50:14:3D:CE:28:03:47:1B:DE:3A:09:E8:F8:77:0F

</td>
</tr>
<tr>
<td valign="top">

verisignclass3\_g3

</td>
<td valign="top">

CN=VeriSign Class 3 Public Primary Certification Authority - G3, OU="\(c\) 1999 VeriSign, Inc. - For authorized use only", OU=VeriSign Trust Network, O="VeriSign, Inc.", C=US

</td>
<td valign="top">

13:2D:0D:45:53:4B:69:97:CD:B2:D5:C3:39:E2:55:76:60:9B:5C:C6

</td>
</tr>
<tr>
<td valign="top">

verisignclass3\_g5

</td>
<td valign="top">

CN=VeriSign Class 3 Public Primary Certification Authority - G5, OU="\(c\) 2006 VeriSign, Inc. - For authorized use only", OU=VeriSign Trust Network, O="VeriSign, Inc.", C=US

</td>
<td valign="top">

4E:B6:D5:78:49:9B:1C:CF:5F:58:1E:AD:56:BE:3D:9B:67:44:A5:E5

</td>
</tr>
<tr>
<td valign="top">

verisignclass3g4ca \[jdk\]

</td>
<td valign="top">

CN=VeriSign Class 3 Public Primary Certification Authority - G4, OU="\(c\) 2007 VeriSign, Inc. - For authorized use only", OU=VeriSign Trust Network, O="VeriSign, Inc.", C=US

</td>
<td valign="top">

22:D5:D8:DF:8F:02:31:D1:8D:F7:9D:B7:CF:8A:2D:64:C9:3F:6C:3A

</td>
</tr>
<tr>
<td valign="top">

verisignroot

</td>
<td valign="top">

CN=VeriSign Universal Root Certification Authority, OU="\(c\) 2008 VeriSign, Inc. - For authorized use only", OU=VeriSign Trust Network, O="VeriSign, Inc.", C=US

</td>
<td valign="top">

36:79:CA:35:66:87:72:30:4D:30:A5:FB:87:3B:0F:A7:7B:B7:0D:54

</td>
</tr>
<tr>
<td valign="top">

workplaceca

</td>
<td valign="top">

CN=mySAP.com Workplace CA \(dsa\), O=mySAP.com Workplace, C=DE

</td>
<td valign="top">

A1:7D:8B:51:8A:8F:BB:DE:A5:00:C8:1E:96:12:26:16:32:4A:34:C0

</td>
</tr>
<tr>
<td valign="top">

xrampglobalca \[jdk\]

</td>
<td valign="top">

CN=XRamp Global Certification Authority, O=XRamp Security Services Inc, OU=www.xrampsecurity.com, C=US

</td>
<td valign="top">

B8:01:86:D1:EB:9C:86:A5:41:04:CF:30:54:F3:4C:52:B7:E5:58:C6

</td>
</tr>
</table>

**Related Information**  


[Server Certificate Authentication](https://help.sap.com/viewer/b865ed651e414196b39f8922db2122c7/Cloud/en-US/3f1247537c1a4f069235ee63633659c5.html "") :arrow_upper_right:

