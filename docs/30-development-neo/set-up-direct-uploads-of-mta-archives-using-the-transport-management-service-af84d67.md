<!-- loioaf84d67f4be24542ac5e46f613a99435 -->

# Set Up Direct Uploads of MTA Archives Using the Transport Management Service

Create the required configurations for using the Transport Management Service to transport MTA archives between subaccounts.



<a name="loioaf84d67f4be24542ac5e46f613a99435__prereq_rhz_rjn_zcb"/>

## Prerequisites

-   You are subscribed and have access to the Transport Management Service, and have set up the environment to transport MTA archives directly in an application. For more information, see [Set Up the Environment to Transport Content Archives Directly in an Application](https://help.sap.com/viewer/7f7160ec0d8546c6b3eab72fb5ad6fd8/Cloud/en-US/8d9490792ed14f1bbf8a6ac08a6bca64.html).
-   You have a service key, which contains parameters you need to refer in the required destinations.



<a name="loioaf84d67f4be24542ac5e46f613a99435__context_jyt_sjn_zcb"/>

## Context

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of the following technology portfolios: application development; process automation; integration; data, analytics, and enterprise planning; artificial intelligence. The platform offers users the ability to turn data into business value, compose end-to-end business processes, connect entire IT landscapes, and personalize, build and extend SAP applications. This reduces the overall total cost of ownership maintaining SAP landscapes and third-party software across end-to-end business processes.") :arrow_upper_right:.**

To perform transports of MTA archives using the Transport Management Service, you have to create and set up destinations defining the source transport node for transporting MTA archives. Proceed as follows:



<a name="loioaf84d67f4be24542ac5e46f613a99435__steps_mhb_tjn_zcb"/>

## Procedure

1.  In the SAP BTP cockpit, navigate to *Services* and enable the *Solution Lifecycle Management* service.

2.  Navigate to the *Services* \> *Solution Lifecycle Management* \> *Configure Destinations*.

3.  Choose *New Destination* to create the destination directed at the Transport Management Service URL and defining the source transport node. Enter the following parameters:

    -   Name: `TransportManagementService`

        > ### Note:  
        > This destination name is mandatory.

    -   Type: `HTTP`
    -   URL: `<"uri" parameter specified in the Service Key>`
    -   Authentication: `OAuth2ClientCredentials`
    -   Proxy Type: `Internet`
    -   Client ID: `<"clientid" specified in the Service Key>`
    -   Client Secret: `<"clientsecret" specified in the Service Key>`
    -   Token Service URL: `<"url" specified in the Service Key>`, followed by the path `/oauth/token`. For example:

        > ### Example:  
        > `https://tmsdemo123.authentication.sap.hana.ondemand.com/oauth/token`

    -   You also have the following additional properties:

        -   \(Mandatory\) sourceSystemId: `<System ID of the source system in the transport route, which is defined above>`

        > ### Note:  
        > You have to manually enter the attributes names, as they are not available in the drop-down list.


4.  Save the destination.




<a name="loioaf84d67f4be24542ac5e46f613a99435__result_k3c_cxb_1db"/>

## Results

You can use the Transport Management Service to transport MTA archives.

**Related Information**  


[Get Access](https://help.sap.com/viewer/7f7160ec0d8546c6b3eab72fb5ad6fd8/Cloud/en-US/13894bed9e2d4b25aa34d03d002707f9.html)

[Set Up the Environment to Transport MTAs Directly in an Application](https://help.sap.com/viewer/7f7160ec0d8546c6b3eab72fb5ad6fd8/Cloud/en-US/8d9490792ed14f1bbf8a6ac08a6bca64.html)

[Creating Service Keys](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/4514a14ab6424d9f84f1b8650df609ce.html "You can use service keys to generate credentials to communicate directly with a service instance. Once you configure them for your service, local clients, apps in other spaces, or entities outside your deployment can access your service with these keys.") :arrow_upper_right:

[Content Transport](https://help.sap.com/viewer/368c481cd6954bdfa5d0435479fd4eaf/Cloud/en-US/e3c79d65aa604b80992e20609881ad7a.html)

