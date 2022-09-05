<!-- loioa0fa9971cf214775ad27343017f72cbc -->

# Configure Keystore on Local Server



## Context

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**



<a name="loioa0fa9971cf214775ad27343017f72cbc__steps_frg_nq1_xj"/>

## Procedure

1.  To deploy your Web application on the local server, follow the steps for deploying a Web application locally as described in .

2.  To upload the required keystores, copy the prepared `client.jks` and `cacerts.jks` files into `<local server root>\config_master\com.sap.cloud.crypto.keystore` subfolder.

3.  To test the functionality, open the following URL in your Web browser: `http://localhost:<local server HTTP port>/HelloWorld/SSLExampleServlet?host=<remote HTTPS server host name>&port=<remote HTTPS server port number>&path=<remote HTTPS server resource>&client.keystore.password=<client identity keystore password>`.


**Related Information**  




