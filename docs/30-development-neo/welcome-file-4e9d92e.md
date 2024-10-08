<!-- loio4e9d92ea8da0400fb40849d4b7bfc560 -->

# Welcome File

You can either display the default Welcome file or specify a different file as Welcome file.

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of the following technology portfolios: application development; process automation; integration; data, analytics, and enterprise planning; artificial intelligence. The platform offers users the ability to turn data into business value, compose end-to-end business processes, connect entire IT landscapes, and personalize, build and extend SAP applications. This reduces the overall total cost of ownership maintaining SAP landscapes and third-party software across end-to-end business processes.") :arrow_upper_right:.**

If the application is accessed only with the domain name in the URL, that is without any additional path information, then the `index.html` file that is located in the root folder of your repository is delivered by default. If you want to deliver a different file, configure this file in the `neo-app.json` file using the `WelcomeFile` parameter. With this additional parameter you specify whether a redirect is sent to the Welcome file or whether the Welcome file is delivered without redirect. If this option is set, then instead of serving the Welcome file directly under `/`, the HTML5 application will send a redirect to the `WelcomeFile` location. With that, relative links in a Welcome file that is not located in the root directory will work.

To configure the Welcome file, add a JSON string with the following format to the `neo-app.json` file:

```

"welcomeFile": "<path to the welcome file>",
"sendWelcomeFileRedirect": true | false
```

> ### Example:  
> An example configuration, which forwards requests without any path information to an `index.html` file in the <code><code>/resources</code></code> folder would look like this:
> 
> ```
> 
> "welcomeFile": "/resources/index.html",
> "sendWelcomeFileRedirect": true
> ```

