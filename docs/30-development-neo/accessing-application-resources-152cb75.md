<!-- loio152cb759db2842db9851d404167d40bc -->

# Accessing Application Resources

To access resources from another HTML5 application or a subscription to an HTML5 application, you can map an application path to the corresponding application or subscription.

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of the following technology portfolios: application development; process automation; integration; data, analytics, and enterprise planning; artificial intelligence. The platform offers users the ability to turn data into business value, compose end-to-end business processes, connect entire IT landscapes, and personalize, build and extend SAP applications. This reduces the overall total cost of ownership maintaining SAP landscapes and third-party software across end-to-end business processes.") :arrow_upper_right:.**

If the given path matches a request path, the resource is loaded from the mapped application or subscription. This feature may be used to separate re-usable resources in a dedicated application.

> ### Note:  
> If multiple routes are defined in the application descriptor, the route for the first matching path in the application descriptor is selected.

```json

...
"routes": [
        {
           "path": "<application path to be mapped>",
           "target": {
               "type": "application",
               "name": "<name of the application or subscription>"
               "version": "<version to be referenced. Default is active version>",
               },
           "description": "<description>"
             }
          ]
...

```

> ### Example:  
> This configuration example maps all paths starting with `/icons` to the active version of the application named `iconlibrary`.
> 
> ```json
> 
> ...
> "routes": [
>              {
>            "path": "/icons", 
>            "target": {
>                "type": "application",
>                "name": "iconlibrary"
>                },
>            "description": "Icon Library"
>              }
>           ]
> ...
> 
> ```

**Related Information**  


[Application Descriptor File](application-descriptor-file-aed1ffa.md "Using the application descriptor file you can configure the behavior of your HTML5 application.")

