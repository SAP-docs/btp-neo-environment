<!-- loio2eebf764c3e34900b92a6ba3e4654ccd -->

# Logout

This topic describes how to enable users to log out from your applications.

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://launchpad.support.sap.com/#/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**



<a name="loio2eebf764c3e34900b92a6ba3e4654ccd__section_064B2CF9B6DB4765B6D88930DEAA904E"/>

## Context

You can provide a logout operation for your application by adding a logout button or logout link.

When logout is triggered in a SAP BTP application, the user is redirected to the identity provider to be logged out there, and is then returned to the original application URL that triggered the logout request.

The following code provides a sample servlet that handles logout operations. When `loginContext.logout()` is used, the system automatically redirects the logout request to the identity provider, and then returns the user to the logout servlet again.

```

import javax.security.auth.login.LoginContext;
import javax.security.auth.login.LoginException;
import com.sap.security.auth.login.LoginContextFactory;
...

public class LogoutServlet extends HttpServlet {
. . . 
  //Call logout if the user is logged in
  LoginContext loginContext = null;
  if (request.getRemoteUser() != null) { 

    try { 
      loginContext = LoginContextFactory.createLoginContext(); 
      loginContext.logout();
     
    } catch (LoginException e) { 
      // Servlet container handles the login exception
      // It throws it to the application for its information
      response.getWriter().println("Logout failed. Reason: " + e.getMessage()); 
    }
   } else {
    response.getWriter().println("You have successfully logged out."); 
   }
. . . 
}

```

We add a logout link to the HelloWorld servlet, which references this logout servlet:

```


      response.getWriter().println("<a href=\"LogoutServlet\">Logout</a>"); 


```



## \(Optional\) Protecting Logout from Cross-Site Request Forgery \(CSRF\)

CSRF is a common Web hacking attack. For more information, see [Cross-Site Request Forgery \(CSRF\)](https://www.owasp.org/index.php/Cross-Site_Request_Forgery_(CSRF)) \(non-SAP link\). You might consider protecting the logout operations for your applications from CSRF to prevent your users from potential CSRF attack related problems \(for example, XSRF denial of service on single logout\).

> ### Note:  
> Although SAP BTP provides ready-to-use support for CSRF filtering, with logout operations you cannot use it. The reason is users are sent to the logout servlet twice: first, when they trigger logout by clicking a button/link, and second, when the identity provider has logged them out and redirected them back to the application. You cannot specify the system to apply the CSRF filter first time, and skip it the second time.

The following example provides XSRF-protected logout.

> ### Source Code:  
> ```
> LoginContext loginContext = null;
>     if (request.getRemoteUser() != null) {
>       Object csrfTokenFromSession = request.getSession().getAttribute("csrf-logout");
>       String csrfTokenFromRequest = request.getParameter("csrf-logout");
>       if (request.getSession(false) != null && csrfTokenFromRequest != null && csrfTokenFromSession != null
>           && csrfTokenFromSession.toString().equals(csrfTokenFromRequest)) {
>         try {
>           loginContext = LoginContextFactory.createLoginContext();
>           loginContext.logout();
> 
>         } catch (LoginException e) {
>           // Servlet container handles the login exception
>           // It throws it to the application for its information
>           response.getWriter().println("Logout failed. Reason: " + e.getMessage());
>         }
>       } else {
>         response.sendError(403, "No valid csrf token found in request. No logout will be performed.");
>       }
>     } else {
>       response.getWriter().println("You have successfully logged out.");
>     }
> 
> ```

We add a logout link to the HelloWorld servlet, which references this logout servlet:

> ### Source Code:  
> ```
> try {
>          HttpSession session = request.getSession(false);
>          if(session != null){
>            long tokenValue = 0L;
>            if(session.getAttribute("csrf-logout") != null){
>              tokenValue = (Long) session.getAttribute("csrf-logout");
>            } else {
>              SecureRandom instance = java.security.SecureRandom.getInstance("SHA1PRNG");
>              instance.setSeed(instance.generateSeed(5));
>              tokenValue = instance.nextLong();
>              session.setAttribute("csrf-logout", tokenValue);
>            }
>         response.getWriter().println("<a href=\"LogoutServlet?csrf-logout="+tokenValue+"\">Logout</a>");
>       }
>     } catch (NoSuchAlgorithmException e) {
>       throw new ServletException(e);
>     }
> 
> ```



<a name="loio2eebf764c3e34900b92a6ba3e4654ccd__section_N1019F_N10013_N10001"/>

## Preventing Common Logout Problems

*Unprotect the Logout Servlet* 

For efficient logout to work, the servlet handling logout must not be protected in the *web.xml*. Otherwise, requesting logout will result in a login request. The following example illustrates how to unprotect successfully a logout servlet. The additional *<security-constraint\>...</security-constraint\>* section explicitly enables access to the logout servlet.

```
<security-constraint>
    <web-resource-collection>
      <web-resource-name>Start Page</web-resource-name>
      <url-pattern>/*</url-pattern>
    </web-resource-collection>
<auth-constraint>
            <role-name>Everyone</role-name>
</ auth-constraint>
  </security-constraint>

<security-constraint>
    <web-resource-collection>
      <web-resource-name>Logout</web-resource-name>
      <url-pattern>/LogoutServlet</url-pattern>
    </web-resource-collection>
  </security-constraint>

```

*Avoid Mapping Servlet Resources to /\* in the web.xml* 

Avoid mapping a servlet to resources using wildcard \(*<url-pattern\>/\*</url-pattern\>* in the *web.xml*\). This may lead to an infinite loop. Instead, map the servlet to particular resources, as in the following example:

```
  <servlet-mapping>
    <servlet-name>Logout Servlet</servlet-name>
    <url-pattern>/LogoutServlet</url-pattern>
    <servlet-class>test.LogoutServlet</servlet-class>
  </servlet-mapping>
```



## Next Steps

You can now test the application locally. For more information, see [Test Security Locally](test-security-locally-fe47e02.md).

After testing, you can proceed with deploying the application to SAP BTP. For more information, see [Deploying and Updating Java Applications](../30-development-neo/deploying-and-updating-java-applications-e5dfbc6.md).

