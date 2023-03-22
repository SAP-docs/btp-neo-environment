<!-- loio11fe332c05cb4d5fa9f752736f6b7575 -->

# Best Practices for Resilient OAuth 2.0 Communication

Best practices for secure and resilient OAuth 2.0 authorization. Guidance on how to protect against common threats and vulnerabilities.



<a name="loio11fe332c05cb4d5fa9f752736f6b7575__section_p2p_rbc_rwb"/>

## Prerequisites

-   You are a member of a subaccount with an administrator role in the Neo environment. See [Managing Member Authorizations in the Neo Environment](../50-administration-and-ops-neo/managing-member-authorizations-in-the-neo-environment-a1ab5c4.md).
-   You have developed an OAuth-protected application \(resource server\). If you are not sure about which OAuth 2.0 authorization grant you are currently using, see [Which Is My Current OAuth 2.0 Authorization Grant?](which-is-my-current-oauth-2-0-authorization-grant-f77bab7.md).
-   You have deployed the application on the Neo environment. See [Deploying and Updating Java Applications](../30-development-neo/deploying-and-updating-java-applications-e5dfbc6.md). The application is running on the latest supported version of its runtime \(see [Check the Process Status](../50-administration-and-ops-neo/check-the-process-status-499992d.md)\). We recommend that you restart the application if you have not done it recently \(see [Restart Applications](../50-administration-and-ops-neo/restart-applications-7b2d704.md)\).
-   In case you are currently in the process of developing an OAuth-protected application, see [Which OAuth 2.0 Authorization Grant Should I Use?](which-oauth-2-0-authorization-grant-should-i-use-f5a9246.md) \(section OAuth 2.0 Authorization Grant\) for directions on which OAuth 2.0 authorization grant to use depending on your case.



<a name="loio11fe332c05cb4d5fa9f752736f6b7575__section_awm_wbc_rwb"/>

## General Best Practices

-   Use Access Tokens of type JWT. See [OAuth 2.0 JWT Token Types](oauth-2-0-jwt-token-types-3f26e04.md) 
-   Consume OAuth 2.0 protected resources through Connectivity Destinations. See [Using OAuth 2.0 Authentication with Connectivity Destinations](using-oauth-2-0-authentication-with-connectivity-destinations-c8b8c06.md).
-   There are several best practices recommended for all cases. See [Achieving Resilient OAuth 2.0 Authorization](achieving-resilient-oauth-2-0-authorization-2f76c6c.md).



<a name="loio11fe332c05cb4d5fa9f752736f6b7575__section_xm1_zbc_rwb"/>

## Best Practices for Scenarios

-   [Periodic Token-Based Operations](periodic-token-based-operations-ead7249.md)
-   [Using OAuth 2.0 Authorization at Irregular Intervals](using-oauth-2-0-authorization-at-irregular-intervals-7263696.md) 

