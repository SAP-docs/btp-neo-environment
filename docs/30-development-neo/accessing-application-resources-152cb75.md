<!-- loio152cb759db2842db9851d404167d40bc -->

# Accessing Application Resources

To access resources from another HTML5 application or a subscription to an HTML5 application, you can map an application path to the corresponding application or subscription.

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/docs/btp/sap-business-technology-platform/sap-business-technology-platform?version=Cloud) .**

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

