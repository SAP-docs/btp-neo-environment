<!-- loioc39c320d4f0e4104b6b171bdad79a984 -->

# Configuring Platform Identity Provider \[Feature Set A\]

Use the procedures below to configure an Identity Authentication tenant as platform identity provider in your Neo subaccount in Feature Set A.

<a name="task_ckk_3q5_q1b"/>

<!-- task\_ckk\_3q5\_q1b -->

## 1. Create Trust with the Identity Authentication Tenant



<a name="task_ckk_3q5_q1b__prereq_cml_b4x_kxb"/>

## Prerequisites

-   You have a user with Administrator role for your subaccount \(provided by the default user base, SAP ID Service\).

-   You have enabled the Platform Identity Provider service. See [Using Services in the Neo Environment](../30-development-neo/using-services-in-the-neo-environment-a32d3d5.md#loioa32d3d532e2d4dceaaca4ebab68df037).

-   You have an Identity Authentication tenant registered for the SAP customer user \(s-user\) who owns your global account \(see [Global Accounts](../10-concepts-neo/account-model-722a475.md#loio9b7d44f92eec44a6ae87129c02aeec0d)\).

-   The Identity Authentication tenant is configured. See [Identity Authentication documentation](https://help.sap.com/viewer/6d6d63354d1242d185ab4830fc04feb1/Cloud/en-US/d17a116432d24470930ebea41977a888.html).




<a name="task_ckk_3q5_q1b__steps_dml_b4x_kxb"/>

## Procedure

1.  Log in to the SAP BTP cockpit with the Administrator user from the default user base.

2.  Navigate to the required SAP BTP subaccount. See [Navigate in the Cockpit](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/0874895f1f78459f9517da55a11ffebd.html "Learn how to navigate to your global accounts and subaccounts in the SAP BTP cockpit.") :arrow_upper_right:.

3.  Go to the *Security* \> *Trust* section.

4.  Go to the *Platform Identity Provider* tab.

5.  Choose *Use Identity Authentication Tenant*.

6.  Choose the required tenant and save.

    ![](images/Register_an_SCI_Tenant_adb298c.png)

    ![](images/SCI_Tenants_Cockpit_38c80ed.png)

    The Identity Authentication tenant appears as a platform identity provider. The trust configuration with it is complete. You can proceed with adding tenant users as subaccount members, and the rest of the steps described in this document.


<a name="task_ccp_skb_r1b"/>

<!-- task\_ccp\_skb\_r1b -->

## 2. Add Identity Authentication Tenant Users as Subaccount Members



<a name="task_ccp_skb_r1b__context_dzl_glb_r1b"/>

## Context

Now that you have switched the user base, you need to add the users that you will use for access to this subaccount as subaccount members.

Go to the *Members* tab in the SAP BTP cockpit. You can see all cockpit users, with their IDs, roles and user base, listed here. To add a new member, choose *Add Members* and configure the member users from the respective user base \(Identity Authentication tenant\). See also [Add Members to Your Neo Subaccount](../50-administration-and-ops-neo/add-members-to-your-neo-subaccount-a253570.md).

> ### Note:  
> The account members for access to this subaccount from the console client must have Administrator role.

![](images/Add_Members_3c031c0.png)

<a name="task_xwz_klb_r1b"/>

<!-- task\_xwz\_klb\_r1b -->

## \(Optional\) 3. Configure the Identity Authentication Tenant for the Required Scenarios



<a name="task_xwz_klb_r1b__context_tsq_nlb_r1b"/>

## Context

You can configure the Identity Authentication tenant for specific authentication scenarios using its Administration Console UI.

To do so, choose the *Administration Console* button next to the registered tenant in the *Security* \> *Trust* \> *Platform Identity Provider* section of the SAP BTP cockpit.

In the tenant's Administration Console you will notice it displays the SAP BTP cockpit as a registered application. The application has `<Identity Authentication tenant ID>` as *display name*, and `https://account.hana.ondemand.com/<account name>/admin` as *SP name*.

Related information in the documentation of Identity Authentication:

-   [Corporate User Store](https://help.sap.com/viewer/6d6d63354d1242d185ab4830fc04feb1/Cloud/en-US/461d71c148594608b9c8b6d016e0a0c5.html#loio461d71c148594608b9c8b6d016e0a0c5)
-   [Configure Kerberos Authentication](https://help.sap.com/viewer/6d6d63354d1242d185ab4830fc04feb1/Cloud/en-US/b0301657df074ab081ab7556854aca56.html#loiob0301657df074ab081ab7556854aca56)
-   [User Management](https://help.sap.com/viewer/6d6d63354d1242d185ab4830fc04feb1/Cloud/en-US/228428f9f476449cafd841a68d75b234.html#loio228428f9f476449cafd841a68d75b234)
-   [Configure Risk-Based Authentication](https://help.sap.com/viewer/6d6d63354d1242d185ab4830fc04feb1/Cloud/en-US/bc52fbf3d59447bbb6aa22f80d8b6056.html#loiobc52fbf3d59447bbb6aa22f80d8b6056)
-   [Operation Guide](https://help.sap.com/viewer/6d6d63354d1242d185ab4830fc04feb1/Cloud/en-US/6a8e67cf98bf41968ea2849dfd0b6bbd.html)

<a name="task_eg5_wlb_r1b"/>

<!-- task\_eg5\_wlb\_r1b -->

## Accessing the SAP BTP Cockpit with the Tenant User Base



<a name="task_eg5_wlb_r1b__context_z1x_fmb_r1b"/>

## Context

If you open the default cockpit URL, <code>https://account.&lt;SAP BTP host&gt;/cockpit</code>, SAP ID Service will be used for user authentication.

To request the SAP BTP cockpit using the Identity Authentication tenant user base, use the following URL:

<code>https://account-&lt;subaccount-name&gt;.&lt;SAP BTP host&gt;</code>

For the SAP BTP host, see [Regions](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/350356d1dc314d3199dca15bd2ab9b0e.html "You can deploy applications in different regions. Each region represents a geographical location (for example, Europe, US East) where applications, data, or services are hosted.") :arrow_upper_right:.

> ### Tip:  
> Make sure you use the **subaccount name**, not the subaccount **display** name, which could be different. Check the value of the subaccount name in the subaccount overview section in the cloud cockpit.

> ### Note:  
> -   You can see only those subaccounts that are in the region of the tenant cockpit URL.
> 
> -   If you want to use risk-based authentication, for example, to enable two-factor authentication \(TFA\), you have to enable it for **all** subaccounts in your global account. This means for each subaccount you need to configure the platform identity provider to be an Identity Authentication tenant configured properly for risk-based authentication.
> 
>     For more information about TFA in your Identity Authentication tenant, see [Two-Factor Authentication](https://help.sap.com/viewer/6d6d63354d1242d185ab4830fc04feb1/Cloud/en-US/0d41cd49f6504f3eaf29b58d616b040f.html#loio0d41cd49f6504f3eaf29b58d616b040f).



<a name="task_eg5_wlb_r1b__steps_cjr_qhq_r1b"/>

## Procedure

1.  In an incognito browser window, open the tenant cockpit URL. This is required to make sure you are not logged in with the SAP ID Service user.

2.  Log in with a user name and password from the Identity Authentication tenant.


<a name="task_sm3_mmb_r1b"/>

<!-- task\_sm3\_mmb\_r1b -->

## Using the Console Client with the Tenant User Base



<a name="task_sm3_mmb_r1b__context_wt5_mmb_r1b"/>

## Context

When using the console client with a custom platform identity provider, you must supply a user from your custom Identity Authentication tenant. For example, you want to execute the `list-schemas` command. In the corresponding command parameter, you can provide the login id or email address of your user in the Identity Authentication tenant as follows:

```
neo list-schemas -a <name of the subaccount> -h <region host> -u <login id or email of the user>
```

If you have enabled two-factor authentication \(TFA\) in your Identity Authentication tenant, you can enter the 6-digit passcode after the user’s password when the console client prompts you for password.

For more information about two-factor authentication in your Identity Authentication tenant, see [Two-Factor Authentication](https://help.sap.com/viewer/6d6d63354d1242d185ab4830fc04feb1/Cloud/en-US/0d41cd49f6504f3eaf29b58d616b040f.html#loio0d41cd49f6504f3eaf29b58d616b040f).

> ### Tip:  
> If you want to switch back to the default user base of SAP ID Service in the console client, you need to remove the custom platform identity provider configuration you created.

