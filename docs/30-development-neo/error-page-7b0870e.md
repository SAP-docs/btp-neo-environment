<!-- loio7b0870e9bfdf41a793b35984c12f1b25 -->

# Error Page

You can configure an error page that is displayed in case of an internal server error.

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/docs/btp/sap-business-technology-platform/sap-business-technology-platform?version=Cloud) .**

You can configure an error page that is displayed instead of a standard error message for internal server errors \(response error code 500\).

You specify the error page in the application descriptor file \(`neo-app.json`\) using the `errorPage` attribute. When an internal sever error \(error code 500\) occurs, the response is redirected to this page. The path to the error page has to be relative. That means the path doesn’t have a leading slash. You can place the file of the error page in the root directory of the HTML5 application next to the neo-app.json file or in a subfolder within the directory. If you don’t configure an error page, the standard error message will be displayed.

> ### Tip:  
> When writing a text for this error page remember that an internal server error with response error code 500 can occur for different reasons. You can use the error page to provide users with suggestions on what they can do in specific error scenarios. However, this error page will always be shown when the error response code 500 happens, regardless of the cause of the error. It will also be shown in error scenarios for which you can’t provide specific hints.
> 
> For example, you could display a very generic tip such as *Reload the application. If this doesn’t help, please try again later.*.
> 
> Or you could give a hints for a specific scenario, for example: *This application is optimized for the < name of the browser\> browser. Try opening the app in < name of the browser\>. If this doesn’t help, please try again later.*

> ### Note:  
> If the response error code 500 comes from the destination, the custom error page will not be displayed. In this case, the destination owner has to provide the relevant details of the error.

To configure the error page, add a JSON string with the following format to the application descriptor file \(`neo-app.json`\):

```

"errorPage": "<path to the error page>"
```

> ### Example:  
> An example configuration that redirects the response to `<application directory>/folder1/myErrorPage.html` can look like this:
> 
> ```
> 
> "errorPage": "folder1/myErrorPage.html"
> ```

