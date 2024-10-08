<!-- loioa0fa9971cf214775ad27343017f72cbc -->

# Configure Keystore on Local Server



## Context

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of the following technology portfolios: application development; process automation; integration; data, analytics, and enterprise planning; artificial intelligence. The platform offers users the ability to turn data into business value, compose end-to-end business processes, connect entire IT landscapes, and personalize, build and extend SAP applications. This reduces the overall total cost of ownership maintaining SAP landscapes and third-party software across end-to-end business processes.") :arrow_upper_right:.**



<a name="loioa0fa9971cf214775ad27343017f72cbc__steps_frg_nq1_xj"/>

## Procedure

1.  Deploy your Web application on the local server. See [Deploy Locally with the Console Client](../30-development-neo/deploy-locally-with-the-console-client-937c833.md).

2.  To upload the required keystores, copy the prepared `client.jks` and `cacerts.jks` files into `<local server root>\config_master\com.sap.cloud.crypto.keystore` subfolder.

3.  To test the functionality, open the following URL in your Web browser: `http://localhost:<local server HTTP port>/HelloWorld/SSLExampleServlet?host=<remote HTTPS server host name>&port=<remote HTTPS server port number>&path=<remote HTTPS server resource>&client.keystore.password=<client identity keystore password>`.


