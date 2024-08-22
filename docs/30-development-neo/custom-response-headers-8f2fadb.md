<!-- loio8f2fadbd0f1c4bea8d84473e8f25e1d5 -->

# Custom Response Headers

You can add custom response headers to your application.

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of the following technology portfolios: application development; process automation; integration; data, analytics, and enterprise planning; artificial intelligence. The platform offers users the ability to turn data into business value, compose end-to-end business processes, connect entire IT landscapes, and personalize, build and extend SAP applications. This reduces the overall total cost of ownership maintaining SAP landscapes and third-party software across end-to-end business processes.") :arrow_upper_right:.**

Custom response headers are added to an application, for example, to comply with security standards.

To set default HTTP response headers retrieved by the request, add the header names and values in the following format to the `neo-app.json` file:

> ### Note:  
> If back end requests are retrieved with the same response headers as in the neo-app.json file, then those values are not overridden.

> ### Note:  
> Custom Response headers are not supported when running your application from SAP Web IDE.

```json

"responseHeaders": [
        {
            "headers": [
            	{
			"name": "header name",
	                "value": "header value"
            	}
            ]
        }
    ],
```

> ### Sample Code:  
> ```
> 
> "responseHeaders": [
>         {
>             "headers": [
>             	{
> 			"name": "Content-Security-Policy",
> 	                "value": "default-src 'self'"
>             	}
>             ]
>         }
>     ],
> ```

> ### Note:  
> The Content Security Policy \(CSP\) is an added layer of security that helps to detect and mitigate certain types of attacks, including Cross Site Scripting \(XSS\) and data injection attacks. These attacks are used for everything from data theft to site defacement or distribution of malware.

