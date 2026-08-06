<!-- loio1814d3603acd4ab18102a3b4984687b4 -->

# Cache Control

To improve the performance of your application you can control the `Cache-Control` headers, which are returned together with the static resource of your application.

> ### Caution:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/docs/btp/sap-business-technology-platform/sap-business-technology-platform?version=Cloud) .**

> ### Tip:  
> Additional IP outbound addresses will soon be used in all regions in the Neo environment. For more information, see [Additional IP Addresses Added to SAP BTP, Neo Runtime Regions](https://help.sap.com/whats-new/cf0cb2cb149647329b5d02aa96303f56?version=Cloud&Component=Region&Valid_as_Of=2026-11-02:2026-11-02). To subscribe to such notifications, see SAP Note [3513325](https://me.sap.com/notes/3513325).

You can configure caching for the complete application, for dedicated paths, or resources of the application. If the path you specify ends with a slash character \(/\) all resources in the given directory and its sub-directories are matched. You can also specify the path using wildcards, for example, the path `**.html` matches all resources ending with `.html`. Only the first caching directive that matches an incoming request is applied. The path `**.css` hides, for example, other paths such as `/resources/custom.css`.

With the `directive` property, you specify whether public proxies can cache the resources. The possible values for the `directive` property are:

-   `public`

    The resource can be cached regardless of your response headers.

-   `private`

    Your resource is stored by end-user caches, for example, the browser's internal cache only.

-   `none`

    This is the default value that does not send an additional directive


To configure caching, add a JSON string in the following format to the `neo-app.json` file:

```json

...
"cacheControl": [
                  {
                    "path": "<optional path of resources to be cached>",
                    "directive": "none | public | private",
                    "maxAge": <lifetime in seconds>
                  }
                ]
...

```

> ### Example:  
> An example configuration that caches all static resources for 24 hours looks like this:
> 
> ```json
> 
> ...
> "cacheControl": [
>                   {
>                     "maxAge": 86400
>                   }
>                 ]
> ...
> ```

