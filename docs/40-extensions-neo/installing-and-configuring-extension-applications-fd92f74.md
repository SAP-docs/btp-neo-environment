<!-- loiofd92f749a9374f9190d716171f9bfd42 -->

# Installing and Configuring Extension Applications

As an implementation partner, you install and configure the extension applications that you want to make available for customers.

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**

You deploy your extension application, configure its connectivity to the SAP SuccessFactors system and map the roles defined in your extension application to the roles in the corresponding SAP SuccessFactors system.



## Prerequisites

-   You have an SAP BTP extension subaccount and the corresponding SAP SuccessFactors customer instance connected to it. For more information about extension subaccounts, see [Extensions](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/08b1effc53634890a525f945017e2edc.html).
-   You are either an administrator of the SAP BTP subaccount or have а platform role with the following platform scopes defined for it:
    -   manageExtensionConfigurations

    -   readExtensionConfigurations

    -   readJavaApplications

    -   readSubscriptions

    -   readAccount

    -   manageDestintaions

    -   readDestinations

    -   readJavaApplications

    -   readHTML5Applications

    -   manageApplicationRoleProvider

    -   readSubscriptionConfiguration


-   You have downloaded and set up the console client for SAP BTP, Neo environment. For more information, see [Console Client for the Neo Environment](../50-administration-and-ops-neo/console-client-for-the-neo-environment-7613230.md).




## Process Flow

You deploy your extension application in your SAP BTP extension. Then you need to configure the application connectivity to SAP SuccessFactors and to enable the use of the HXM Suite OData API. To ensure that only approved applications are using the SAP SuccessFactors identity provider for authentication, you need to register the extension application as an authorized assertion consumer service in SAP SuccessFactors. Then you register the extension application home page tiles and import the extension application roles in the SAP SuccessFactors customer instance connected to the extension subaccount.

To finalize the configuration on SAP BTP side, you change the default role provider to the SAP SuccessFactors one. To finalize the configuration on SAP SuccessFactors side, you assign user groups to the permission roles defined for your extension application.

> ### Note:  
> In the Neo environment, you can alternatively deploy your extension application as a solution. You can package all artifacts that are needed for your extension solution – Java applications, HTML5 application, database bindings, destinations, even SAP SuccessFactors roles and home page tiles into a Multi-Target Application \(MTA\) archive that includes a deployment descriptor file, and then deploy the MTA archive in your account. See:
> 
> -   [Multitarget Applications for the Neo Environment](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/e1bb7eb746d34237b8b47035adff5022.html)
> 
> -   [Modeling SAP SuccessFactors Extensions](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/ec3579359e86435cb343a7874e01acd8.html)


<table>
<tr>
<th valign="top">

Task



</th>
<th valign="top">

Description



</th>
</tr>
<tr>
<td valign="top">

1. [Register the Extension Application as an Authorized Assertion Consumer Service](register-the-extension-application-as-an-authorized-assertion-consumer-service-47c4bff.md)



</td>
<td valign="top">

Register the extension application as an authorized assertion consumer service.



</td>
</tr>
<tr>
<td valign="top">

2. [Configure the Extension Application's Connectivity to SAP SuccessFactors](configure-the-extension-application-s-connectivity-to-sap-successfactors-ebb281b.md)



</td>
<td valign="top">

Configure the connectivity between your Java extension application and the SAP SuccessFactors system associated with your SAP BTP extension subaccount.



</td>
</tr>
<tr>
<td valign="top">

3. [Register a Home Page Tile for the Extension Application](register-a-home-page-tile-for-the-extension-application-6648ccf.md)



</td>
<td valign="top">

Register a home page tile for the extension application in the extended SAP SuccessFactors system



</td>
</tr>
<tr>
<td valign="top">

4. [Create the Resource File with Role Definitions](create-the-resource-file-with-role-definitions-93d5ce5.md)



</td>
<td valign="top">

Create the resource file containing the SAP SuccessFactors HXM role definitions.



</td>
</tr>
<tr>
<td valign="top">

5. [Import the Extension Application Roles in the SAP SuccessFactors System](import-the-extension-application-roles-in-the-sap-successfactors-system-f0ed89f.md)



</td>
<td valign="top">

Import the application-specific roles from the SAP BTP system repository into to the SAP SuccessFactors customer instance connected to your extension subaccount.



</td>
</tr>
<tr>
<td valign="top">

6. [Assign the Extension Application Roles to Users](assign-the-extension-application-roles-to-users-d838fff.md)



</td>
<td valign="top">

Assign the extension application roles you have imported in the SAP SuccessFactors systems to the user to whom you want to grant access to your application.



</td>
</tr>
<tr>
<td valign="top">

7. [Configure the SAP SuccessFactors Role Provider](configure-the-sap-successfactors-role-provider-22bda07.md)



</td>
<td valign="top">

Change the default SAP BTP role provider of your Java application to the SAP SuccessFactors role provider.

> ### Note:  
> This task is relevant for Java extension applications only.



</td>
</tr>
<tr>
<td valign="top">

8. [Test the Role Assignments](test-the-role-assignments-00f238b.md)



</td>
<td valign="top">

Try to access the application with the users with different level of granted access to test the role assignments.



</td>
</tr>
</table>

