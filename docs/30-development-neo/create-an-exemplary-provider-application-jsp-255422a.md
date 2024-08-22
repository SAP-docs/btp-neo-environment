<!-- loio255422aab2c4459e837d8c22d11b4a54 -->

# Create an Exemplary Provider Application \(JSP\)

This tutorial explains how to create a sample application which makes use of the multitenancy concept. That is, you can enable your application to be consumed by users, members of a tenant which is subscribed to this application in a multitenant flavor.



## Prerequisites

-   You have downloaded and set up your Eclipse IDE, SAP HANA Cloud Tools for Java and SAP HANA SDK. For more information, see [Setting Up the Development Environment](setting-up-the-development-environment-e815ca4.md).
-   You are an application provider. For more information, see [Multitenancy Roles](multitenancy-roles-48b552f.md).



## Context

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of the following technology portfolios: application development; process automation; integration; data, analytics, and enterprise planning; artificial intelligence. The platform offers users the ability to turn data into business value, compose end-to-end business processes, connect entire IT landscapes, and personalize, build and extend SAP applications. This reduces the overall total cost of ownership maintaining SAP landscapes and third-party software across end-to-end business processes.") :arrow_upper_right:.**

> ### Note:  
> The Java tools for Eclipse used in this page are no longer available. We are in the process of updating the content accordingly.

<a name="concept_fg2_nmy_xl"/>

<!-- concept\_fg2\_nmy\_xl -->

## Procedure



<a name="concept_fg2_nmy_xl__section_02D65FD5DB1740B28F2E46E4CCEA71C7"/>

## 1. Create a dynamic Web project

1.  Open the *Java EE* perspective of the Eclipse IDE.
2.  In the *Project Explorer* view, from the context menu, choose *New* \> *Dynamic Web Project*.
3.  Enter `TenantContextApp` as the *Project name*.
4.  In the *Target Runtime* pane, select the runtime you want to use to deploy the application. In this tutorial, we choose `Java Web`.
5.  In the *Configuration* pane, leave the default configuration.
6.  Choose *Finish* to finalize the creation of your project.





## 2. Add resource declaration in the Web deployment descriptor

1.  Go to `/TenantContextApp/WebContent/WEB-INF` and open the *web.xml* file.
2.  Choose the *Source* tab page.
3.  Add the following code block to the `<web-app>` element:

    ```
    
    <resource-ref>
    	<res-ref-name>TenantContext</res-ref-name>
    	<res-type>com.sap.cloud.account.TenantContext</res-type>
    </resource-ref>
    
    ```




## 3. Create a sample JSP

1.  Under the *TenantContextApp* project node, choose *New* \> *JSP File* in the context menu.
2.  Enter `index.jsp` as the *File* name and choose *Finish*.
3.  Open the *index.jsp* file using the text editor.
4.  Replace the entire JSP file content with the following sample code:

    ```
    
    <%@page import="javax.naming.InitialContext,javax.naming.Context,com.sap.cloud.account.TenantContext" %>
    <%@ page language="java" contentType="text/html; charset=ISO-8859-1"
        pageEncoding="ISO-8859-1"%>
    <!DOCTYPE html PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN" "http://www.w3.org/TR/html4/loose.dtd">
    <html>
    <head>
    <meta http-equiv="Content-Type" content="text/html; charset=ISO-8859-1">
    <title>SAP BTP - Tenant Context Demo Application</title>
    </head>
    
    <body>
    <h2> Welcome to the SAP BTP Tenant Context demo application</h2>
    <br></br>
    
    	<%
    		try {
    			InitialContext ctx = new InitialContext();
    			Context envCtx = (Context) ctx.lookup("java:comp/env");
    			TenantContext tenantContext = (TenantContext) envCtx
    					.lookup("TenantContext");
    			String currentTenantId = tenantContext.getTenant().getId();
    			out.println("<p><font size=\"5\"> The application was accessed on behalf of a tenant with an ID: <b>"
    					+ currentTenantId + "</b></font></p>");
    		} catch (Exception e) {
    			out.println("error at client");
    		}
    	%>
    
    </body>
    </html>
    
    ```

5.  Save the Java editor. The project compiles without errors.



## 4. Deploy the application

To learn how to deploy your application, see [Deploying and Updating Java Applications](deploying-and-updating-java-applications-e5dfbc6.md).



## Result

You have successfully created a Web application containing a JSP file and tenant context functionality.



## Next Steps

-   To test the access to your multitenant application, go to a browser and request it on behalf of your subaccount. Use the following URL pattern: `https://<application_name><provider_subaccount>.<host>/<application_path>`
-   If you want to test the access to your multitenant application on behalf of a consumer subaccount, follow the steps in page: [Consume a Multitenant Connectivity Application](consume-a-multitenant-connectivity-application-d2886a5.md)



## Related Information

[Developing Java Applications](developing-java-applications-ac36e1f.md)

[Developing Multitenant Applications in the Neo Environment](developing-multitenant-applications-in-the-neo-environment-54a7615.md)

