<!-- loio85a19f0ef154441c8b077cc8e0901109 -->

# Authorizations

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/docs/btp/sap-business-technology-platform/sap-business-technology-platform?version=Cloud) .**

Use the `isUserInRole` method of the servlet request \(`javax.servlet.HttpServletRequest`\) to manage authorizations for users. The following example returns a 403 error if the user accessing this servlet does not have role Developer:

```
protected void doGet(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
    PrintWriter out = response.getWriter();
				
    if(!request.isUserInRole("Developer")){
      response.sendError(403, "Logged in user does not have role Developer");
      return;
    } else {
      out.println("Hello developer");
    }
  }

```



## Next Steps

You can now test the application locally. For more information, see [Test Security Locally](test-security-locally-fe47e02.md).

After testing, you can proceed with deploying the application to SAP BTP. For more information, see [Deploying and Updating Java Applications](../30-development-neo/deploying-and-updating-java-applications-e5dfbc6.md).

After deploying on SAP BTP, you need to configure the role assignments users and groups will have for this application. For more information, see [Managing Roles](managing-roles-db8175b.md).

