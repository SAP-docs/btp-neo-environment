<!-- loio0ce18cefc6894278a8287e2222d5ec33 -->

# Mitigating Third-Party Cookie Deprecation

Mitigate third-party cookie deprecation if your application is affected by it.



## Context

Google have announced their new [third-party cookie deprecation](https://chromestatus.com/feature/5133113939722240) policy for enhanced privacy protection. Note that this doesn’t mean blocking all third-party cookies but only the ones that don’t have partitioned cookie attribute.

If your Neo application is **embedded in an iFrame** element and supports *OAuth 2.0*, *OIDC* or *SAML 2.0* authentication, some of the major authentication scenarios may be affected. For example:

-   Authentication within a third-party context
-   Single Sign-On \(SSO\) and Single Logout \(SLO\) between websites accessed in both first-party and third-party contexts
-   Session sharing among first party and third party context.

To mitigate this, follow the steps below for enabling cookie partitioning. It allows you to maintain seamless authentication experiences across your applications even as third-party cookies are phased out.

> ### Note:  
> For this mitigation, make sure your application users use a web browser that supports the following:
> 
> -   Cookie partitioning \(such as Chrome 109 or higher, Edge 114 or higher, or Firefox 109 or higher\).
> 
>     Users of lower browser versions will not be affected \(their scenarios will continue to work without change\). However, they will not be able to benefit from the partitioned cookies we use either.
> 
> -   \(For the *OIDC* and *SAML 2.0* scenarios only\) Opening a new tab/opening popups for the web site running the application. The *OAuth 2.0* scenario works without tabs/popups enabled.



<a name="loio0ce18cefc6894278a8287e2222d5ec33__steps-unordered_gvc_dqk_rdc"/>

## Procedure

1.  Set the required property/attribute as follows.

    -   **Java Application**: Add the system property `-Dcom.sap.cloud.security.3pc.partitioning.enabled=true`. How to set the property:

        -   *During deployment*: pass it as `--vm-arguments` parameter value to the [rolling-update](../50-administration-and-ops-neo/rolling-update-3f5d412.md) or [deploy](../50-administration-and-ops-neo/deploy-937db4f.md) command.
        -   *After deployment*: use the [set-application-property](../50-administration-and-ops-neo/set-application-property-113e957.md) command and [restart](../50-administration-and-ops-neo/restart-7c0f7a1.md) the application.

        > ### Note:  
        > This enables cookie partitioning for *all* mentioned scenarios \(*OAuth 2.0*, *OIDC* and *SAML 2.0*\) **at the same time**. Note that you cannot have it enabled for only some of the scenarios.

    -   **HTML5 Application**: Add the attribute `sessionReuse: true` in the `neo-app.json` file and re-deploy the application. See [Application Descriptor File](../30-development-neo/application-descriptor-file-aed1ffa.md).

2.  Make sure the application users delete the cookies in their web browsers. Either inform them to do so or provide a mechanism for cookie deletion.




<a name="loio0ce18cefc6894278a8287e2222d5ec33__result_lyz_brk_rdc"/>

## Results

Authentication scenarios continue functioning even when browsers reject third-party cookies.

The session in the third-party context \(within the iFrame\) is maintained using partitioned cookies, which are allowed by the [CHIPS specification](https://github.com/privacycg/CHIPS) as a replacement mechanism for deprecated third-party cookies.

> ### Tip:  
> If you need to revert this mitigtion for some reason, re-deploy using [rolling-update](../50-administration-and-ops-neo/rolling-update-3f5d412.md) or [deploy](../50-administration-and-ops-neo/deploy-937db4f.md) command without the above system property, and make sure the application users delete browser cookies again.

**Related Information**  


[Declarative Authentication](authentication-e637f62.md#loioe36c712efa844e8199a9c4bd681cb4e0)

[OpenID Connect \(OIDC\) Authentication](openid-connect-oidc-authentication-084c6fb.md "Protect your applications on SAP BTP, Neo environment with OpenID Connect (OIDC) authentication method using an Identity Authentication tenant as an OpenID Connect provider.")

[OAuth 2.0 Service](oauth-2-0-service-e526ca3.md "Use OAuth 2.0 service on SAP BTP to protect applications in the Neo environment using the OAuth 2.0 protocol.")

