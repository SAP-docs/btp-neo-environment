<!-- loioe5be9994bb571014b575a785961062db -->

# Using the Apache Tomcat CSRF Prevention Filter

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://launchpad.support.sap.com/#/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**



<a name="loioe5be9994bb571014b575a785961062db__section_2B5216929F7A410F8AFE7256DC3A6A7C"/>

## Prerequisites

You have created a working Web application and have enforced authentication for it. See [Authentication](authentication-e637f62.md#loioe637f62abb571014857cb0232adc43a7).

For the purposes of this tutorial, an example application consisting of the following URLs will be used:

-   `/home` - displays home page, and has links to `/doActionA` and `/doActionB` 
-   `/doActionA` - executes a security sensitive action A, and also has a link to `/doActionB` 
-   `/doActionB` - executes a security sensitive action B



<a name="loioe5be9994bb571014b575a785961062db__section_AF1CCB2ECA864A018FC435E89E6F0E49"/>

## Adding CSRF Prevention to a Web Application

**1. Choose entry point URLs** 

Entry points are URLs used as a starting point for the navigation across the application. They are not protected against CSRF as requests to them will not be tested for the presence of a valid nonce. Entry points should meet the following criteria:

-   Entry points are protected resources.
    -   Entry points should not trigger any security sensitive actions.
    -   Using the full set of entry points as navigation starting points, it should be possible to reach any link in the application that is being protected against CSRF.


Considering the example application, `/doActionA` and`/doActionB` are not plausible for entry points since they are state changing URLs. They should be protected against CSRF. Following the rules above, you could easily conclude that `/home` is best suited to be the entry point.

**2. Define the filter in the application's web.xml** 

The CSRF Prevention Filter should be defined in the `web.xml` configuration file. Important init parameters are `entryPoints` and `nonceCacheSize`. The first parameter's value is a comma separated list of the entry points, identified in the previous step. In this case `/home`.

The second parameter, `nonceCacheSize`, should be used in case of parallel requests that might cause a new nonce to be generated, before the validation of an encoded URL. The `nonceCacheSize` parameters defines the number of previous values stored. The default number is 5.

The definition below will protect all URLs except for the entry point `/home`.

```
  <filter>
    <filter-name>CsrfFilter</filter-name>
    <filter-class>org.apache.catalina.filters.CsrfPreventionFilter</filter-class>
    <init-param>
      <param-name>entryPoints</param-name>
      <param-value>/home</param-value>
    </init-param>
  </filter>

```

**3. Define the filter mapping in the web.xm**

The general recommendation is to enable the filter for all URLs using the pattern /\*:

```
  <filter-mapping>
    <filter-name>CsrfFilter</filter-name>
    <url-pattern>/*</url-pattern>
  </filter-mapping>

```

**4. Encode all URL links**

In the example application the URLs that should be encoded are`/protected/doActionA` and `/protected/doActionB` in `/protected/home`, and the`/protected/doActionB` URL in`/protected/doActionA`. To encode the URLs use `HttpServletResponse#encodeRedirectURL(String)` or `HttpServletResponse#encodeURL(String)`.

Here is the source for the `home.jsp`, mapped to`/protected/home`.

```
<%@ page language="java" contentType="text/html; charset=ISO-8859-1"
    pageEncoding="ISO-8859-1"%>
<!DOCTYPE html PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN" "http://www.w3.org/TR/html4/loose.dtd">
<html>
<head>
<meta http-equiv="Content-Type" content="text/html; charset=ISO-8859-1">
<title>Home</title>
</head>
<body>
	This is a home page and I am an entry point.
	<br/>

	<%
		String urlActionA = "doActionA";
		String urlActionAEncoded = response.encodeURL(urlActionA);
	%>
	<form action="<%=urlActionAEncoded %>" method="POST">
		<input type="text" name="arg" value="A"/>
		<input type="submit" value="Do Action A"/>
	</form>
	<br/>

	<%
		// Encode URL for action B
		String urlActionB = "doActionB";
		String urlActionBEncoded = response.encodeURL(urlActionB);
	%>
	<form action="<%=urlActionBEncoded %>" method="POST">
		<input type="text" name="arg" value="B"/>
		<input type="submit" value="Do Action B"/>
	</form>
	<br/>
</body>
</html>

```

**5. Adding new URLs to a CSRF protected application** 

In case a new URL needs to be added to the application later, for example, `/newlink`, then you should evaluate its need of CSRF protection. For example, if it executes a state changing action, it certainly should be protected. Depending on the case there are two possibilities:

-   No CSRF protection is needed

    The URL should be defined as entry point. This is done by editing the `web.xml` and adding the new URL to the value of the init parameter `entryPoints` of the `CsrfPreventionFilter` from step 2. The new value should be separated with a comma.

-   CSRF protection is needed.

    The `/newlink` URL should be encoded in all pages that use it as described in step 4.


All CSRF protected links that are used in the new page should be encoded, as described in step 4.

