<!-- loiod553d78bf9bd4ecbac201b873f557db6 -->

# Using Cloud Environment Variables

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**



## Overview

SAP BTP runtime sets several system environment variables that identify the runtime environment of the application. Using them, an application can get information about its application name, subaccount and URL, as well as information about the region host it is deployed on and region-specific parameters. All SAP BTP specific environment variables names start with the common prefix HC\_.



## List of Environment Variables

The following SAP BTP environment variables are set to the runtime environment of the application:

****


<table>
<tr>
<th valign="top">

Key



</th>
<th valign="top">

Sample Value



</th>
<th valign="top">

Description



</th>
</tr>
<tr>
<td valign="top">

HC\_HOST



</td>
<td valign="top">

***hana.ondemand.com*** / ***us1.hana.ondemand.com*** / ***hanatrial.ondemand.com*** 



</td>
<td valign="top">

Base URL of the SAP BTP region host where the application is deployed



</td>
</tr>
<tr>
<td valign="top">

HC\_HOST\_SVC



</td>
<td valign="top">

***svc.hana.ondemand.com / svc.us1.hana.ondemand.com / svc.hanatrial.ondemand.com***



</td>
<td valign="top">

URL of the SAP BTP region host which provides access within the same region; for direct communication and not open on the Internet or other networks



</td>
</tr>
<tr>
<td valign="top">

HC\_HOST\_CERT



</td>
<td valign="top">

***cert.hana.ondemand.com / cert.us1.hana.ondemand.com / cert.hanatrial.ondemand.com***



</td>
<td valign="top">

URL of the SAP BTP region host which enables client certificate authentication



</td>
</tr>
<tr>
<td valign="top">

HC\_REGION



</td>
<td valign="top">

***EU\_1*** / ***US\_1*** 



</td>
<td valign="top">

Region where the application is deployed



</td>
</tr>
<tr>
<td valign="top">

HC\_ACCOUNT



</td>
<td valign="top">

***mysubaccount***



</td>
<td valign="top">

Name of the subaccount where the application is deployed



</td>
</tr>
<tr>
<td valign="top">

HC\_APPLICATION



</td>
<td valign="top">

***myapp***



</td>
<td valign="top">

Application name



</td>
</tr>
<tr>
<td valign="top">

HC\_APPLICATION\_URL



</td>
<td valign="top">

***https://myapp.hana.ondemand.com***



</td>
<td valign="top">

URL of the application



</td>
</tr>
<tr>
<td valign="top">

HC\_LOCAL\_HTTP\_PORT



</td>
<td valign="top">

***9001***



</td>
<td valign="top">

HTTP port of the application bound to localhost



</td>
</tr>
<tr>
<td valign="top">

HC\_LANDSCAPE



</td>
<td valign="top">

***production*** / ***trial*** 



</td>
<td valign="top">

Type of the region host where the application is deployed



</td>
</tr>
<tr>
<td valign="top">

HC\_PROCESS\_ID



</td>
<td valign="top">

***8921b0a7cebc5538038b6b7b0c0ea6a7127f0cd4***



</td>
<td valign="top">

Process ID of the current application process as returned by the `status` command with parameter `--show-full-process-id`.



</td>
</tr>
<tr>
<td valign="top">

HC\_AVAILABILITY\_ZONE



</td>
<td valign="top">

***AZ 1*** / ***AZ 2***



</td>
<td valign="top">

Name of the availability zone where the application process is running



</td>
</tr>
<tr>
<td valign="top">

HC\_OP\_HTTP\_PROXY\_HOST



</td>
<td valign="top">

***localhost***



</td>
<td valign="top">

Host of the HTTP Proxy for on-premise connectivity



</td>
</tr>
<tr>
<td valign="top">

HC\_OP\_HTTP\_PROXY\_PORT



</td>
<td valign="top">

***20003***



</td>
<td valign="top">

Port of the HTTP Proxy for on-premise connectivity



</td>
</tr>
</table>



## Using Cloud Environment Variables

SAP BTP environment variables are accessed as standard system environment variables of the Java process - for example via System.getenv\("..."\).

> ### Note:  
> Environment variables are not set when deploying locally with the console client.



```
<html>
  <head>
    <title>Display SAP BTP Environment Platform variables</title>
  </head>

  <body>
        <p>Application Name: <%= System.getenv("HC_APPLICATION") %></p>
  </body>
</html>

```

**Related Information**  


[status](../50-administration-and-ops-neo/status-d4f6592.md "You can check the current status of an application or application process. The command lists all application processes with their IDs, state, last change date sorted chronologically, and runtime information.")

[Regions](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/350356d1dc314d3199dca15bd2ab9b0e.html "You can deploy applications in different regions. Each region represents a geographical location (for example, Europe, US East) where applications, data, or services are hosted.") :arrow_upper_right:

[HTTP Proxy for On-Premise Connectivity](https://help.sap.com/viewer/b865ed651e414196b39f8922db2122c7/Cloud/en-US/d872cfb4801c4b54896816df4b75c75d.html "The Connectivity service provides a standard HTTP Proxy for on-premise connectivity that is accessible by any application.") :arrow_upper_right:

