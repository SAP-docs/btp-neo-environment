<!-- loio1de599bf722446849d2b2e10132df42a -->

# Accessing the User API

The User API service provides an API to query the details of the user that is currently logged on to the HTML5 application.

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**



If you use a corporate identity provider \(IdP\), some features of the API do not work as described here. The corporate IdP requires you to configure a mapping from your IdP’s assertion attributes to the principal attributes usable in SAP BTP. See [Configure User Attribute Mappings](../60-security-neo/application-identity-provider-dc61853.md#loiob6cfc4bb4bff4ace90afc71b0962fcb5__configure_attributes).



To use the User API in your HTML5 application, add a route to your `neo-app.json` application descriptor file as follows:

```json

...
"routes": [
   {
     "path": "<application path to be forwarded>", 
     "target": {
       "type": "service",
       "name": "userapi"
     }
  }
]
...
```

The route defines which requests to the application are forwarded to the API. The route is matched with the path from a request. All `GET` requests with paths that start with the `path` from the route are forwarded to the API.

> ### Example:  
> With the following configuration, all `GET` requests with paths starting with `/services/userapi` are forwarded to the user API.
> 
> ```json
> 
> ...
> "routes": [
>    {
>      "path": "/services/userapi", 
>      "target": {
>        "type": "service",
>        "name": "userapi"
>      }
>   }
> ]
> ...
> ```

The User API supports the following endpoints:

-   /`currentUser`

-   /`attributes`


The User API requires authentication. The user is logged on automatically even if the `authentication` property is set to ***none*** in the `neo-app.json` file.



## Current User Details

Calling the `/currentUser` endpoint returns a JSON object that provides the user ID and additional information of the logged-on user. The table below describes the properties contained in the JSON object and specifies the principal attribute used to compute this information.


<table>
<tr>
<th valign="top">

Property Name



</th>
<th valign="top">

Description



</th>
<th valign="top">

Principal Attribute



</th>
</tr>
<tr>
<td valign="top">

 `name` 



</td>
<td valign="top">

The user ID that is used for logging on.



</td>
<td valign="top">

n.a.



</td>
</tr>
<tr>
<td valign="top">

 `firstName` 



</td>
<td valign="top">

The first name of the user.



</td>
<td valign="top">

firstname



</td>
</tr>
<tr>
<td valign="top">

 `lastName` 



</td>
<td valign="top">

The last name of the user.



</td>
<td valign="top">

lastname



</td>
</tr>
<tr>
<td valign="top">

 `email` 



</td>
<td valign="top">

The email address of the user.



</td>
<td valign="top">

email



</td>
</tr>
<tr>
<td valign="top">

 `displayName` 



</td>
<td valign="top">

Concatenated user name derived from the first name, last name, and user ID. If either the first or the last name does not exist, the `displayName` consists solely of the user ID.



</td>
<td valign="top">

firstname + lastname + name



</td>
</tr>
</table>

The `/currentUser` endpoint maps a default set of attributes. To retrieve all attributes, use the `/attributes` endpoint as described in *User Attributes*.

> ### Example:  
> A sample URL for the route defined above would look like this: `/services/userapi/currentUser`.
> 
> An example response could return the following user data:
> 
> ```json
> {
>   "name": "p12345678",
>   "firstName": "John",
>   "lastName": "Doe",
>   "email": "john@doeenterprise.com",
>   "displayName": "John Doe (p12345678)"
> }
> 
> ```

> ### Caution:  
> Calls to this service must not be cached by the Content Delivery Network\(CDN\). Caching causes the wrong results to be returned.



## User Attributes

The `/attributes` endpoint returns the principal attributes of the current user as a JSON object. These attributes are received as SAML assertion attributes when the user logs on. To make them visible, define a mapping within the trust settings of the SAP BTP cockpit, see [Configure User Attribute Mappings](../60-security-neo/application-identity-provider-dc61853.md#loiob6cfc4bb4bff4ace90afc71b0962fcb5__configure_attributes).

> ### Example:  
> A sample URL for the route defined above would look like this: `/services/userapi/attributes`.
> 
> If the principal attributes `firstname`, `lastname`, `companyname`, and `organization` are present, an example response may return the following user data:
> 
> ```json
> {
>   "firstname": "John",
>   "lastname": "Doe",
>   "companyname": "Doe Enterprise",
>   "organization": "Customer sales and marketing"
> }
> 
> ```



## Query Parameters

For some endpoints, you can use query parameters to influence the output behavior of the endpoint. The following table shows which parameters exist for the `/attributes` endpoint and how they impact the outputs.


<table>
<tr>
<th valign="top">

URL Parameter



</th>
<th valign="top">

Type/Unit



</th>
<th valign="top">

Default



</th>
<th valign="top">

Recommended Value



</th>
<th valign="top">

Behavior



</th>
</tr>
<tr>
<td valign="top">

 `multiValuesAsArrays` 



</td>
<td valign="top">

Boolean



</td>
<td valign="top">

 ***false*** 



</td>
<td valign="top">

***true***



</td>
<td valign="top">

If set to ***true***, multivalued attributes are formatted as JSON arrays. If set to ***false***, only the first value of the entire value range of the specific attribute is returned and formatted as a simple string.

> ### Note:  
> If set to ***true*** for an attribute that is not multivalued, then the value of the attribute is formatted as a simple string and not a JSON array.



</td>
</tr>
</table>

