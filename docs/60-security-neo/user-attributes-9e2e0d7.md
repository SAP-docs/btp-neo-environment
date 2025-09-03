<!-- loio9e2e0d7e91cc44e79901a756bf7b2d88 -->

# User Attributes

You can access user attributes using the User Management Java API \(`com.sap.security.um.user`\). It can be used to get and create users or to read and update their information.

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/docs/btp/sap-business-technology-platform/sap-business-technology-platform?version=Cloud) .**

To access user information, you need to get to `com.sap.security.um.user.UserProvider`.

To get `UserProvider`, first, declare a resource reference in the *web.xml*. For example:

```
<resource-ref>
    <res-ref-name>user/Provider</res-ref-name>
    <res-type>com.sap.security.um.user.UserProvider</res-type>
</resource-ref>
```

Then look up `UserProvider` via JNDI in the source code of your application. For example:

```

InitialContext ctx = new InitialContext();
UserProvider userProvider = (UserProvider) ctx.lookup("java:comp/env/user/Provider");
User user = null;
if (request.getUserPrincipal() != null) {
     user = userProvider.getUser(request.getUserPrincipal().getName());
}
```

> ### Note:  
> If you are using the SDK for Java EE 6 Web Profile, you can look up `UserProvider` via annotation \(instead of embedding JNDI lookup in the code\). For example:
> 
> ```
> @Resource
> private UserProvider userProvider;
> 
> try {
>   // Read the currently logged in user from the user storage
>   return userProvider.getUser(request.getRemoteUser());
> } catch (PersistenceException e) {
>   throw new ServletException(e);
> }
> 
> 
> ```

Alternatively, you can access `UserProvider` using `com.sap.security.um.user.UserManagementAccessor`. For example:

```
import com.sap.security.um.user.User;
import com.sap.security.um.user.UserProvider;
import com.sap.security.um.service.UserManagementAccessor;

...

// Check for a logged in user
if (request.getUserPrincipal() != null) {
  try {
    // UserProvider provides access to the user storage
    UserProvider users = UserManagementAccessor.getUserProvider();

    // Read the currently logged in user from the user storage
    User user = users.getUser(request.getUserPrincipal().getName());

    // Print the user name and email
    response.getWriter().println("User name: " + user.getAttribute("firstname") + " " + user.getAttribute("lastname"));
    response.getWriter().println("Email: " + user.getAttribute("email"));
    
    response.getWriter().println("Assigned groups: " + Arrays.toString(user.getAttributeValues("groups"))); 
    
  } catch (Exception e) {
    // Handle errors
  }
}
```

In the source code above, the `user.getAttribute` method is used for single-value attributes \(the first name and last name of the user\). For attributes that we expect to have more than one value \(such as the assigned groups\), we use `user.getAttributeValues` method.



## Next Steps

You can now test the application locally. For more information, see [Test Security Locally](test-security-locally-fe47e02.md).

After testing, you can proceed with deploying the application to SAP BTP. For more information, see [Deploying and Updating Java Applications](../30-development-neo/deploying-and-updating-java-applications-e5dfbc6.md).

