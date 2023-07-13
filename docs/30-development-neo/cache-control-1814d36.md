<!-- loio1814d3603acd4ab18102a3b4984687b4 -->

# Cache Control

To improve the performance of your application you can control the `Cache-Control` headers, which are returned together with the static resource of your application.

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**

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

