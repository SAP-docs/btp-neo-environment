<!-- loio05a07108d34540d39b8a79e2caf96c8c -->

# Implementing Statistics Gathering for Java Applications



## Context

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**

For Java applications running on **Java Web Tomcat 7, Java Web Tomcat 8, and Java EE 7 Web Profile TomEE 7**, you have to update the `SAP-PASSPORT` and forward it as a header. To implement the tracing of outgoing connection calls, you also have to configure your destinations using the destination names from the SAP BTP cockpit, and then call them while forwarding the `SAP-PASSPORT` header.

> ### Note:  
> All following code blocks contain example code, which might only be similar to what you have to implement in your application.



## Procedure

1.  Implement а custom connection in accordance with the following guidelines:

    -   The implemented `ConnectionInfo` interface should return two values - a `byte[]` object id consisting of 16 bytes representing a UUID. For example, `java.util.UUID.randomUUID()` in byte array form with `UUID.mostSigBits` in bytes 0 to 7, and `UUID.leastSigBits` in Bytes 8 to 15.
    -   The `ConnectionCounter int` value is a strictly-increasing value that represents the number of the request performed over the connection with the specific `ConnectionId`.
    -   If you generate a new `ConnectionId` for each request the `ConnectionCounter` must always be set to `1`.
    -   If you reuse a `ConnectionId` for each call, you have to increment the `ConnectionCounter` before each request.

2.  Implement the acquisition of the destination URL in a way similar to the following:

    > ### Sample Code:  
    > ```
    > 
    > Context ctx = new InitialContext();
    > ConnectivityConfiguration configuration = (ConnectivityConfiguration) ctx.lookup("java:comp/env/connectivityConfiguration");
    > 
    > DestinationConfiguration destConfiguration = configuration.getConfiguration(destinationName);
    > String destinationUrl = destConfiguration.getProperty("URL");
    > 
    > ```

    In the example above:

    -   We instruct the look up of the connectivity configuration API
    -   We set the acquisition of the destination configuration for `destinationName`.

3.  Update the `SAP-PASSPORT` for the outgoing connection:

    > ### Sample Code:  
    > ```
    > 
    > SapPassportHeader sapPassportHeader = updateSapPassportHeader(ctx);
    > 
    > private SapPassportHeader updateSapPassportHeader(Context ctx) throws NamingException {
    >      SapPassportHeaderProvider sapPassportHeaderProvider = (SapPassportHeaderProvider) ctx.lookup("java:comp/env/SapPassportHeaderProvider");
    >     
    >         return sapPassportHeaderProvider.getSapPassportHeader(CONNECTION_INFO);
    >     }
    > 
    > ```
    > 
    > ```
    > 
    > ```

    In the example above:

    -   We retrieve `SapPassportHeaderProvider` implementation from the context
    -   We set the current connection info. This is the connection that is established for sending/receiving data to/from a destination.

4.  Set the updated `SAP-PASSPORT` as a HTTP header for the outgoing connection, and then execute the call:

    > ### Sample Code:  
    > ```
    > HttpClient client = HttpClientBuilder.create().build();
    > HttpGet getRequest = new HttpGet(destionationUrl);
    > request.setHeader("SAP-PASSPORT",sapPassportHeader.getValue());
    > 
    > HttpResponse destinationResponse = client.execute(getRequest);
    > 
    > ```


