<!-- loiob3ffae761a984f5f8d629d0faaa9d032 -->

# Configure Keystore on Cloud



## Context

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**



<a name="loiob3ffae761a984f5f8d629d0faaa9d032__steps_msd_tq1_xj"/>

## Procedure

1.  To deploy your Web application on the cloud, follow the steps for deploying a Web application to SAP BTP as described in [Deploy on the Cloud with the Console Client](../30-development-neo/deploy-on-the-cloud-with-the-console-client-030863c.md).

2.  To upload the required keystores, execute `upload-keystore` console command with the prepared *.jks* files. For more information, see the *Cloud Configuration* section in [Keys and Certificates](keys-and-certificates-3735938.md).

    > ### Example:  
    > Assuming you have *mySubaccount* subaccount, *myApplication* application, *myUser* user, and the keystore files in folder `C:\Keystores`, you need to execute the following commands in your local `<SDK root>\tools` folder:
    > 
    > ```
    > neo upload-keystore --account mySubaccount --user myUser --location C:\Keystores\client.jks --host hana.ondemand.com
    > neo upload-keystore --account mySubaccount --user myUser --location C:\Keystores\cacerts.jks
    >  --host hana.ondemand.com
    > ```
    > 
    > For more information about the keystore console commands, see [Keystore Console Commands](keystore-console-commands-20b6fbd.md).

3.  To test the functionality, open the application URL shown by SAP BTP cockpit with the following options:<code>&lt;SAP BTP Application URL&gt;/SSLExampleServlet?host=&lt;remote HTTPS server host name&gt;&amp;port=&lt;remote HTTPS server port number&gt;&amp;path=&lt;remote HTTPS server resource&gt;&amp; client.keystore.password=&lt;client identity keystore password&gt;</code>.

    For more information, see [Start and Stop Applications](../50-administration-and-ops-neo/start-and-stop-applications-7612f03.md).


**Related Information**  


[Deploy on the Cloud with the Console Client](../30-development-neo/deploy-on-the-cloud-with-the-console-client-030863c.md "Deploying an application publishes it to SAP BTP. During deploy, you can define various specifics of the deployed application using the deploy command optional parameters.")

[Keys and Certificates](keys-and-certificates-3735938.md)

[Keystore Console Commands](keystore-console-commands-20b6fbd.md)

[Start and Stop Applications](../50-administration-and-ops-neo/start-and-stop-applications-7612f03.md "You can directly start, stop, and undeploy applications, as well as start, stop, and disable individual application processes.")

