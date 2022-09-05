<!-- loiod18a9b0739264a4dbd0acbbc0232d614 -->

# Accessing SAPUI5 Resources

To access SAPUI5 resources in your HTML5 application, configure the SAPUI5 service routing in the application descriptor file.

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**



## SAPUI5 Service Routing

To configure the SAPUI5 service routing for your application, map a URL path that your application uses to access SAPUI5 resources to the SAPUI5 service:

```json

...
"routes": [
        {
           "path": "<application path to be mapped>", 
           "target": {
               "type": "service",
               "name": "sapui5",
               "version": "<version>",
               "entryPath": "/resources"
                     },
           "description": "<description>"
           }
        ]
...

```

> ### Example:  
> This configuration example maps all paths starting with `/resources` to the `/resources` path of the SAPUI5 library.
> 
> ```json
> 
> ...
> "routes": [
>         {
>            "path": "/resources", 
>            "target": {
>                "type": "service",
>                "name": "sapui5",
>                "entryPath": "/resources"
>                    },
>            "description": "SAPUI5"
>            }
>         ]
> ...
> 
> ```



For more information about using SAPUI5 for your application, see [SAPUI5: UI Development Toolkit for HTML5](https://sapui5.hana.ondemand.com/sdk/#docs/guide/95d113be50ae40d5b0b562b84d715227.html).



## Determining the Current Active SAPUI5 Version

In the top right corner on ***https://sapui5-sapui5.dispatcher.hana.ondemand.com/***, choose *VERSION INFO* to display the latest versions of the individual libs.



## Referencing a Specific SAPUI5 Version in Your HTML5 App

> ### Example:  
> This configuration example shows how to reference the SAPUI5 version 1.26.6 using the `neo-app.json` file.
> 
> ```json
> 
> ...
> "routes": [
>     {
>         "path": "/resources",
>         "target": {
>           "type": "service",
>           "name": "sapui5",
>           "version": "1.26.6",
>           "entryPath": "/resources"
>         },
>         "description": "SAPUI5"
>     }
> }
> ...
> 
> ```

To display the available SAPUI5 versions, open ***https://sapui5-sapui5.dispatcher.hana.ondemand.com/neo-app.json*** file.

**Related Information**  


[VERSION INFO in SAPUI5 Release Notes](https://sapui5-sapui5.dispatcher.hana.ondemand.com/)

[To view the SAPUI5 versions in the HTML5 App, open the `neo-app.json` file](https://sapui5-sapui5.dispatcher.hana.ondemand.com/neo-app.json)

[Release Notes for SAP BTP](http://scn.sap.com/docs/DOC-28833)

