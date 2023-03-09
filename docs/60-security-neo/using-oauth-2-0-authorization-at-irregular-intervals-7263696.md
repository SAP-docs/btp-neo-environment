<!-- loio7263696f14b745bd86880702622c38c5 -->

# Using OAuth 2.0 Authorization at Irregular Intervals

This document provides guidance for client applications that require ongoing OAuth 2.0 authorization for operations that occur at irregular intervals. If your application falls into this category, this document provides valuable guidance on how to use OAuth 2.0 authorization in a secure and efficient manner.



<a name="loio7263696f14b745bd86880702622c38c5__section_zfm_glz_qwb"/>

## The Problem

Generating multiple tokens per execution instead of reusing issued tokens for OAuth 2.0 authorization scenarios significantly increases the risk of encountering issues when the OAuth Service experiences reduced responsiveness. To minimize this risk, the following guidelines can help address this challenge and ensure that your application can handle such scenarios in a secure and efficient manner.



<a name="loio7263696f14b745bd86880702622c38c5__section_wsp_fmz_qwb"/>

## Guidelines

To optimize the use of access tokens when accessing OAuth 2.0 protected resources in the Neo environment, we recommend configuring the token validity to be longer, such as 12 or 24 hours. However, using the same token for the entire validity period is not advisable. Instead, generating a new token every 1 or 2 hours and using only the latest one for verification purposes is suggested.

> ### Tip:  
> It is not advisable to use tokens with a longer validity period due to the increased risk of unauthorized access in the event of token leakage.

If generating a new token fails, even after a retry, it may indicate that the OAuth Service is experiencing availability problems. Nonetheless, the most recently issued token can still be utilized until the OAuth Service is fully restored, ensuring the client application remains unaffected.

Reusing the same token for most of the operations increases the resilience of the OAuth 2.0 authorization, as frequently used opaque tokens have a higher chance of successful verification during degradation of the OAuth Service responsiveness. This is due to a policy that prioritizes more recently used tokens.

Using tokens in JWT \(JSON Web Token\) format further increases the robustness of the scenario, as JWT tokens do not require communication between the application and OAuth Service to be verified.

For more information about how to issue tokens in JWT format, see [OAuth 2.0 JWT Token Types](oauth-2-0-jwt-token-types-3f26e04.md).

