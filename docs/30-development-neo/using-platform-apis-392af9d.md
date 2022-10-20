<!-- loio392af9d162694d6595499f1549978aa6 -->

# Using Platform APIs

Platform APIs are protected with *OAuth 2.0 client credentials*. Create an OAuth client and obtain an access token to call the platform API methods.



## Context

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**

For description of OAuth 2.0 client credentials grant, see the [OAuth 2.0 client credentials grant specification](https://tools.ietf.org/html/rfc6749#section-4.4).

For some of the platform APIs, the JWT type of access tokens is used. See [Best Practices for Resilient OAuth 2.0 Communication](../60-security-neo/best-practices-for-resilient-oauth-2-0-communication-11fe332.md).

For detailed description of the available methods, see the respective API documentation.

> ### Tip:  
> Do not get a new OAuth access token for each and every platform API call. Re-use the same existing access token throughout its validity period instead, until you get a response indicating the access token needs to be re-issued.

 <a name="task_hrx_5pp_ns"/>

<!-- task\_hrx\_5pp\_ns -->

## 1. Create an OAuth Client



## Context

The OAuth client is identified by a *client ID* and protected with a *client secret*. In a later step, those are used to obtain the OAuth API access token from the *OAuth access token endpoint*.



<a name="task_hrx_5pp_ns__steps_it4_ypp_ns"/>

## Procedure

1.  In your Web browser, open the SAP BTP cockpit.

2.  Go to the *Security* \> *OAuth* section.

3.  Enter the *Platform API* tab.

4.  Choose *Create API Client*.

5.  Choose the required API option and required combination of scopes. We recommend that you enter an OAuth client description as well.

6.  Save the client.

7.  Copy the generated client ID and client secret, and save them locally.

    > ### Caution:  
    > Make sure you save the generated client credentials. Once you close the confirmation dialog, you cannot retrieve the generated client credentials again.


 <a name="task_f12_jqp_ns"/>

<!-- task\_f12\_jqp\_ns -->

## 2. Get an OAuth Access Token



## Context

*OAuth access token endpoint* and use the *client ID* and *client secret* as user and password for HTTP Basic Authentication. You will receive the access token as a response.

By default, the access token received in this way is valid 1500 seconds \(25 minutes\). You cannot configure its validity length.

If you want to revoke the access token before its validity ends, delete the respective OAuth client. The access token remains valid up to 2 minutes after the client is deleted.



<a name="task_f12_jqp_ns__steps_b2m_kqp_ns"/>

## Procedure

1.  Send a POST request to the OAuth access token endpoint. The URL is landscape specific, and looks like this:

    *https://api.<cloud platform host\>/oauth2/apitoken/v1?grant\_type=client\_credentials*

    For the cloud platform host, see [Regions and Hosts Available for the Neo Environment](../10-concepts-neo/regions-and-hosts-available-for-the-neo-environment-d722f7c.md).

    The parameter *grant\_type=client\_credentials* notifies the endpoint that the Client Credentials flow is used.

2.  Get and save the access token from the received response from the endpoint.

    The response is a JSON object, whose *access\_token*parameter is the access token. It is valid for the specified time \(in seconds\) in the *expires\_in* parameter. \(default value: 1500 seconds\).




Retrieving an access token on the Europe \(Rot\) region will look like this:

```
POST https://api.hana.ondemand.com/oauth2/apitoken/v1?grant_type=client_credentials 

Headers: 
Authorization: Basic eW91ckNsaWVudElEOnlvdXJDbGllbnRTZWNyZXQ

```

The `eW91ckNsaWVudElEOnlvdXJDbGllbnRTZWNyZXQ` String in the above request is the Base-64 encoded `<clientID>:<ClientSecret>`.

You receive a response like this:

```
{
    "access_token": "51ddd94b15ec85b4d54315b5546abf93",
    "token_type": "Bearer",
    "expires_in": 1500,
    "scope": "hcp.manageAuthorizationSettings hcp.readAuthorizationSettings"
}

```

Alternatively, you can do this using an HTTP destination.

1.  At the required \(application, subaccount or global account\) level, create an HTTP destination with the following information \(the name can be different\):

    -   Name=<yourdestination name\>

    -   URL=https://api.<cloud platform host\>/oauth2/apitoken/v1?grant\_type=client\_credentials

    -   ProxyType=Internet

    -   Type=HTTP

    -   CloudConnectorVersion=2

    -   Authentication=BasicAuthentication

    -   User=<clientID\>

    -   Password=<clientSecret\>


    See [Create HTTP Destinations](https://help.sap.com/viewer/b865ed651e414196b39f8922db2122c7/Cloud/en-US/1e110da0ddd8453aaf5aed2485d84f25.html "Create HTTP destinations in the Destinations editor (SAP BTP cockpit).") :arrow_upper_right:.

2.  In your application, obtain an `HttpURLConnection` object that uses the destination.

    See [ConnectivityConfiguration API](https://help.sap.com/viewer/b865ed651e414196b39f8922db2122c7/Cloud/en-US/4da3b13c88ce4220bbd56a4361799668.html "All connectivity API packages are visible by default from all Web applications. Applications can consume the connectivity configuration via a JNDI lookup.") :arrow_upper_right:.

3.  With the object retrieved from the previous step, execute a POST call.

    ```
    urlConnection.setRequestMethod("POST");
    urlConnection.setRequestProperty("Authorization", "Basic <Base64 encoded representation of {clientId}:{clientSecret}>");
    urlConnection.connect();
    
    ```


 <a name="task_ovh_nrp_ns"/>

<!-- task\_ovh\_nrp\_ns -->

## 3. Call API Methods



<a name="task_ovh_nrp_ns__steps_yp5_srp_ns"/>

## Procedure

In the requests to the required platform API, include the access token as a header with name *Authorization* and value *Bearer <token value\>*.



We will call the Authorization Management API.

```
GET https://api.hana.ondemand.com/authorization/v1/accounts/mysampleaccount/users/roles/?userId=mysampleuser
Headers: 
Authorization: Bearer 51ddd94b15ec85b4d54315b5546abf93

```

**Related Information**  


[Keystore API](../60-security-neo/keystore-api-08ff3f8.md "The Кeystore API provides a repository for cryptographic keys and certificates to the applications in the Neo environment. It allows you to manage keystores at subaccount, application or subscription level.")

[Authorization Management API](../60-security-neo/authorization-management-api-dbea343.md "The Authorization Management API allows you to manage user roles and groups, and their assignments in your applications.")

[Audit Log Retrieval API Usage for the Neo Environment](../60-security-neo/audit-log-retrieval-api-usage-for-the-neo-environment-e4d818d.md "The audit log retrieval API allows you to retrieve the audit logs for your SAP BTP Neo environment account. It follows the OData 4.0 standard, providing the audit log results as OData with collection of JSON entities.")

[Audit Log Retention API Usage for the Neo Environment](../60-security-neo/audit-log-retention-api-usage-for-the-neo-environment-fb195bf.md "The audit log retention API allows you to view your currently active retention period for all the audit log data that is stored for your account.")

[Platform Authorization Management API](../60-security-neo/platform-authorization-management-api-eb01a9f.md "The Platform Authorization Management API allows you to manage the users authorized to access your subaccount in the Neo environment.")

