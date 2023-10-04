<!-- loioe48e486f70d543e399db40354fdc2ac3 -->

# Log in with a Custom Identity Provider



## Context

If trust is configured between your global account and a custom identity provider, you need to use the `--idp` parameter to log in through this identity provider. As value, you provide its tenant ID. You find the correct value in the cockpit under *Security* → *Trust Configuration* → *Custom Platform Identity Providers* in the *btp CLI* column.

> ### Note:  
> To work with users from a custom identity provider, you need to specify the `--of-idp` parameter by providing the origin key of the custom identity provider. This is applicable to the following commands: `btp list security/user`, `btp get security/user`, `btp delete security/user`, `btp assign security/role-collection`, `btp unassign security/role-collection`, and you find this origin key in the cockpit under *Security*.

To learn how to configure trust to a custom identity provider, see [Establish Trust and Federation of Custom Identity Providers for Platform Users \[Feature Set B\]](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/c36898473d704e07a33268c9f9d29515.html "You want to use a custom identity provider for the platform users of SAP BTP in different environments and at the different account levels: global account, directory, and subaccount. By default, platform users in multi-environment subaccounts are users in the default identity provider.") :arrow_upper_right: or the command help of [btp create security/trust](https://help.sap.com/docs/BTP/btp-cli/btp-create-security-trust.html).

> ### Restriction:  
> If you work with a custom identity provider for platform users in Feature Set B, keep in mind that each user is allowed a maximum of 10 parallel sessions per identity provider. This number takes into account all tools, including the cockpit and CLIs.
> 
> For more information, see [Restrictions When Using Custom Identity Providers for Platform Users \[Feature Set B\]](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6f0a623807b541a0aef41f3d65c7a0fa.html "The following is a list of restrictions that apply to the use of custom identity providers with platform users in Feature Set B.") :arrow_upper_right:.



## Procedure

1.  To make use of single sign-on, log in with:

    ```
    btp login --sso --idp <TENANT>
    ```

2.  To provide user and password on the command line, log in with:

    ```
    btp login --idp <TENANT>
    ```

    You will be promped for all required login information.


**Related Information**  


[Establish Trust and Federation of Custom Identity Providers for Platform Users \[Feature Set B\]](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/c36898473d704e07a33268c9f9d29515.html "You want to use a custom identity provider for the platform users of SAP BTP in different environments and at the different account levels: global account, directory, and subaccount. By default, platform users in multi-environment subaccounts are users in the default identity provider.") :arrow_upper_right:

[Trust and Federation with Identity Providers](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/cb1bc8f1bd5c482e891063960d7acd78.html "When setting up accounts you need to assign users. While we provide you with your first users to get you started, your organization has identity providers that you want to integrate.") :arrow_upper_right:

[Log in](log-in-e241b30.md "Log in with the btp CLI is on global account level.")

