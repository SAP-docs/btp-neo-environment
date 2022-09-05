<!-- loiodf89d9cd06a84905a3a4747f102c5b2c -->

# Approving HTTP Headers

For security reasons not all HTTP headers are forwarded from the application to a backend or from the backend to the application.

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**



## Header Approved by Default

The following HTTP headers are forwarded automatically without any additional configuration because they are part of the HTTP standard:

-   `Accept`
-   `Accept-Charset`
-   `Accept-Language`
-   `Accept-Range`
-   `Age`
-   `Allow`
-   `Authorization`
-   `Cache-Control`
-   `Content-Language`
-   `Content-Location`
-   `Content-Range`
-   `Content-Type`
-   `Date`
-   `ETag`
-   `Expires`
-   `From`
-   `If-Match`
-   `If-Modified-Since`
-   `If-None-Match`
-   `If-Range`
-   `If-Unmodified-Since`
-   `Last-Modified`
-   `Link`
-   `Location`
-   `Max-Forwards`
-   `Pragma`
-   `Range`
-   `Referer`
-   `Retry-After`
-   `User-Agent`
-   `Vary`
-   `Via`
-   `Warning`
-   `WWW-Authenticate`



Additionally the following HTTP headers are transferred automatically because they are frequently used by Web applications and \(SAP\) servers:

-   `Content-Disposition`
-   `Content-MD5`
-   `DataServiceVersion`
-   `DNT`
-   `MaxDataServiceVersion`
-   `Origin`
-   `RequestID`
-   `Sap-ContextId`
-   `Sap-Message`
-   `Sap-Messages`
-   `Sap-Metadata-Last-Modified`
-   `SAP-PASSPORT`
-   `Slug`: For more information, see [Atom Publishing Protocol](https://tools.ietf.org/html/rfc5023#section-9.7).
-   `X-CorrelationID`
-   `X-CSRF-TOKEN`
-   `X-dynaTrace`
-   `X-Forwarded-For`
-   `X-HTTP-Method`
-   `X-Requested-With`



## Approving Custom Headers

If you need additional HTTP headers to be forwarded to or from a backend request or backend response, add the header names in the following format to the `neo-app.json` file:

```json
"headerWhiteList": [<header1> (, <header2>, ...)]
```

> ### Example:  
> An example configuration that forwards the additional headers `X-Custom1` and `X-Custom2` looks like this:
> 
> ```json
> "headerWhiteList": ["X-Custom1 "," X-Custom2"]
> ```



## Excluded Headers

The following headers are never forwarded:

-   `Cookie`
-   `Cookie2`
-   `Content-Length`
-   `Accept-Encoding`

Cookies are used for user session identification and therefore should not be shared. The system stores cookies sent by a backend in the session and removes them from the response before forwarding to the user. With the next request to the backend the stored cookies are added again.

The `Content-Length` header cannot be approved as the value is recalculated on demand matching the content of the given request or response.

The HTML5 application internally manages the `Accept-Encoding` header.

