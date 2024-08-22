<!-- loio929294823bc44614ba2034662f043793 -->

# Create and Configure the HTTP Destination

Use this procedure to configure the HTTP destination in the SAP BTP subaccount required to create an HTTP client for the OData API.



## Prerequisites

-   You have configured the OAuth client for OData access. For more information, see [Configure the OAuth Client for OData Access](configure-the-oauth-client-for-odata-access-0ac0dc9.md).

-   You have logged into the SAP BTP cockpit from the SAP BTP landing page for your subaccount.



## Context

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of the following technology portfolios: application development; process automation; integration; data, analytics, and enterprise planning; artificial intelligence. The platform offers users the ability to turn data into business value, compose end-to-end business processes, connect entire IT landscapes, and personalize, build and extend SAP applications. This reduces the overall total cost of ownership maintaining SAP landscapes and third-party software across end-to-end business processes.") :arrow_upper_right:.**

You create and configure the destinations on subaccount or application level in the SAP BTP cockpit.

Depending on your scenario, you use either OAuth or basic authentication for accessing the SAP Cloud for Customer system and the extension applications. If your scenario requires the SAP Cloud for Customer system and the extension applications to support Single Sign-On, you create and configure an HTTP destination with OAuth authentication. Otherwise, you can use an HTTP destination with basic authentication.



## Procedure

1.  In the cockpit, navigate to your subaccount.

2.  Choose *Connectivity* \> *Destinations* in the navigation panel.

3.  Depending on your scenario, create an HTTP destination as follows:

    -   To enable the support of SSO, create an *OAuth2SAMLBearerAssertion* HTTP destination and configure its settings as follows:
        1.  Configure the basic settings:


            <table>
            <tr>
            <th valign="top">

            Parameter
            
            </th>
            <th valign="top">

            Value
            
            </th>
            </tr>
            <tr>
            <td valign="top">
            
            `Name`
            
            </td>
            <td valign="top">
            
            Enter a meaningful name.
            
            </td>
            </tr>
            <tr>
            <td valign="top">
            
            `Type`
            
            </td>
            <td valign="top">
            
            `HTTP`
            
            </td>
            </tr>
            <tr>
            <td valign="top">
            
            `Description`
            
            </td>
            <td valign="top">
            
            \(Optional\) Enter a meaningful description.
            
            </td>
            </tr>
            <tr>
            <td valign="top">
            
            `URL`
            
            </td>
            <td valign="top">
            
            <code>https://<i class="varname">&lt;my_SAP_Cloud_for_Customer_system_name&gt;</i>.crm.ondemand.com/sap/c4c/odata/v1/c4codata</code>
            
            </td>
            </tr>
            <tr>
            <td valign="top">
            
            `Proxy Type`
            
            </td>
            <td valign="top">
            
            `Internet`
            
            </td>
            </tr>
            <tr>
            <td valign="top">
            
            `Authentication`
            
            </td>
            <td valign="top">
            
            `OAuth2SAMLBearerAssertion`
            
            </td>
            </tr>
            <tr>
            <td valign="top">
            
            `Audience`
            
            </td>
            <td valign="top">
            
            Take this value from the *Local Service Provider* field in *Configure Single Sign-On* under *General Settings* in SAP Cloud for Customer administration view.
            
            </td>
            </tr>
            <tr>
            <td valign="top">
            
            `Client Key`
            
            </td>
            <td valign="top">
            
            Client ID

            Paste the entry you have copied from the *Client ID* field when configuring the OAuth client. For more information, see [Configure the OAuth Client for OData Access](configure-the-oauth-client-for-odata-access-0ac0dc9.md).
            
            </td>
            </tr>
            <tr>
            <td valign="top">
            
            `Token Service URL`
            
            </td>
            <td valign="top">
            
            <code>https://<i class="varname">&lt;my_SAP_Cloud_for_Customer_system_name&gt;</i>.crm.ondemand.com/sap/bc/sec/oauth2/token</code>
            
            </td>
            </tr>
            <tr>
            <td valign="top">
            
            `Token Service User`
            
            </td>
            <td valign="top">
            
            Client ID

            Paste the entry you have copied from the *Client ID* field when configuring the OAuth client. For more information, see [Configure the OAuth Client for OData Access](configure-the-oauth-client-for-odata-access-0ac0dc9.md).
            
            </td>
            </tr>
            <tr>
            <td valign="top">
            
            `Token Service Password`
            
            </td>
            <td valign="top">
            
            Client secret

            Paste the entry you have copied from the *Client Secret* field when configuring the OAuth client. For more information, see [Configure the OAuth Client for OData Access](configure-the-oauth-client-for-odata-access-0ac0dc9.md).
            
            </td>
            </tr>
            </table>
            
        2.  Configure the required additional properties. To do so, in the *Additional Properties* panel, choose *New Property*, and enter the following properties:


            <table>
            <tr>
            <th valign="top">

            Parameter
            
            </th>
            <th valign="top">

            Value
            
            </th>
            </tr>
            <tr>
            <td valign="top">
            
            `authnContextClassRef`
            
            </td>
            <td valign="top">
            
            `urn:none` 
            
            </td>
            </tr>
            <tr>
            <td valign="top">
            
            `nameIdFormat`
            
            </td>
            <td valign="top">
            
            `urn:oasis:names:tc:SAML:1.1:nameid-format:emailAddress` 
            
            </td>
            </tr>
            <tr>
            <td valign="top">
            
            `scope`
            
            </td>
            <td valign="top">
            
            Scope ID entries separated by space.

            We recommend that you use `UIWC:CC_HOME`.
            
            </td>
            </tr>
            <tr>
            <td valign="top">
            
            `userIdSource`
            
            </td>
            <td valign="top">
            
            email
            
            </td>
            </tr>
            </table>
            
        3.  Select the *Use default JDK truststore* checkbox.

    -   To use basic authentication, create a *Basic Authentication* HTTP destination and configure its settings as follows:


        <table>
        <tr>
        <th valign="top">

        Parameter
        
        </th>
        <th valign="top">

        Value
        
        </th>
        </tr>
        <tr>
        <td valign="top">
        
        `Name`
        
        </td>
        <td valign="top">
        
        Enter a meaningful name
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        `Type`
        
        </td>
        <td valign="top">
        
        `HTTP`
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        `Description` 
        
        </td>
        <td valign="top">
        
        \(Optional\) Enter a meaningful description
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        `URL`
        
        </td>
        <td valign="top">
        
        <code>https://<i class="varname">&lt;my_SAP_Cloud_for_Customer_system_name&gt;</i>.crm.ondemand.com/sap/c4c/odata/v1/c4codata</code>
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        `Proxy Type`
        
        </td>
        <td valign="top">
        
        `Internet`
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        `Authentication`
        
        </td>
        <td valign="top">
        
        `BasicAuthentication`
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        `User`
        
        </td>
        <td valign="top">
        
        Enter the name of the SAP Cloud for Customer user who should have access to the extension applications. This user will be used as a technical user.
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        `Password`
        
        </td>
        <td valign="top">
        
        Enter the password of the SAP Cloud for Customer user who should have access to the extension applications.
        
        </td>
        </tr>
        </table>
        

4.  Save your entries.




## Results

It takes some time for the system to activate the destination.

**Related Information**  


[Create Destinations](https://help.sap.com/viewer/cca91383641e40ffbe03bdc78f00f681/Cloud/en-US/1e110da0ddd8453aaf5aed2485d84f25.html)

