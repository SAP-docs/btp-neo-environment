<!-- loio390594a7ee9e4a51b5f5eb6af61d8bdc -->

# Enable and Configure Gzip Response Compression

Usage of gzip response compression can optimize the response time and improve interaction with an application as it reduces the traffic between the Web server and browsers. Enabling compression configures the server to return zipped content for the specified MIME type and size of the response.



## Prerequisites

You have downloaded and configured SAP BTP console client.

For more information, see [Set Up the Console Client](../30-development-neo/set-up-the-console-client-7613dee.md).



## Context

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://launchpad.support.sap.com/#/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**

You can enable and configure gzip using some optional parameters of the deploy command in the console client. When deploying the application, specify the following parameters:



## Procedure

1.  To enable gzip compression, specify *\--compression on*.

2.  To configure response MIME types that will be compressed, use *\--compressible-mime-type*.

3.  To specify the size of responses which will be compressed, use *\--compression-min-size*.

    If you enable compression but do not specify values for *\--compressible-mime-type* or *\--compression-min-size*, then the defaults are used: *text/html, text/xml, text/plain* and *2048* bytes, respectively.

    If you specify values for *\--compressible-mime-type* or *\--compression-min-size* but do not enable compression, then the operation passes, compression is not enabled and you get a warning message.

    If you want to enable compression for all responses independently from MIME type and size, use only *\--compression force*.




## Example

```
neo deploy myapp.properties --compression on --compressible-mime-type application/javascript,application/json
 --compression-min-size 1024
```



## Next Steps

Once enabled, you can disable the compression by redeploying the application without the compression options or with parameter *\--compression off*.

**Related Information**  


[Console Client for the Neo Environment](console-client-for-the-neo-environment-7613230.md)

[deploy](deploy-937db4f.md "Deploying an application publishes it to SAP BTP. Use the optional parameters to make some specific configurations of the deployed application.")

