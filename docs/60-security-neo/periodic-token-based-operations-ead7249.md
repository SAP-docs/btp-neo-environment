<!-- loioead72491ef16469f9d5c9d2917723fb3 -->

# Periodic Token-Based Operations

This document is applicable for customers who have operations requiring OAuth 2.0 authorization for a brief time. These operations can include, but are not limited to background data job synchronization, one-time operations during application startup, or operations that are triggered and constantly use OAuth 2.0 authorization thorough their brief execution.

> ### Caution:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/docs/btp/sap-business-technology-platform/sap-business-technology-platform?version=Cloud) .**

> ### Tip:  
> Additional IP outbound addresses will soon be used in all regions in the Neo environment. For more information, see [Additional IP Addresses Added to SAP BTP, Neo Runtime Regions](https://help.sap.com/whats-new/cf0cb2cb149647329b5d02aa96303f56?version=Cloud&Component=Region&Valid_as_Of=2026-11-02:2026-11-02). To subscribe to such notifications, see SAP Note [3513325](https://me.sap.com/notes/3513325).



<a name="loioead72491ef16469f9d5c9d2917723fb3__section_hrr_v1c_rwb"/>

## The Problem

Clients that are not reusing issued tokens for the operations they made, but instead are issuing multiple tokens per execution are significantly more exposed to the risk of experiencing issues during degradation of the OAuth Service responsiveness. For that reason, we have developed a guideline that will help with the mitigation of this problem.



<a name="loioead72491ef16469f9d5c9d2917723fb3__section_l43_w1c_rwb"/>

## Guidelines

In these cases, subaccount administrators should configure the OAuth client token validity to be equal to the expected duration of the operation plus a comfortable buffer. This is to ensure that the execution process will have a valid token to reuse during its lifetime. This recommendation is made since clients should reuse the tokens to avoid token issuing operations, which might fail and can be expensive in terms of resources and increased execution time.

> ### Note:  
> For example, if the average time for executing an operation takes approximately 20 minutes, you might consider using a token with validity of 1 hour, so that you have enough buffer in case of slower execution or need of retrying failed operations.

> ### Note:  
> An alternative approach to using a token with a validity long enough to last the operation execution is to use a similar mechanism. See [Using OAuth 2.0 Authorization at Irregular Intervals](using-oauth-2-0-authorization-at-irregular-intervals-7263696.md).

SAP Business Technology Platform \(BTP\) Neo OAuth Service can issue tokens in two formats – opaque and JWT \(JSON Web Token\). When opaque tokens are used, the application server must communicate with the OAuth Service to validate the token. Because of that, they are prone to failures in case of degradation in OAuth Service responsiveness. In contrast, JWT tokens do not require communication between the application and OAuth Service. As a result, they are significantly more resilient to failures of the OAuth Service. For that reason, we highly recommend their usage.

For more information, see [OAuth 2.0 JWT Token Types](oauth-2-0-jwt-token-types-3f26e04.md).

