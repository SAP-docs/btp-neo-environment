<!-- loioa8f2255658ba4cbfb3ec3ab0f928f360 -->

# Tenant Context API

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**



## Overview

In a provider-managed application scenario, each application consumer gets its own access URL for the provider application. To be able to use an application with a consumer-specific URL, the consumer must be subscribed to the provider application. When an application is launched via a consumer-specific URL, the tenant runtime is able to identify the current consumer of the application. The tenant runtime provides an API to retrieve the current application consumer. Each application consumer is identified by a unique ID, which is called ***tenantId***.

Since the information about the current consumer is extracted from the request URL, the tenant runtime can only provide a tenant ID if the current thread has been started via an HTTP request. In case the current thread wasn’t started via an HTTP request \(for example, a background process\), the tenant context API only returns a tenant if the current application instance has been started for a dedicated consumer. If the current application instance is shared between multiple consumers and the thread wasn’t started via an HTTP request, the tenant runtime throws an exception.

> ### Note:  
> The tenant context API is of interest to application providers only.



## Tenant Context API


<table>
<tr>
<th valign="top">

API



</th>
<th valign="top">

Description



</th>
</tr>
<tr>
<td valign="top">

`com.sap.cloud.account`



</td>
<td valign="top">

The tenant context API provides the following methods:

-   ***getTenant*** - returns the tenant associated with the current thread.
-   ***execute*** - executes `callable.call()` method on behalf of the specified tenant and returns the result of a called method.
-   ***getSubscribedTenants*** - returns all tenants subscribed to a calling application, or empty collection if there are no subscribed tenants.

To find the tenant context API in your local SDK installation, go to: `<SDK_location>/javadoc/com/sap/cloud/account`

For more information, see [API Documentation](api-documentation-4570e92.md).



</td>
</tr>
</table>



## Tenant Context API via JNDI Lookup

To look up the `TenantContext` API via JNDI, follow the steps:

1.  Add the following resource reference of type `com.sap.cloud.account.TenantContext` in your `web.xml` file:

    ```
    
    <resource-ref>
        <res-ref-name>TenantContext</res-ref-name>
        <res-type>com.sap.cloud.account.TenantContext</res-type>
    </resource-ref>
    ```

2.  Then, use the following code to look up:

    ```
    
    Context ctx = new InitialContext();
    TenantContext tenantctx = (TenantContext) ctx.lookup("java:comp/env/TenantContext");
    ```




## Tenant Context API via Resource Injection

To get an instance of the `TenantContext` API, use resource injection the following way:

```

@Resource
private TenantContext tenantContext;
```

> ### Note:  
> When you use WebSockets, the `TenantId` and `AccountName` parameters, provided by the `TenantContext` API, are correct only during processing of WebSocket handshake request. This is because what follows after the handshake doesn’t conform to the HTTP protocol. In case `TenantId` and `AccountName` are needed during next WebSocket requests, they should be stored into the HTTP session, and, if needed, you can use `TenantContext.execute(...)` to operate on behalf of the relevant tenant.



## Account API

The `Account` API provides methods to get subaccount ID, subaccount display name, and attributes.

For more information, see [API Documentation](api-documentation-4570e92.md).

You can access the `Account` API in two ways.

-   Via looking up or injecting the `TenantContext` API:

    > ### Sample Code:  
    > ```
    > 
    > Context ctx = new InitialContext();
    > TenantContext tenantctx = (TenantContext) ctx.lookup("java:comp/env/TenantContext");
    >  
    > Account account = tenantctx.getTenant().getAccount();
    > ```

-   Via the `getSubscribedTenants` method:

    > ### Sample Code:  
    > ```
    > 
    > 
    > Context ctx = new InitialContext();
    > TenantContext tenantctx = (TenantContext) ctx.lookup("java:comp/env/TenantContext");
    >  
    > Collection<Tenant> subscribedTenants = tenantctx.getSubscribedTenants();
    >  
    > for(Tenant tenant: subscribedTenants ) {
    >     Account subscribedAccount = tenant.getAccount();
    > }
    > ```


**Related Information**  


[Developing Multitenant Applications in the Neo Environment](developing-multitenant-applications-in-the-neo-environment-54a7615.md "In the Neo environment of SAP BTP, you can develop and run multitenant (tenant-aware) applications. These applications run on a shared compute unit that can be used by multiple consumers (tenants). Each consumer accesses the application through a dedicated URL.")

[Default Trace File](../50-administration-and-ops-neo/default-trace-file-1b651b3.md "")

[Providing Java Multitenant Applications to Tenants for Testing](../22-getting-started-neo/providing-java-multitenant-applications-to-tenants-for-testing-b093032.md "Using the console client, you can create subaccounts and subscribe them to a provider application to test how applications can be provided to multiple consumers.")

