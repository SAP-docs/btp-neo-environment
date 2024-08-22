<!-- loioe6433164bb571014aae3ba1ee751b250 -->

# Protection from Cross-Site Scripting \(XSS\)

This document describes how to protect SAP BTP applications from XSS attacks.

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of the following technology portfolios: application development; process automation; integration; data, analytics, and enterprise planning; artificial intelligence. The platform offers users the ability to turn data into business value, compose end-to-end business processes, connect entire IT landscapes, and personalize, build and extend SAP applications. This reduces the overall total cost of ownership maintaining SAP landscapes and third-party software across end-to-end business processes.") :arrow_upper_right:.**



<a name="loioe6433164bb571014aae3ba1ee751b250__section_91F4FFC184824A82ADB53630B16B45C6"/>

## What is Cross-Site Scripting \(XSS\)

Cross-site Scripting \(XSS\) is the name of a class of security vulnerabilities that can occur in Web applications. It summarizes all vulnerabilities that allow an attacker to inject HTML Markup and/or JavaScript into the affected Web application's front-end.

XSS can occur whenever the application dynamically creates its HTML/JavaScript/CSS content, which is passed to the user's Web browser, and attacker-controlled values are used in this process. In case these values are included into the generated HTML/JavaScript/CSS without proper validation and encoding, the attacker is able to include arbitrary HTML/JavaScript/CSS into the application's frontend, which in turn is rendered by the victim's Web browser and, thus, interpreted in the victim's current authentication context.



<a name="loioe6433164bb571014aae3ba1ee751b250__section_tsp_wyn_vdb"/>

## How To Protect Applications from Cross-Site Scripting

There are several possibilities you can use to protect your application:

-   Protecting applications using SAPUI5
-   Protecting applications using the XSS Output Encoding Library




<a name="loioe6433164bb571014aae3ba1ee751b250__section_75217150BA2741E2BE898BA3C5001D2A"/>

## Protecting Applications Using SAPUI5

For SAPUI5 applications, XSS vulnerabilities can exist at different levels:

-   Within the HTML page or custom data transports sent to the browser by the server
-   Within the JavaScript Code of the application processing server responses
-   Within the HTML renderers of SAPUI5 controls

For more information about the security measures implemented by SAPUI5, see [Securing SAPUI5 Applications](https://sapui5.hana.ondemand.com/sdk/#docs/guide/91f3d8706f4d1014b6dd926db0e91070.html).



<a name="loioe6433164bb571014aae3ba1ee751b250__section_znx_pvb_1jb"/>

## Protecting Applications from Domain Relaxation Risk

Domain Relaxation can occur in some on-premise UI technologies such as WebGUI, WebDynPro, and BSP UI. It uses the Same-Origin Policy, which allows a web browser to permit scripts contained in one web page to access data from another web page as long as they have the same root domain. This policy also prevents a malicious script on one page from obtaining access to sensitive data on another web page.

However, in some cases, an attacker can call the exposed service and use its domain relaxation feature, so that it shares its own application's root domain with your web pages. If this happens, the attacker has full access to all of your application resources.

To prevent this from happening, use the `--disable-application-url` parameter when creating a custom domain to block attackers from using your default application URL and prevent them from accessing your sensitive data. For more information, see [add-custom-domain](../50-administration-and-ops-neo/add-custom-domain-ebc5269.md).



<a name="loioe6433164bb571014aae3ba1ee751b250__section_8F4578378FF747ACAA288C571D3C0A8B"/>

## Protecting Applications Using the XSS Output Encoding Library

> ### Note:  
> Using the XSS output encoding library is given as an option that you can use for your applications. You can successfully use your custom or third-party XSS protection libraries that you have available.

SAP BTP provides an output encoding library that helps protecting from XSS vulnerabilities. It is a central library that implements several encoding methods for the different contexts.

In the application node, first retrieve the `com.sap.security.core.server.csi.IXSSEncoder` interface using `com.sap.security.core.server.csi.XSSEncoder.getInstance()`.

The interface provides methods for retrieving parameters or attributes, and for encoding and decoding data.

It also has various methods for different data types that should be encoded:


<table>
<tr>
<th valign="top">

Data Type

</th>
<th valign="top">

Code Sample for Encoding

</th>
</tr>
<tr>
<td valign="top">

HTML / XML:

</td>
<td valign="top">

out = XSSEncoder.encodeHTML\( in \); / XSSEncoder.encodeXML\( val \);

</td>
</tr>
<tr>
<td valign="top">

JavaScript:

</td>
<td valign="top">

out = XSSEncoder.encodeJavaScript\( val \);

</td>
</tr>
<tr>
<td valign="top">

URL:

</td>
<td valign="top">

out = XSSEncoder.encodeURL\( val \);

</td>
</tr>
<tr>
<td valign="top">

CSS:

</td>
<td valign="top">

out = XSSEncoder.encodeCSS\( val \);

</td>
</tr>
</table>



<a name="loioe6433164bb571014aae3ba1ee751b250__section_igv_kpd_rhb"/>

## Installing the XSS Output Encoding Library

Тo use XSS output encoding API, you need to add it as library to the Dynamic Web Project. This is done with the following steps:

1.  In the *Project Explorer* view, select the *persistence-with-jpa/WebContent/WEB-INF/lib* node.
2.  From the context menu, choose *Import* \> *General* \> *File System* and choose *Next.* 
3.  Browse to your local directory where you downloaded and unpacked the SAP BTP SDK, select the *repository/plugins* directory \(*/impl* directory if you are using the Tomcat 7 runtime\), and choose *OK*.
4.  Select the archive *com.sap.security.core.server.csi\_1.x.y.jar* and choose *Finish*.



<a name="loioe6433164bb571014aae3ba1ee751b250__section_xzw_lpd_rhb"/>

## Using the XSS Output Encoding Library

In the following example, we demonstrate the use of the XSS Output Encoding API. The example has one HTML form that retrieves user input, which can contain malicious code:

```

<%@ page language="java" contentType="text/html; charset=UTF-8" pageEncoding="UTF-8"%> 
<!DOCTYPE html PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN" "http://www.w3.org/TR/html4/loose.dtd">
<html>
    <head>
<title>Login Page</title>
<link rel="stylesheet" href="resources/login.css" />
<meta http-equiv="cache-control" content="no-cache"/>
      <meta http-equiv="Content-Type" content="text/html; charset=UTF-8"/>
    </head>
    <body>
      <div class="fields">
<form method="post" action="checkedInput.jsp">
          <span class="header">Enter your names:</span><br/>
          <table border="0">
            <tr>
              <td>First name: </td>
              <td><input name="firstname"/></td>
            </tr>
<tr>
              <td>Last name: </td>
              <td><input name="lastname"/></td>
</tr>
<tr>
<td></td>
<td><input type="submit" value="Submit"/></td>
            </tr>
          </table>
        </form>
      </div>
</body>
</html>






```

Тhis form sends parameters to a second JSP:

```

<%@ page language="java" contentType="text/html; charset=UTF-8" pageEncoding="UTF-8"%>
<%@ page import="com.sap.security.core.server.csi.IXSSEncoder" %>
<%@ page import="com.sap.security.core.server.csi.XSSEncoder" %>
<%@ page import="java.io.UnsupportedEncodingException" %>
<!DOCTYPE html PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN" "http://www.w3.org/TR/html4/loose.dtd">
<html>
<head>
<title>Welcome</title>
<link rel="stylesheet" href="resources/login.css" />
<meta http-equiv="cache-control" content="no-cache"/> <meta http-equiv="Content-Type" content="text/html; charset=UTF-8"/>
  </head>
<body>
<div class="fields">
      <form>
<%
String encodedName = validateInput(request.getParameter("firstname"));
out.println("<br>Hello, " + encodedName);
        String lastName = request.getParameter("lastname");
out.println("<br> Hacked: " + lastName);
%>
      </form>
    </div>
    <%!
      private String validateInput(String firstName) {
String encodedInput = null;
        IXSSEncoder xssEncoder = XSSEncoder.getInstance();
try {
encodedInput = xssEncoder.encodeHTML(firstName).toString();
        } catch (UnsupportedEncodingException e) {
          e.printStackTrace();
        } return encodedInput;
      }
    %>
  </body>
</html>






```

Even though the attacker might attempt to inject malicious code in both parameters - *firstname* and *lastname*, the firstname is protected, since it uses the output encoding library to neutralize all special symbols. However, the attack attempt will be successful for the lastname parameter since it is printed directly to the output. This is unsafe behavior and should be avoided.

