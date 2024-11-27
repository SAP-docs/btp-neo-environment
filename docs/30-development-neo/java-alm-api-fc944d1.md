<!-- loiofc944d19af614052898b145deb2bee59 -->

# Java ALM API

The Java ALM service REST API provides functionality for managing the lifecycle of Java applications.



> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of the following technology portfolios: application development; process automation; integration; data, analytics, and enterprise planning; artificial intelligence. The platform offers users the ability to turn data into business value, compose end-to-end business processes, connect entire IT landscapes, and personalize, build and extend SAP applications. This reduces the overall total cost of ownership maintaining SAP landscapes and third-party software across end-to-end business processes.") :arrow_upper_right:.**

> ### Note:  
> The Java ALM API applies rate limiting for deployment and start operations when you send *POST* Applications, *PUT* Application, and *PUT* Application State requests. This means that you receive the *HTTP 429 Too Many Requests* response when you attempt to send more than 10 simultaneous requests for a given subaccount. See [Java ALM API](https://api.sap.com/api/SAP_HCP_Lifecycle_Management/resource/).



<a name="loiofc944d19af614052898b145deb2bee59__section_xbn_t2n_bmb"/>

## Overview

![](images/Java_Application_Lifecycle_Management_Graphic_4a22e9b.png)



This tutorial provides information about the most common use cases for Java applications and the operations that are included in each one:

-   [Authentication and Authorization](java-alm-api-fc944d1.md#loio654812131e9e440d85e97648061212bb)
-   [Deploy an Application](java-alm-api-fc944d1.md#loio83729f7df7074de3a795d61ae8844c0e)
-   [Deploy an Application with a Copy Operation](java-alm-api-fc944d1.md#loiocf6608a1b8ed4e30a32393ed39d1e4a3)
-   [Verify Application Binaries](java-alm-api-fc944d1.md#loio7fc54044e29f4fb3aa39a171032b6b17)
-   [Start an Application](java-alm-api-fc944d1.md#loio2d3be560df574092909ed8171ec197ec)
-   [Stop an Application](java-alm-api-fc944d1.md#loio38829d2c139c47b3a1c1d64e6ce6d4f8)

<a name="loio654812131e9e440d85e97648061212bb"/>

<!-- loio654812131e9e440d85e97648061212bb -->

## Authentication and Authorization

You can use one of the following:

-   Basic authentication

    You provide username and password.

-   OAuth authentication and authorization

    The REST API is protected with OAuth 2.0 client credentials.

    > ### Note:  
    > For OAuth authentication and authorization, the Java ALM API supports JWT access tokens. See [Best Practices for Resilient OAuth 2.0 Communication](https://help.sap.com/docs/btp/sap-btp-neo-environment/best-practices-for-resilient-oauth-2-0-communication).




<a name="loio654812131e9e440d85e97648061212bb__section_oqk_jbb_yfb"/>

## Prerequisites

-   For basic authentication, assign the *manageJavaApplications* scope to the platform role used in the subaccount. See [Platform Scopes](../50-administration-and-ops-neo/platform-scopes-f226074.md).

-   For OAuth authentication and authorization, create an OAuth client and obtain an access token to call the API methods. See [Using Platform APIs](using-platform-apis-392af9d.md) as you add the *Lifecycle Management* scopes for the *Platform API OAuth* client.


<a name="loio83729f7df7074de3a795d61ae8844c0e"/>

<!-- loio83729f7df7074de3a795d61ae8844c0e -->

## Deploy an Application



<a name="loio83729f7df7074de3a795d61ae8844c0e__prereq_k2l_ky4_w1b"/>

## Prerequisites

-   You have installed a REST client.




## Context

For the purposes of this tutorial, we will deploy three `.war` files: \(app.war, example.war, demo.war\).

> ### Note:  
> The deployment with a deprecated or unsupported runtime will fail with an error message.



## Procedure

1.  Get a CSRF token.

    1.  Start a new session.

    2.  Send a *GET* CSRF Protection request:

        ```
        Client Request:
        
        GET https: api.hana.ondemand.com/lifecycle/v1/csrf
        
        Request Headers:
        X-CSRF-Token: Fetch
        Authorization: Basic UDE5NDE3OTM5NDg6RnJhZ28jNjQ3Ng==
        ```

        For OAuth Platform API authentication and authorization, the last line looks like `Authorization: Bearer a9cd683534471f499b630bb97b3d3fc`, where *a9cd683534471f499b630bb97b3d3fc* has been retrieved with `POST <host>/oauth2/apitoken/v1?grant_type=client_credentials`. For more information, see [Using Platform APIs](using-platform-apis-392af9d.md).

        ```
        Server Response:
        
        Response Status: 200
        
        Response Headers:
        X-CSRF-Token: 3B95B7A8B0E8E6B923C67E6C0BFD234D
        ```

        > ### Note:  
        > After a while the CSRF token expires. If you are using an invalid CSRF token, you will receive an error message similar to this one: ***HTTP Status 403 - CSRF token validation failed!*** If this happens, get a new token.


2.  Create an application.

    Send a *POST* Applications request:

    ```
    Client Request:
    
    POST: https://api.hana.ondemand.com/lifecycle/v1/accounts/test/apps
    
    Request Body:
    {
                   "applicationName": "myapp",
                   "runtimeName": "neo-java-web",
                   "runtimeVersion": "1",
                   "minProcesses": 1,
                   "maxProcesses": 1
    }
    ```

    ```
    Server Response:
    
    Response Status: 201
    
    Response Body:
    {
                   "metadata": {
                                  "url": "/lifecycle/v1/accounts/test/apps/myapp"
                   },
                   "entity": {
                                  "accountName": "test",
                                  "applicationName": "myapp",
                                  "runtimeName": "neo-java-web",
                                  "runtimeVersion": "1",
                                  "minProcesses": 1,
                                  "maxProcesses": 1
                   }
    }
    ```

    > ### Tip:  
    > You can add other properties to the body of the request. The properties in this example are the minimum requirements that let you execute the request successfully.

3.  Create a list of the application binaries.

    Send a *POST* Binaries request:

    ```
    Client Request:
    
    POST: https://api.hana.ondemand.com/lifecycle/v1/accounts/test/apps/myapp/binaries
    
    Request Headers:
    X-CSRF-Token: 3B95B7A8B0E8E6B923C67E6C0BFD234D
    Content-Type: application/json
    
    Request Body:
    {
                   "files": [{
                                  "path": "app.war"
                   }, {
                                  "path": "demo.war"
                   }, {
                                  "path": "example.war"
                   }]
    }
    ```

    ```
    Server Response:
    
    Response Status: 201
    
    Response Body:
    {
                   "metadata": {
                                  "url": "/lifecycle/v1/accounts/test/apps/myapp/binaries"
                   },
                   "entity": {
                                  "totalSize": 0,
                                  "status": "UPLOADING",
                                  "files": [{
                                                 "path": "app.war",
                                                 "pathGuid": "YXBwLndhcg\u003d\u003d",
                                                 "status": "UNAVAILABLE",
                                                 "entries": []
                                  }, {
                                                 "path": "example.war",
                                                 "pathGuid": "ZXhhbXBsZS53YXI\u003d",
                                                 "status": "UNAVAILABLE",
                                                 "entries": []
                                  }, {
                                                 "path": "demo.war",
                                                 "pathGuid": "ZGVtby53YXI\u003d",
                                                 "status": "UNAVAILABLE",
                                                 "entries": []
                                  }]
                   }
    }
    ```

    This request describes the metadata of the binaries and prepares them for their upload.

4.  Upload the binaries.

    > ### Note:  
    > You must start uploading the binaries within the next 2 minutes. Otherwise, the operation will be canceled and you will have to deploy the application again. If you do not start uploading the binaries within the next 2 minutes, you will receive the following response:

    ```
    Server Response:
    
    Response Status: 404
    
    Response Body:
    {
        "code": "98a59939-0e9a-430c-9ec3-c094a4d8d78d",
        "description": "Application operation is not found"
    }
    ```

    Send *PUT* Binary requests for each one of the binaries. Use the corresponding *pathGuid* values for each `.war` file from the previous *POST* Binaries response and add it to the URL:

    ```
    Client Request:
    
    PUT: https://api.hana.ondemand.com/lifecycle/v1/accounts/test/apps/myapp/binaries/YXBwLndhcg==
    
    Request Headers:
    X-CSRF-Token: 3B95B7A8B0E8E6B923C67E6C0BFD234D
    Content-Type: application/octet-stream
    
    Request Body:
    Choose to add a file and select app.war.
    ```

    ```
    Client Request:
    
    PUT: https://api.hana.ondemand.com/lifecycle/v1/accounts/test/apps/myapp/binaries/ZXhhbXBsZS53YXI=
    
    Request Headers:
    X-CSRF-Token: 3B95B7A8B0E8E6B923C67E6C0BFD234D
    Content-Type: application/octet-stream
    
    Request Body:
    Choose to add a file and select example.war.
    ```

    ```
    Client Request:
    
    PUT: https://api.hana.ondemand.com/lifecycle/v1/accounts/test/apps/myapp/binaries/ZGVtby53YXI=
    
    Request Headers:
    X-CSRF-Token: 3B95B7A8B0E8E6B923C67E6C0BFD234D
    Content-Type: application/octet-stream
    
    Request Body:
    Choose to add a file and select demo.war.
    ```

    If the operation is successful, the response for all three requests should return 200 without a body.

5.  List the binaries.

    Send a *GET* Binaries request every 5-10 seconds:

    ```
    Client Request:
    
    GET: https://api.hana.ondemand.com/lifecycle/v1/accounts/test/apps/myapp/binaries
    ```

    Repeat the process and observe the general status until you receive the *FAILED* or the *DEPLOYED* values. The *DEPLOYED* status shows that the deployment operation has been successful and you can now start your application:

    ```
    Server Response:
    
    Response Status: 200
    
    Response Body:
    {
                   "metadata": {},
                   "entity": {
                                  "totalSize": 57857,
                                  "status": "DEPLOYED",
                                  "warnings": "Warning: No compute unit size was specified for the application so size was set automatically to \u0027lite\u0027.",
                                  "files": [{
                                                 "path": "app.war",
                                                 "pathGuid": "YXBwLndhcg\u003d\u003d",
                                                 "size": 17194,
                                                 "status": "AVAILABLE",
                                                 "hash": "6c8b99a72d5b42db31cc576273260f9c2f316c1ac7dcc4a8c845412e51d420f0dcf53f4035745e303cdd43bf73974fada19839920d845010013bf422ae5bc4dd",
                                                 "entries": [{...}]
                                  }, {
                                                 "path": "example.war",
                                                 "pathGuid": "ZXhhbXBsZS53YXI\u003d",
                                                 "size": 37615,
                                                 "status": "AVAILABLE",
                                                 "hash": "7b2a80771f79d0740f629bdaaf019c550b10df55eec8789447ec02fa93e7fdb1f6f47f4864769f4a4f027a4bca8bfa1ea45a83c5fb38ae539b397abe9fe66be1",
                                                 "entries": [{...}]
                                  }, {
                                                 "path": "demo.war",
                                                 "pathGuid": "ZGVtby53YXI\u003d",
                                                 "size": 3048,
                                                 "status": "AVAILABLE",
                                                 "hash": "8c4b39bfe3a034d64e8592e7cf638ac4b5985c5f9a4f691270d040b8f15dc8edbb6284bd5431f1a240abaad3b2288411563b784b691c35ca677ae5e9ced565a9",
                                                 "entries": [{...}]
                                  }]
                   }
    }
    ```

    The binaries are now officially *DEPLOYED*. You can also see that each binary has status *AVAILABLE*.


<a name="loiocf6608a1b8ed4e30a32393ed39d1e4a3"/>

<!-- loiocf6608a1b8ed4e30a32393ed39d1e4a3 -->

## Deploy an Application with a Copy Operation

You can deploy an application by copying an existing application.



<a name="loiocf6608a1b8ed4e30a32393ed39d1e4a3__prereq_k2l_ky4_w1b"/>

## Prerequisites

-   For basic authentication, assign the *Administrator* role to the user.

-   You have an existing source application deployed on the platform.

-   You have installed a REST client.




## Context

In this tutorial, you will deploy an application from an existing application by specifying the source account and application as query parameters.

> ### Note:  
> In platform OAuth, the copy operation is applicable for applications in the same account.



## Procedure

1.  Get a CSRF token.

    1.  Start a new session.

    2.  Send a *GET* CSRF Protection request:

        ```
        Client Request:
        
        GET https: api.hana.ondemand.com/lifecycle/v1/csrf
        
        Request Headers:
        X-CSRF-Token: Fetch
        Authorization: Basic UDE5NDE3OTM5NDg6RnJhZ28jNjQ3Ng==
        ```

        For OAuth Platform API authentication and authorization, the last line looks like `Authorization: Bearer a9cd683534471f499b630bb97b3d3fc`, where *a9cd683534471f499b630bb97b3d3fc* has been retrieved with `POST <host>/oauth2/apitoken/v1?grant_type=client_credentials`. For more information, see [Using Platform APIs](using-platform-apis-392af9d.md).

        ```
        Server Response:
        
        Response Status: 200
        
        Response Headers:
        X-CSRF-Token: 3B95B7A8B0E8E6B923C67E6C0BFD234D
        ```

        > ### Note:  
        > After a while the CSRF token expires. If you are using an invalid CSRF token, you will receive an error message similar to this one: ***HTTP Status 403 - CSRF token validation failed!*** If this happens, get a new token.


2.  Create an application with a copy operation of the source application.

    Send a *POST* Applications request:

    ```
    Client Request:
    
    POST: https://api.hana.ondemand.com/lifecycle/v1/accounts/test/apps?operation=copy&sourceAccount=sourcesubaccount&sourceApplication=sourceapp
    
    Request Body:
    {
                   "applicationName": "myapp",
                   "runtimeName": "neo-java-web",
                   "runtimeVersion": "1",
                   "minProcesses": 1,
                   "maxProcesses": 1
    }
    ```

    ```
    Server Response:
    
    Response Status: 201
    
    Response Body:
    {
                   "metadata": {
                                  "url": "/lifecycle/v1/accounts/test/apps/myapp"
                   },
                   "entity": {
                                  "accountName": "test",
                                  "applicationName": "myapp",
                                  "runtimeName": "neo-java-web",
                                  "runtimeVersion": "1",
                                  "minProcesses": 1,
                                  "maxProcesses": 1
                   }
    }
    ```

    > ### Tip:  
    > Тhe body is optional for the request. If you do not specify a body, the REST API will take the parameters from the source application.

    The application is deployed by using the binaries in the source application.

3.  List the binaries.

    Send a *GET* Binaries request every 5-10 seconds:

    ```
    Client Request:
    
    GET: https://api.hana.ondemand.com/lifecycle/v1/accounts/test/apps/myapp/binaries
    ```

    Repeat the process and observe the general status until you receive the *FAILED* or the *DEPLOYED* values. The *DEPLOYED* status shows that the copy operation has been successful and you can now start your application:

    ```
    Server Response:
    
    Response Status: 200
    
    Response Body:
    {
                   "metadata": {},
                   "entity": {
                                  "totalSize": 57857,
                                  "status": "DEPLOYED",
                                  "warnings": "Warning: No compute unit size was specified for the application so size was set automatically to \u0027lite\u0027.",
                                  "files": [{
                                                 "path": "app.war",
                                                 "pathGuid": "YXBwLndhcg\u003d\u003d",
                                                 "size": 17194,
                                                 "status": "AVAILABLE",
                                                 "hash": "6c8b99a72d5b42db31cc576273260f9c2f316c1ac7dcc4a8c845412e51d420f0dcf53f4035745e303cdd43bf73974fada19839920d845010013bf422ae5bc4dd",
                                                 "entries": [{...}]
                                  }, {
                                                 "path": "example.war",
                                                 "pathGuid": "ZXhhbXBsZS53YXI\u003d",
                                                 "size": 37615,
                                                 "status": "AVAILABLE",
                                                 "hash": "7b2a80771f79d0740f629bdaaf019c550b10df55eec8789447ec02fa93e7fdb1f6f47f4864769f4a4f027a4bca8bfa1ea45a83c5fb38ae539b397abe9fe66be1",
                                                 "entries": [{...}]
                                  }, {
                                                 "path": "demo.war",
                                                 "pathGuid": "ZGVtby53YXI\u003d",
                                                 "size": 3048,
                                                 "status": "AVAILABLE",
                                                 "hash": "8c4b39bfe3a034d64e8592e7cf638ac4b5985c5f9a4f691270d040b8f15dc8edbb6284bd5431f1a240abaad3b2288411563b784b691c35ca677ae5e9ced565a9",
                                                 "entries": [{...}]
                                  }]
                   }
    }
    ```

    The binaries are now officially *DEPLOYED*. You can also see that each binary has status *AVAILABLE*.


<a name="loio7fc54044e29f4fb3aa39a171032b6b17"/>

<!-- loio7fc54044e29f4fb3aa39a171032b6b17 -->

## Verify Application Binaries

Use the response to verify the binaries of an application.



<a name="loio7fc54044e29f4fb3aa39a171032b6b17__prereq_zfx_wk3_hdb"/>

## Prerequisites

You have installed a REST client.



## Context

You can validate the content of an application by verifying the hash values in a binaries response. For example, you verify changes to an application by comparing hash values of deployed binaries with the hash values of modified binaries. You can use this verification to be sure that you have the correct binaries for deploy or update in a copy operation.



## Procedure

1.  Get a CSRF token. If you try to start your application long after its deployment, the token has most probably expired.

    Send a *GET* CSRF Protection request.

    > ### Note:  
    > If your session is still actively running, you do not have to request a new CSRF token. In this case, we will use the CSRF token generated during the deployment scenario.

2.  List the binaries.

    Send a *GET* Binaries request:

    ```
    Client Request:
    
    GET: https://api.hana.ondemand.com/lifecycle/v1/accounts/test/apps/myapp/binaries
    ```

3.  Use the hash values of the binaries to compare with those of previous binaries before you start another operation.


<a name="loiof2cc4cdc7ce04291bcad59c0c7fad61f"/>

<!-- loiof2cc4cdc7ce04291bcad59c0c7fad61f -->

## Download Application Binaries

Download the binaries of a Java application in a ZIP file.



<a name="loiof2cc4cdc7ce04291bcad59c0c7fad61f__prereq_zfx_wk3_hdb"/>

## Prerequisites

-   You have an existing source application deployed on the platform.

-   The *downloadJavaApplicationBinaries* scope is assigned to the used platform role for the subaccount. See [Platform Scopes](../50-administration-and-ops-neo/platform-scopes-f226074.md).

-   You've installed a REST client.




## Context

You can download the latest deployed content of an application as a ZIP file. The ZIP file includes all the files that you've deployed for your Java application.



## Procedure

1.  Request the download of the binaries.

    Send a *GET* binaries request:

    ```
    Client Request:
    
    GET: https://api.hana.ondemand.com/lifecycle/v1/accounts/mysubaccount/apps/myapp/binaries/files
    ```

2.  Save the `mysubaccount_myapp.zip` file locally.


<a name="loio2d3be560df574092909ed8171ec197ec"/>

<!-- loio2d3be560df574092909ed8171ec197ec -->

## Start an Application



## Procedure

1.  Get a CSRF token. If you try to start your application long after its deployment, the token has most probably expired.

    Send a *GET* CSRF Protection request.

    > ### Note:  
    > If your session is still actively running, you do not have to request a new CSRF token. In this case, we will use the CSRF token generated during the deployment scenario.

2.  Start the previously deployed application.

    Send a *PUT* Application State request and set the value of the *applicationState* property to *STARTED*:

    ```
    Client Request:
    
    PUT: https://api.hana.ondemand.com/lifecycle/v1/accounts/test/apps/myapp/state
    
    Request Headers:
    X-CSRF-Token: 3B95B7A8B0E8E6B923C67E6C0BFD234D
    Content-Type: application/json
    
    Request Body:
    {
        "applicationState": "STARTED"
    }
    ```

    ```
    Server Response:
    
    Response Status: 200
    
    Response Body:
    {
                   "metadata": {
                                  "message": "Triggered start of application process.",
                                  "url": "/lifecycle/v1/accounts/test/apps/myapp",
                                  "createdAt": 1501825923105,
                                  "updatedAt": 1501827428000
                   },
                   "entity": {
                                  "applicationState": "STARTING",
                                  "processes": [{
                                                 "processId": "dc1460001710d282b42b7331f1831ec5ad9c1924",
                                                 "status": "PENDING",
                                                 "lastStatusChange": 0,
                                                 "availabilityZone": "",
                                                 "computeUnitSize": "LITE"
                                  }],
                                  "warningMessage": "Triggered start of application process."
                   }
    }
    ```

    The *applicationState* value will change from *STARTING* \(or *PENDING*\) to *STARTED*.

3.  Make sure the application is working properly.

    Send a *GET* Application State request to verify whether your application is started. Send this request every 5-10 seconds and check the *applicationState* property in the response. If that property shows the *STARTED* value, then you have successfully started your application:

    ```
    Client Request:
    
    GET: https://api.hana.ondemand.com/lifecycle/v1/accounts/test/apps/myapp/state
    ```

    ```
    Server Response:
    
    Response Body:
    {
                   "metadata": {
                                  "domain": "hana.ondemand.com",
                                  "aliases": "[\"/DemoApp\",\"example\",\"/\"]",
                                  "accessPoints": ["https://myapptest.int.hana.ondemand.com", "https://myapptest.hana.ondemand.com"],
                                  "runtime": {
                                                 "id": "neo-java-web",
                                                 "state": "recommended",
                                                 "expDate": "1541203200000",
                                                 "displayName": "Java Web",
                                                 "relDate": "1501718400000",
                                                 "version": "1.133.3"
                                  },
                                  "url": "/lifecycle/v1/accounts/test/apps/myapp",
                                  "createdAt": 1501825923105,
                                  "updatedAt": 1501827428000
                   },
                   "entity": {
                                  "applicationState": "STARTED",
                                  "loadBalancerState": "ENABLED",
                                  "urls": ["https://myapptest.int.hana.ondemand.com", "https://myapptest.hana.ondemand.com"],
                                  "processes": [{
                                                 "processId": "dc1460001710d282b42b7331f1831ec5ad9c1924",
                                                 "status": "STARTED",
                                                 "lbStatus": "ENABLED",
                                                 "lastStatusChange": 1501827728209,
                                                 "runtime": {
                                                                "id": "neo-java-web",
                                                                "state": "recommended",
                                                                "expDate": "1541203200000",
                                                                "displayName": "Java Web",
                                                                "relDate": "1501718400000",
                                                                "version": "1.133.3.2"
                                                 },
                                                 "availabilityZone": "PRSAG",
                                                 "computeUnitSize": "LITE"
                                  }]
                   }
    }
    ```


<a name="loio38829d2c139c47b3a1c1d64e6ce6d4f8"/>

<!-- loio38829d2c139c47b3a1c1d64e6ce6d4f8 -->

## Stop an Application



## Procedure

1.  Get a CSRF token. If you try to start your application long after its deployment, the token has most probably expired.

    Send a *GET* CSRF Protection request.

    > ### Note:  
    > If your session is still actively running, you don't have to request a new CSRF token. In this case, we will use the CSRF token generated during the deployment scenario.

2.  Stop the application.

    Send a *PUT* Application State request and set the value of the *applicationState* property to*STOPPED*:

    ```
    Client Request:
    
    PUT: https://api.hana.ondemand.com/lifecycle/v1/accounts/test/apps/myapp/state
    
    Request Headers:
    X-CSRF-Token: 3B95B7A8B0E8E6B923C67E6C0BFD234D
    Content-Type: application/json
    
    Request Body:
    {
        "applicationState": "STOPPED"
    }
    ```

    ```
    Server Response:
    
    Response Status: 200
    
    Response Body:
    {
                   "metadata": {
                                  "message": "Triggered stop of application process.",
                                  "url": "/lifecycle/v1/accounts/test/apps/myapp",
                                  "createdAt": 1501825923105,
                                  "updatedAt": 1501827428000
                   },
                   "entity": {
                                  "applicationState": "STOPPING",
                                  "processes": [{
                                                 "processId": "dc1460001710d282b42b7331f1831ec5ad9c1924",
                                                 "status": "PENDING",
                                                 "lastStatusChange": 0,
                                                 "availabilityZone": "",
                                                 "computeUnitSize": "LITE"
                                  }],
                                  "warningMessage": "Triggered stop of application process."
                   }
    }
    ```

3.  Check if the application is stopped.

    Send a *GET* Application State request. Send this request in a loop every 5-10 seconds and pay close attention to the *applicationState* property in the response. If that property shows the *STOPPED* value, then you have successfully stopped your application.

    ```
    Client Request:
    
    GET: https://api.hana.ondemand.com/lifecycle/v1/accounts/test/apps/myapp/state
    ```

    ```
    Server Response:
    
    Response Body:
    {
        "metadata": {
            "aliases": "[]",
            "runtime": {
                "id": "neo-java-web",
                "state": "recommended",
                "expDate": "1541203200000",
                "displayName": "Java Web",
                "relDate": "1501718400000",
                "version": "1.133.3"
            },
            "url": "/lifecycle/v1/accounts/test/apps/myapp",
            "createdAt": 1502274734263,
            "updatedAt": 1502274835000
        },
        "entity": {
            "applicationState": "STOPPED",
            "processes": []
        }
    }
    ```


**Related Information**  


[Java ALM API](https://api.sap.com/api/SAP_HCP_Lifecycle_Management)

