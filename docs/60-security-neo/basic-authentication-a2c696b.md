<!-- loioa2c696be81c14da189ccaeae9a2d687f -->

# Basic Authentication

In basic HTTP authentication method \("basic authentication" for short\), users log in using their user name/ID and password sent in HTTP header “Authorization”. SAP BTP checks in the specified user base if the supplied pair is valid.



## Context

For more inormation about basic authentication, see [RFC 7617 \(Section 2\)](https://datatracker.ietf.org/doc/html/rfc7617#section-2).

You can use it in system-to-system communication \(usually, using a destination, see [Managing Destinations](https://help.sap.com/docs/CP_CONNECTIVITY/b865ed651e414196b39f8922db2122c7/e4f1d97cbb571014a247d10f9f9a685d.html)\).

You may use basic authentication for specific scenarios of SAP BTP services, for example:

-   For securing SAP Cloud Integration iFlows
-   For securing APIs in SAP API Management
-   For building a proxy bridge in SAP Document Service for Neo Environment
-   For application authentication in SAP Mobile Services.

You can also use it in \(generic\) Java applications in the Neo environment.

> ### Note:  
> For Java applications, we recommend using a more secure authentication method, such as form or OAuth. For more information about the supported methods, see [Declarative Authentication](authentication-e637f62.md#loioe36c712efa844e8199a9c4bd681cb4e0).



### User Base

By default, SAP ID Service provides the user base for basic authentication. It consists of the SAP users \(s-users\). See [SAP ID Service](../50-administration-and-ops-neo/sap-id-service-d1e1e18.md).

Alternatively, you can use your Identity Authentication tenant that provides your custom private user base. See [Identity Authentication documentation](https://help.sap.com/docs/IDENTITY_AUTHENTICATION/6d6d63354d1242d185ab4830fc04feb1/d17a116432d24470930ebea41977a888.html).

 <a name="task_acb_fyd_15b"/>

<!-- task\_acb\_fyd\_15b -->

## Create and Deploy the Application



<a name="task_acb_fyd_15b__steps-unordered_rnd_gzd_15b"/>

## Procedure

-   If you are using basic authentication for specific scenarios of SAP BTP services, check the respective documentation for specific prerequisites and steps.

    Some use cases:

    -   [Configure Integration in SAP Cloud Integration](https://help.sap.com/docs/SAP_CLOUD_FOR_CUSTOMER/97f5b6f7272b4501b99c693e53bd8474/1933ca4727bf48cd95f200f0ea36b13f.html)
    -   [Basic Authentication \(in SAP API Management\)](https://help.sap.com/docs/SAP_CLOUD_PLATFORM_API_MANAGEMENT/66d066d903c2473f81ec33acfe2ccdb4/693c0d1720644d57918ed77acc6a95ef.html)
    -   [Application Authentication \(in SAP Mobile Services\)](https://help.sap.com/docs/SAP_MOBILE_SERVICES/33c4b62fdc174d89a47d4baee3ced08a/9995b0fa9b4e45709eb62ebe4071fc5d.html)
    -   [Build a Proxy Bridge \(in SAP Document Service for Neo Environment\)](https://help.sap.com/docs/DOCUMENT_SERVICE/b0cc1109d03c4dc299c215871eed8c42/ed1c6732d4214c68846ab9813b9df943.html)

-   If you are using a Java application:

    1.  Implement basic authentication declaratively or programmatically in the application \(see [Authentication](authentication-e637f62.md#loioe637f62abb571014857cb0232adc43a7)\).
    2.  Deploy the application \(see [Deploying and Updating Java Applications](../30-development-neo/deploying-and-updating-java-applications-e5dfbc6.md)\).
    3.  Optionally, configure authentication. See [Authentication Configuration](authentication-configuration-4a46723.md).


 <a name="task_rpl_gf2_15b"/>

<!-- task\_rpl\_gf2\_15b -->

## Configure the User Base



<a name="task_rpl_gf2_15b__prereq_uyh_jf2_15b"/>

## Prerequisites

-   \(If you want to use Identity Authentication instead of SAP ID Service\) You have at least one fully configured Identity Authentication tenant \(and containing the required users\). See [Initial Setup \(for Identity Authentication\)](https://help.sap.com/docs/IDENTITY_AUTHENTICATION/6d6d63354d1242d185ab4830fc04feb1/31af7da133874e199a7df1d42905241b.html).
-   You are logged in the SAP BTP cockpit with a user that has the platform role *Administrator* or a custom platform role with the following scopes: *manageBasicConfigurationSettings* and *readBasicConfigurationSettings*. See [Managing Member Authorizations in the Neo Environment](../50-administration-and-ops-neo/managing-member-authorizations-in-the-neo-environment-a1ab5c4.md)



<a name="task_rpl_gf2_15b__steps_dn2_f32_15b"/>

## Procedure

1.  In the SAP BTP Cockpit, navigate to your subaccount.

2.  Navigate to *Security* \> *Trust* \> *Basic Authentication*

    In the *Basic Authentication* section, you can configure the user base for basic authentication. By default, it is SAP ID Service. You can change it to an Identity Authentication tenant, and back to SAP ID Service.

3.  If you want to use an Identity Authentication tenant, choose the Use Identity Authentication tenant button, and select the required tenant from the list.

    > ### Tip:  
    > If you don’t see your tenant listed, create an incident in component BC-NEO-SEC-IAM. See [Getting Support, Neo Environment](../70-getting-support-neo/getting-support-neo-environment-fc2bf6a.md).

    You can switch back to SAP ID Service if required.


**Related Information**  


[Example: Configure Document Management for Workflow Capability Attachments](https://help.sap.com/docs/WORKFLOW/e157c391253b4ecd93647bf232d18a83/d99fd6a4d13e43bfbfc936a03ff65b32.html)

[Commmon Errors with Basic Authentication in SAP ID Service](commmon-errors-with-basic-authentication-in-sap-id-service-fa6645e.md "")

[Troubleshooting: Basic Authentication](https://ga.support.sap.com/dtp/viewer/index.html#/tree/2065/actions/26547:26548:33705:33706:33708)

