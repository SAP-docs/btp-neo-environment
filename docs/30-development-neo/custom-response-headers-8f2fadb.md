<!-- loio8f2fadbd0f1c4bea8d84473e8f25e1d5 -->

# Custom Response Headers

You can add custom response headers to your application.

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/docs/btp/sap-business-technology-platform/sap-business-technology-platform?version=Cloud) .**

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

