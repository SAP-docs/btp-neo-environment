<!-- loiod88900ba9dd848fc95d875a3056109a7 -->

# Create a Multitenant Connectivity Application



## Prerequisites

-   You have downloaded and set up your Eclipse IDE, SAP BTP Tools for Java and SAP BTP SDK for Neo environment. For more information, see [Setting Up the Development Environment](setting-up-the-development-environment-e815ca4.md).
-   You are an application provider. For more information, see [Multitenancy Roles](multitenancy-roles-48b552f.md).



## Context

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**

> ### Note:  
> The Java tools for Eclipse used in this page are no longer available. We are in the process of updating the content accordingly.

This tutorial explains how you can create a sample application which is based on the multitenancy concept, makes use of the connectivity service, and can be later consumed by other users. That means, you can enable your application to be consumed by users, members of a tenant which is subscribed for this application in a multitenant flavor. The output of the application you are about to create, displays a welcome page showing the URI of the tenant-specific destination configuration. This means that the administrator of the consumer subaccount may have been previously set a tenant-specific configuration for this application. However, in case such configuration has not been set, the application would use the default one, set by the administrator of the provider subaccount.

The application code is the same as for a standard `HelloWorld` consuming the connectivity service as the latter manages the multitenancy with no additional actions required by you. The users of the consumer subaccount, which is subscribed to this application, can access the application using a tenant-specific URL. This would lead the application to use a tenant-specific destination configuration. For more information, see [Multitenancy in the Connectivity Service](https://help.sap.com/viewer/b865ed651e414196b39f8922db2122c7/Cloud/en-US/b92140a0c6b942e1a0f72e9fd1133fd9.html "Using multitenancy for applications that require a connection to a remote service or on-premise application.") :arrow_upper_right:.

> ### Note:  
> As a provider, you can set your destination configuration on **application** and **subaccount** level. They are the default destination configurations in case a consumer has not configured tenant-specific destination configuration \(on subscription level\).

 <a name="concept_fg2_nmy_xl"/>

<!-- concept\_fg2\_nmy\_xl -->

## Procedure



<a name="concept_fg2_nmy_xl__section_02D65FD5DB1740B28F2E46E4CCEA71C7"/>

## 1. Create a dynamic Web project

1.  Open the *Java EE* perspective of the Eclipse IDE.
2.  In the *Project Explorer* view, from the context menu, choose *New* \> *Dynamic Web Project*.
3.  Enter `MultitenantConnectivity` as the *Project name*.
4.  In the *Target Runtime* pane, select the runtime you want to use to deploy the application. In this tutorial, we choose `Java Web`.
5.  In the *Configuration* pane, leave the default configuration.
6.  Choose *Finish* to finalize the creation of your project.



## 2. Add resource declaration in file "Web deployment descriptor"

1.  Go to `/MultitenantConnectivity/WebContent/WEB-INF` and open the *web.xml* file.
2.  Choose the *Source* tab page.
3.  Add the following code block to the `<web-app>` element:

    ```
    
    <resource-ref>
    	<res-ref-name>search_engine_destination</res-ref-name>
    	<res-type>com.sap.core.connectivity.api.http.HttpDestination</res-type>
    </resource-ref>
    
    ```




## 3. Create a sample JSP file

1.  Under the *MultitenantConnectivity* project node, choose *New* \> *JSP File* in the context menu.
2.  Enter `index.jsp` as the *File* name and choose *Finish*.
3.  Open the *index.jsp* file using the text editor.
4.  Replace the entire JSP file content with the following sample code:

    ```
    
    <%@page
    	import="javax.naming.InitialContext,javax.naming.Context,com.sap.core.connectivity.api.http.HttpDestination,java.util.Arrays"%>
    <%@ page language="java" contentType="text/html; charset=ISO-8859-1"
    	pageEncoding="ISO-8859-1"%>
    <!DOCTYPE html PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN" "http://www.w3.org/TR/html4/loose.dtd">
    <html>
    <head>
    <meta http-equiv="Content-Type" content="text/html; charset=ISO-8859-1">
    <title>SAP BTP - Multitenant Connectivity Demo Application</title>
    </head>
    
    <body>
    	<h2>Welcome to SAP BTP - multitenant connectivity demo application</h2>
    	<br></br>
    
    	<%
    		try {
    			Context context = (Context) new InitialContext()
    					.lookup("java:comp/env");
    
    			// In this case you don't need to explicitly use the TenantContext API
    			// because the Connectivity service handles the tenancy by itself.
    			// The retrieved HttpDestination object will be tenant-specific.
    			String destinationName = "search_engine_destination";
    			HttpDestination destination = (HttpDestination) context
    					.lookup(destinationName);
    			out.println("<p><font size=\"5\"> Retreived destination with name <i>"
    					+ destination.getName()
    					+ "</i> and URI <b>"
    					+ destination.getURI() + "</b></font></p>");
    		} catch (Exception e) {
    			out.println("<b>An exception has been thrown: <i>" + e.getMessage()
    					+ "</i></b>");
    			out.println(Arrays.toString(e.getStackTrace()));
    		}
    	%>
    
    </body>
    </html>
    
    ```

5.  Save the JSP file.

    The project compiles without errors.


You have successfully created a Web application containing a sample JSP file and consuming the connectivity service via looking up a destination configuration.



## 4. Deploy the application

To learn how to deploy your application, see [Deploying and Updating Java Applications](deploying-and-updating-java-applications-e5dfbc6.md).



## 5. Define the destination configurations

You, as application provider, can configure a default destination, which is then used at runtime when the application is requested in the context of the provider subaccount. In this case, the URL used to access the application is not tenant-specific.

**Example:**

```ini

Name=search_engine_destination
URL=https://www.google.com
Type=HTTP
ProxyType=Internet
Authentication=NoAuthentication
TrustAll=true

```

For more information on how to define a destination for provider subaccount, see:

 [Configure Destinations from the Console Client](https://help.sap.com/viewer/b865ed651e414196b39f8922db2122c7/Cloud/en-US/e51558bbbb571014bfc89325eaf075c0.html "") :arrow_upper_right:.

[Configure Destinations from the Cockpit](https://help.sap.com/viewer/b865ed651e414196b39f8922db2122c7/Cloud/en-US/60735ad11d8a488c83537cdcfb257135.html "") :arrow_upper_right:



## Result

You have created a sample application which can be requested in a browser. Its output depends on the tenant name.



## Next Steps

-   To test the access to your multitenant application, go to a browser and request it on behalf of your subaccount. Use the following URL pattern: `https://<application_name><provider_subaccount>.<host>/<application_path>`
-   If you want to test the access to your multitenant application on behalf of a consumer subaccount, follow the steps in page: [Consume a Multitenant Connectivity Application](consume-a-multitenant-connectivity-application-d2886a5.md)

**Related Information**  


[Upload Destinations](https://help.sap.com/viewer/b865ed651e414196b39f8922db2122c7/Cloud/en-US/7bd8fcd7e74c467c811144505e0280fb.html "") :arrow_upper_right:



[Developing Multitenant Applications in the Neo Environment](developing-multitenant-applications-in-the-neo-environment-54a7615.md "In the Neo environment of SAP BTP, you can develop and run multitenant (tenant-aware) applications. These applications run on a shared compute unit that can be used by multiple consumers (tenants). Each consumer accesses the application through a dedicated URL.")

