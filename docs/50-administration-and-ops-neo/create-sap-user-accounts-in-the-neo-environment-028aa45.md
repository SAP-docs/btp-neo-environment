<!-- loio028aa45866734f988bb229ca73ac5370 -->

# Create SAP User Accounts in the Neo Environment

To grant authorizations to people from the default identity provider in your subaccount, ensure that they have a user account.



## Context

If the person in question already has a user account on `sap.com` Web sites, then that person already has a user in the default identity provider. Add this user to your accounts, if you know this person's e-mail address.

Consider using a custom identity provider to integrate your own identity and access management solution.

> ### Note:  
> For technical users, create the user in your custom identity provider. In your custom identity provider, you control the access policies of these users independently from the policies we set for the default identity provider. Our default identity provider is meant for **human** users, who interact with SAP and our solutions.



## Procedure

Send your colleagues the self-registration URL.

`https://account.sap.com/core/create/register?redirectURL=https%3A%2F%2Femea.cockpit.btp.cloud.sap%2Fcockpit%2F`

The Web site registers you with SAP Universal ID, which also registers you with the SAP ID service. If you already have a user in the SAP ID service, associate this user with your new SAP Universal ID account. SAP Universal ID manages the users of official SAP sites, including the SAP developer and partner community.

> ### Tip:  
> After your colleagues sign up, add them to a subaccount. Assign role collections to them. Then your colleagues can log on to the SAP BTP cockpit.

**Related Information**  


[Add Users from SAP ID Service for Multi-Environment Subaccounts](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/760ab77e5afd4c15ae70ec7ff59e02ef.html "Before you can assign role collection to a user from SAP ID service, ensure that this user exists in your subaccount.") :arrow_upper_right:

[Default Identity Provider](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/d6a8db70bdde459f92f2837349f95090.html "SAP ID service is the default identity provider for both platform users and business users (in applications) at SAP BTP. You can start using it without further configuration.") :arrow_upper_right:

[Trust and Federation with Identity Providers](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/cb1bc8f1bd5c482e891063960d7acd78.html "When setting up accounts you need to assign users. While we provide you with your first users from the default identity provider to get you started, your organization has identity providers that you want to integrate.") :arrow_upper_right:

