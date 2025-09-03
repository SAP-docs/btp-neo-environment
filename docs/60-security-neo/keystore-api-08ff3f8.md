<!-- loio08ff3f81b5944351ae540c71ac478d04 -->

# Keystore API

The Кeystore API provides a repository for cryptographic keys and certificates to the applications in the Neo environment. It allows you to manage keystores at subaccount, application or subscription level.

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/docs/btp/sap-business-technology-platform/sap-business-technology-platform?version=Cloud) .**

The Keystore API is protected with *OAuth 2.0 client credentials*. Create an OAuth client and obtain an access token to call the API methods. See [Using Platform APIs](../30-development-neo/using-platform-apis-392af9d.md).



<a name="loio08ff3f81b5944351ae540c71ac478d04__section_kkj_jmr_zbb"/>

## Using an HTTP Destination for Connecting to the Keystore

Using an HTTP destination is a convenient way to establish connection to the keystore. Once created, you can re-use the destination for different API calls. To create the required destination, do the following steps:

1.  At the required level, create an HTTP destination with the following information:

    -   Name=<your destination name\>

    -   URL=https://api.<cloud platform host\>/keystore/v1

    -   ProxyType=Internet

    -   Type=HTTP

    -   CloudConnectorVersion=2

    -   Authentication=NoAuthentication


    See [Create HTTP Destinations](https://help.sap.com/viewer/b865ed651e414196b39f8922db2122c7/Cloud/en-US/1e110da0ddd8453aaf5aed2485d84f25.html "Create HTTP destinations in the Destinations editor (SAP BTP cockpit).") :arrow_upper_right:.

2.  In your application, obtain an `HttpURLConnection` object that uses the destination.

    See [ConnectivityConfiguration API](https://help.sap.com/viewer/b865ed651e414196b39f8922db2122c7/Cloud/en-US/4da3b13c88ce4220bbd56a4361799668.html "All connectivity API packages are visible by default from all Web applications. Applications can consume the connectivity configuration via a JNDI lookup.") :arrow_upper_right:.




<a name="loio08ff3f81b5944351ae540c71ac478d04__section_eht_kmr_zbb"/>

## Example: Downloading a Keystore at Account Level

With the `HttpURLConnection` object retrieved, execute a GET call.

```
//value is the URL property of the destination
URL url = new URL(value + "accounts/{account}/{keystoreName}");  
HttpURLConnection urlConnection = (HttpURLConnection)url.openConnection();
urlConnection.setRequestMethod("GET");
urlConnection.setRequestProperty("Authorization", "Bearer <OAuth token ID from previous step>");
urlConnection.connect();

```

If everything is OK, you should get a response like that:

`200 - <content of the keystore>`

> ### Tip:  
> We recommend using `If-None-Match` header for subsequent calls to the keystore to check if the keystore contents have been modified since your last GET call.
> 
> From the response, copy the `Etag` header value and repeat the request with the added header below:
> 
> `If-None-Match : <Etag_header value from the first response>`
> 
> You can do it using the same code excerpt as above with added the following line before the last line:
> 
> ```
> urlConnection.setRequestProperty("If-None-Match", "<value of Etag header>");
> ```
> 
> Expected responses:
> 
> -   If no content has been modified:
> 
>     `304 - Not Modified`
> 
> -   If the content was successfully modified:
> 
>     `200 - <the modified keystore content>`



<a name="loio08ff3f81b5944351ae540c71ac478d04__section_n1j_jnr_zbb"/>

## Example: Uploading a Keystore at Account Level

With the `HttpURLConnection` object retrieved, execute a PUT call.

```
URL url = new URL(value + "accounts/{account}/{keystoreName}");
HttpURLConnection urlConnection = (HttpURLConnection)url.openConnection();
urlConnection.setRequestMethod("PUT");
urlConnection.setRequestProperty("Authorization",  "Bearer < token ID from previous step>");
urlConnection.setRequestProperty("Content-Type",  "<selected_content_type>");
urlConnection.setDoOutput(true);
urlConnection. getOutputStream().write(keyStore.getBytes());  // writes the keystore bytes in the URL connection
urlConnection.connect();
				
```

If you want to overwrite the keystore, set to true the query parameter `overwrite`. For example:

```
URL url = new URL(value + "accounts/{account}/{keystoreName}?overwrite=true");
```

The `Content-Type` header can be:

-   `application/x-pkcs12` - for PKCS12 formatted keystores

    `application/x-pem-file` - for PEM formatted keystores

    `application/octet-stream` – for any other type.


Expected response:

-   If the keystore upload was successful:

    `200 - OK`

-   If the keystore already exists:

    `409 - conflict`




<a name="loio08ff3f81b5944351ae540c71ac478d04__section_gf2_n1v_x1c"/>

## Rate Limits

Rate limits are used to limit the number of requests against this REST API. Requests may be throttled \(delayed\), and if there is a very high load also denied.

The following limits are available:

**Limit**

If this limit is **fully exceeded**, the service responds with '429 - Too many requests'.

The **rate limit** defined for the API is **100 requests** per minute per subaccount.

> ### Note:  
> Depending on the service health, this limit may be ignored or further reduced to keep the service operational.

**Related Information**  


[Using Platform APIs](../30-development-neo/using-platform-apis-392af9d.md "Platform APIs are protected with OAuth 2.0 client credentials. Create an OAuth client and obtain an access token to call the platform API methods.")

[Keystore API](https://api.hana.ondemand.com/keystore/v1/documentation)

