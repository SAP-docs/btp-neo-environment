<!-- copy51ec990e1d6e42468eafb733a503c92b -->

# Create SAP User Accounts

To grant authorizations to people from the default identity provider in your subaccount, ensure that they have a user account.



## Context

If the person in question already has a user account on `sap.com` websites, then they already have a user in the default identity provider. You can already add this user to your accounts, if you know this person's e-mail address.

Consider using a custom identity provider to integrate your own identity and access management solution.

> ### Note:  
> For technical users, create the user in your custom identity provider.



## Procedure

Send your colleagues the self-registration URL.

`https://account.sap.com/core/create/register?redirectURL=https%3A%2F%2Femea.cockpit.btp.cloud.sap%2Fcockpit%2F`

The website registers you with SAP Universal ID, which also registers you with SAP ID service. If you already have a user in SAP ID service, you have the option to associate this user with your new SAP Universal ID account. SAP Universal ID manages the users of official SAP sites, including the SAP developer and partner community.

> ### Tip:  
> If you already know the e-mail addresses of your colleagues, you can add them to your subaccount and assign role collections. After registering, your colleagues have the option to return to the SAP BTP cockpit. If you have already assigned authorizations to that user, then your colleagues have access when they log on.



<a name="copy51ec990e1d6e42468eafb733a503c92b__result_yzf_ccq_p5b"/>

## Results

**Related Information**  


[Add Users from SAP ID Service for Multi-Environment Subaccounts](https://help.sap.com/viewer/ae8e8427ecdf407790d96dad93b5f723/Cloud/en-US/760ab77e5afd4c15ae70ec7ff59e02ef.html "Before you can assign role collection to a user from SAP ID service, ensure that this user exists in your subaccount.") :arrow_upper_right:

[Default Identity Provider](https://help.sap.com/viewer/ae8e8427ecdf407790d96dad93b5f723/Cloud/en-US/d6a8db70bdde459f92f2837349f95090.html "SAP ID service is the default identity provider for both platform users and business users (in applications) at SAP BTP. You can start using it without further configuration.") :arrow_upper_right:

[Trust and Federation with Identity Providers](https://help.sap.com/viewer/ae8e8427ecdf407790d96dad93b5f723/Cloud/en-US/cb1bc8f1bd5c482e891063960d7acd78.html "When setting up accounts you need to assign users. While we provide you with your first users to get you started, your organization has identity providers that you want to integrate.") :arrow_upper_right:

