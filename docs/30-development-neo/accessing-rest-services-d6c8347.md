<!-- loiod6c8347494ce4b48864dfabb42d0d207 -->

# Accessing REST Services

To connect your application to a REST service, configure routing to an HTTP destination in the application descriptor file.

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://launchpad.support.sap.com/#/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**

A route defines which requests to the application are forwarded to the destination. Routes are matched with the path from a request. All requests with paths that start with the path from the route are forwarded to the destination.

If you define multiple routes in the application descriptor file, the route for the first matching path is selected.

The HTTP destination must be created in the subaccount where the application is running. For more information on HTTP destinations, see [Create HTTP Destinations](https://help.sap.com/viewer/b865ed651e414196b39f8922db2122c7/Cloud/en-US/1e110da0ddd8453aaf5aed2485d84f25.html "Create HTTP destinations in the Destinations editor (SAP BTP cockpit).") :arrow_upper_right: and [Assign Destinations for HTML5 Applications](../50-administration-and-ops-neo/assign-destinations-for-html5-applications-bec79c9.md).

```json

...
"routes": [
           {
              "path": "<application path to be forwarded>", 
              "target": {
                   "type": "destination",
                   "name": "<name of the destination>"
              },
             "description": "<description>"
           }
          ]
...

```

> ### Example:  
> With this configuration, all requests with paths starting with `/gateway` are forwarded to the `gateway` destination.
> 
> ```json
> 
> ...
> "routes": [
>            {
>               "path": "/gateway", 
>               "target": {
>                   "type": "destination",
>                   "name": "gateway"
>               },
>              "description": "Gateway System"
>            }
>           ]
> ...
> 
> ```
> 
> The browser sends a request to your HTML5 application to the path `/gateway/resource` \(1\). This request is forwarded by the HTML5 application to the service behind the destination `gateway` \(2\). The path is shortened to `/resource`. The response returned by the service is then routed back through the HTML5 application so that the browser receives the response \(3\).
> 
> ![](images/Example_C_21e0283.png)

> ### Caution:  
> Routes to destinations using the web socket protocol is not supported.



## Destination Properties

In addition to the application-specific setup in the application descriptor, you can configure the behavior of routes at the destination level. For information on how to set destination properties, see [You can enter additional properties (step 9)](https://help.sap.com/viewer/b865ed651e414196b39f8922db2122c7/Cloud/en-US/1e110da0ddd8453aaf5aed2485d84f25.html "Create HTTP destinations in the Destinations editor (SAP BTP cockpit).") :arrow_upper_right:.

You can set the following properties:


<table>
<tr>
<th valign="top">

Property



</th>
<th valign="top">

Type/Unit



</th>
<th valign="top">

Default



</th>
<th valign="top">

Maximum



</th>
<th valign="top">

Recommended Value



</th>
<th valign="top">

Description



</th>
</tr>
<tr>
<td valign="top">

`HTML5.ConnectionTimeoutInSeconds` 



</td>
<td valign="top">

Integer/seconds



</td>
<td valign="top">

10



</td>
<td valign="top">

120



</td>
<td valign="top">

Default



</td>
<td valign="top">

The period of time in which the HTML5 application expects a confirmation when it initiates a new TCP connection.



</td>
</tr>
<tr>
<td valign="top">

`HTML5.SocketReadTimeoutInSeconds` 



</td>
<td valign="top">

Integer/seconds



</td>
<td valign="top">

30



</td>
<td valign="top">

300



</td>
<td valign="top">

Default



</td>
<td valign="top">

The period of time the HTML5 application waits for the REST service to start streaming the response.



</td>
</tr>
<tr>
<td valign="top">

`HTML5.HandleRedirects` 



</td>
<td valign="top">

Boolean



</td>
<td valign="top">

`true` 



</td>
<td valign="top">

\--



</td>
<td valign="top">

`false` 



</td>
<td valign="top">

When set to `true` the HTML5 application internally calls the target URL of a redirecting HTTP response \(HTTP 30X status code\). Then, the browser will only see this second response.



</td>
</tr>
<tr>
<td valign="top">

`sap-client`



</td>
<td valign="top">

String



</td>
<td valign="top">

\--



</td>
<td valign="top">

\--



</td>
<td valign="top">

\--



</td>
<td valign="top">

If `true`, the HTML5 Applications propagates the sap-client and its value as a header in the back-end request.

This is expected by ABAP back-end systems.



</td>
</tr>
</table>



## Timeout Handling

A request to a REST service can time out when the network or backend is overloaded or unreachable. Different timeouts apply for initially establishing the TCP connection \(`HTML5.ConnectionTimeoutInSeconds`\) and reading a response to an HTTP request from the socket \(`HTML5.SocketReadTimeoutInSeconds`\). When a timeout occurs, the HTML5 application returns a gateway timeout response \(***HTTP status code 504***\) to the client.

While some long-running requests may require to increase the socket timeout, we do not recommend that you change the default values. Too high timeouts may impact the overall performance of the application by blocking other requests in the browser or blocking back-end resources.



## Redirect Handling

By default all HTML5 applications follow HTTP redirects of REST services internally. This means whenever your REST service responds with a `301`, `302`, `303`, or `307` HTTP status code, a new request is issued to the redirect target. Only the response to this second request reaches the browser of the end user. To change this behavior, set the `HTML5.HandleRedirects` destination property to `false`. As a consequence, the 30X responses given above are directly sent back without following the redirect.

We recommend that you set this property to `false`. This helps improve the performance of your HTML5 application because the browser stores redirects and thus avoids round trips. If you use relative links, the automatic handling of redirects might break your HTML5 application on the browser side. However, certain service types may not run with a value of `false`.

> ### Example:  
> Prerequisites:
> 
> -   Your application descriptor contains a route that forwards requests starting with the path `/gateway`, to the destination named `gateway` as in the example above.
> 
> -   The service redirects requests from `/resource` to the path `./servicePath/resource`.
> 
> 
> `HTML5.HandleRedirects` is set to `true:`
> 
> When the browser requests the path `/gateway/resource` \(1\), the HTML5 application forwards it to the path `/resource` of the service \(2\). As the service responds with a redirect \(3\), the HTML5 application sends another request to the new path `/servicePath/resource` \(4\). This second response contains the required resource and is forwarded back to the browser \(5\).
> 
> ![](images/Example_A_89ad7ee.png)
> 
> `HTML5.HandleRedirects` is set to `false:`
> 
> For the same request to the path `/gateway/resources`\(1\), the HTML5 application again forwards the request to the path `/resources` of the service \(2\). Now the redirect is directly forwarded back to the browser \(3\). In this case it is the browser that sends another request to the path `/gateway/servicePath/resource` \(4\), which the HTML5 application forwards to the service path `/servicePath/resource` \(5\). The requested resource is then forwarded back to the browser \(6\).
> 
> ![](images/Example_B_817a3fd.png)



## Deprecated Properties

The following destination properties have been deprecated and replaced by new properties. If the new and the old properties are both set, the new property overrules the old one.


<table>
<tr>
<th valign="top">

Old Property



</th>
<th valign="top">

Type/Unit



</th>
<th valign="top">

Values



</th>
<th valign="top">

Replaced by New Property



</th>
</tr>
<tr>
<td valign="top">

`ConnectionTimeout` 



</td>
<td valign="top">

Integer/milliseconds



</td>
<td valign="top">

Default: `10000` \(10 seconds\)

Max. value: `120000` \(120 seconds\)



</td>
<td valign="top">

`HTML5.ConnectionTimeoutInSeconds` 



</td>
</tr>
<tr>
<td valign="top">

`ClientReadTimeout` 



</td>
<td valign="top">

Integer/milliseconds



</td>
<td valign="top">

Default: `30000` \(30 seconds\)

Max. value: `300000` \(300 seconds\)



</td>
<td valign="top">

`HTML5.SocketReadTimeoutInSeconds` 



</td>
</tr>
</table>



## Security Considerations

When accessing a REST service from an HTML5 application, a new connection is initiated by the HTML5 application to the URL that is defined in the HTTP destination.

To prevent that security-relevant headers or cookies are returned from the REST service to the client, only whitelisted headers are returned. While some headers are whitelisted per default, additional headers can be whitelisted in the application descriptor file. For more information about how to whitelist additional headers, see [Approving HTTP Headers](approving-http-headers-df89d9c.md).

Cookies that are retrieved from a REST service response are stored by the HTML5 application in an HTTP session that is bound to the client request. The cookies are not returned to the client. If a subsequent request is initiated to the same REST service, the cookies are added to the request by the application. Only those cookies are added that are valid for the request in the sense of correct domain and expiration date. When the client session is terminated, all associated cookies are removed from the HTML5.

**Related Information**  


[Assign Destinations for HTML5 Applications](../50-administration-and-ops-neo/assign-destinations-for-html5-applications-bec79c9.md "If an HTML5 application requires connectivity to one or more back-end systems, destinations must be created or assigned.")

