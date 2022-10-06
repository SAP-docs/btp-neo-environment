<!-- loio5eccd481731c498588a466f6ec70fc69 -->

# OAuth 2.0 Clients with Unlimited Validity Tokens

The support for clients with unlimited validity tokens is discontinued. Use the steps below to re-configure existing clients.



## Context

If you have existing clients with unlimited token validity \(the *Token Lifetime* value is set to *0*\), they will continue to issue tokens with unlimited validity for some time \(timeline will be provided soon\). When we will disable this feature, we will set an **automatic vaildity period of 180 days** to existing clients and tokens.

> ### Tip:  
> We recommend that you change the token validity to a supported value suitable for your scenario as soon as possible instead of waiting for the system to set it automatically.

> ### Note:  
> When you change the token validity of a client or when the system sets it automatically, all previously issued tokens are also affected, so you will need to re-issue the tokens when their validity expires \(and some may expire immediately\). The validity period is calculated starting from the time the token was issued. For example, if a token was issued 3 months ago, and its validity period is 6 months, the token will expire in 3 months. If, however, the token was issued 2 years ago, it will expire immediately after changing the client configuration.



## Procedure

1.  Evaluate your existing OAuth 2.0 scenario.

    1.  Determine the right token validity period for your scenario. Use a value bigger than 0 and smaller than 180 days.

    2.  If required, implement changes over the application \(or the OAuth scenario itself\) to re-issue expired tokens instead of relying on a single unlimited one.


2.  If possible, test the scenario before changing productive applications and their OAuth clients.

    If you have a testing \(staging\) subaccount, you can deploy the application and OAuth clients there. See [Using Multiple Subaccounts for Staged Application Development](https://help.sap.com/docs/BTP/ea72206b834e4ace9cd834feed6c0e09/2611e633b9044186a68a316a6e2b0789.html?version=Cloud).

3.  Deploy the changed applications productively, and update their resprective OAuth clients.

    Updating the OAuth clients is done using the *Security* \> *OAuth* \> *Clients* section at your subaccount level in the SAP BTP cockpit.

    See [Register an OAuth Client](register-an-oauth-client-61d8095.md).

    > ### Note:  
    > After you change the token validity to a supported value, you cannot restore the unlimited validity configuration.


