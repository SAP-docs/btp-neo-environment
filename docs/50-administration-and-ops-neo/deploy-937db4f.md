<!-- loio937db4fa204c456f9b7820f83bc87118 -->

# deploy

Deploying an application publishes it to SAP BTP. Use the optional parameters to make some specific configurations of the deployed application.

If you use enhanced disaster recovery, the application is deployed first on the specified region and then on the disaster recovery region.



> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**



```
neo deploy --host <host> --account <subaccount_technical_name> --application <application_name> 
--source <file_location> --user <e-mail_or_user>
  
```



<a name="loio937db4fa204c456f9b7820f83bc87118__section_N10015_N10012_N10001"/>

## Parameters

To list all parameters available for this command, execute ***neo help deploy*** in the command line.


<table>
<tr>
<th valign="top" colspan="2">

Required



</th>
</tr>
<tr>
<td valign="top">

`-a`, `--account`



</td>
<td valign="top">

Subaccount technical name

`Type`: string \(up to 30 characters; lowercase letters and numbers, starting with a letter\)



</td>
</tr>
<tr>
<td valign="top">

`-b`, `--application` 



</td>
<td valign="top">

Application name

 `Type`: string \(up to 30 characters; lowercase letters and numbers, starting with a letter\)

> ### Note:  
> When the sum of the characters of the subaccount technical name and the application name exceeds 30, the default application URL is truncated. This means that parts of the subaccount name and the application name will be missing from the application URL:
> 
> > ### Example:  
> > Subaccount name: mycompanyextensionspoc
> > 
> > Application name: myappsimplesimplereq
> > 
> > Application URL: `https://myappsimplemycompanyextensions.us1.hana.ondemand.com`



</td>
</tr>
<tr>
<td valign="top">

`-s`, `--source`



</td>
<td valign="top">

A comma-separated list of file locations, pointing to WAR files, or folders containing them

> ### Note:  
> The size of an application can be up to 1.5 GB. If the application is packaged as a WAR file, the size of the unzipped content is taken into account.

If you want to deploy more than one application on one and the same application process, put all WAR files in the same folder and execute the deployment with this source, or specify them as a comma-separated list.

`Type`: file location



</td>
</tr>
<tr>
<td valign="top">

`-h`, `--host`



</td>
<td valign="top">

Enter a region host.

`Type`: URL. For acceptable values, see [Regions](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/350356d1dc314d3199dca15bd2ab9b0e.html "You can deploy applications in different regions. Each region represents a geographical location (for example, Europe, US East) where applications, data, or services are hosted.") :arrow_upper_right:.

To deploy an application in more than one region, execute the deploy separately for each region host.



</td>
</tr>
<tr>
<td valign="top">

`-p`, `--password`



</td>
<td valign="top">

To protect your password, enter it only when prompted by the console client and not explicitly as a parameter in the properties file or the command line.

`Type`: string



</td>
</tr>
<tr>
<td valign="top">

`-u`, `--user`



</td>
<td valign="top">

Use your email, SAP ID, or username.

`Type`: string



</td>
</tr>
</table>


<table>
<tr>
<th valign="top" colspan="2">

Optional



</th>
</tr>
<tr>
<td valign="top" colspan="2">

**Command-specific parameters**



</td>
</tr>
<tr>
<td valign="top">

`--connections`



</td>
<td valign="top">

The number of connections used to deploy an application.

Use it to speed up deployment of application archives bigger than 5 MB in slow networks. Choose the optimal number of connections depending on the overall network speed to the cloud.

`Default`: *2*

`Acceptable values`: ***1-6***

`Type`: integer



</td>
</tr>
<tr>
<td valign="top">

 `--delta` 



</td>
<td valign="top">

Deploys only the changes between the provided source and the deployed content. New content will be added; missing content will be deleted. Recommended for development use to speed up the deployment.

> ### Note:  
> The deployment to the disaster recovery region is not supported with this parameter.

`Acceptable values`: None



</td>
</tr>
<tr>
<td valign="top">

 `--ev` 



</td>
<td valign="top">

Environment variables for configuring the environment in which the application runs.

> ### Note:  
> For security reasons, do not specify any confidential information in plain text format, such as usernames and passwords. You can either encrypt such data, or store it in a secure manner. For more information, see [Keystore Service](../60-security-neo/keystore-service-a18327e.md).

Sets one environment variable by removing the previously set value; can be used multiple times in one execution.

`Type`: --ev <KEY1\>=<VALUE1\> --ev <KEY2\>=<VALUE2\> , where a key-value pair specifies one environment variable

If you provide a key without any value \(--ev <KEY1\>=\), the `–ev` parameter is ignored.

For a value that contains spaces, use quotation marks.



</td>
</tr>
<tr>
<td valign="top">

`-j`, `--java-version`



</td>
<td valign="top">

Java/JRE major version number.

`Default`: see the default Java/JRE version for each runtime in [Application Runtime Container](../30-development-neo/application-runtime-container-7613bd2.md).

Each runtime has its own set of supported Java/JRE versions. See [Application Runtime Container](../30-development-neo/application-runtime-container-7613bd2.md).

`Type`: version number of Java/JRE.

For more information, see [Choose JRE Version](choose-jre-version-ee71c1a.md).



</td>
</tr>
<tr>
<td valign="top">

`-m`, ``



</td>
<td valign="top">

Minimum number of application processes, on which the application can be started

`Default`: *1*



</td>
</tr>
<tr>
<td valign="top">

`-M`, `--maximum-processes`



</td>
<td valign="top">

Maximum number of application processes, on which the application can be started

`Default`: *1*



</td>
</tr>
<tr>
<td valign="top">

`-V`, `--vm-arguments`



</td>
<td valign="top">

Java Virtual Machine arguments

System properties \(-D<name\>=<value\>\) separated with space that will be used when starting the application process.

Memory settings of your compute units. You can set the following memory parameters: -Xms, -Xmx, -XX:PermSize, -XX:MaxPermSize.

We recommend that you use the default memory settings. Change them only if necessary and note that this may impact the application performance or its ability to start.

For more information, see [Configure VM Arguments](configure-vm-arguments-b82d392.md).



</td>
</tr>
<tr>
<td valign="top">

`-z`, `--size`



</td>
<td valign="top">

Compute unit size

`Acceptable values`: lite, pro, prem, prem-plus

`Default`: the smallest size from the subaccount quotas

For more information, see [Compute Units](../30-development-neo/compute-units-7612fba.md).



</td>
</tr>
<tr>
<td valign="top">

`--runtime`



</td>
<td valign="top">

Application runtime

Use the parameter if you want to choose an application runtime container different from the one coming with your SDK. To view all available runtime containers, use [list-runtimes](list-runtimes-49bb201.md).

For more information, see [Application Runtime Container](../30-development-neo/application-runtime-container-7613bd2.md).

If you specify `--runtime`, you also have to specify `--runtime-version`.

> ### Note:  
> The deployment with an unsupported runtime will fail with an error message, and the deployment with a deprecated runtime will result in a warning message.



</td>
</tr>
<tr>
<td valign="top">

`--runtime-version`



</td>
<td valign="top">

The runtime version on which the application will be started and will run on the same version after a restart. Otherwise, by default, the application is started on the latest minor version \(of the same major version\) which is backward compatible and includes the latest corrections \(including security patches\), enhancements, and updates. Note that choosing this option does not affect already started application processes.

You can view the recommended versions by executing the *list-runtime-versions* command.

This is a mapping between the runtime and the respective version:

-   Java EE 7 Web Profile TomEE 7 corresponds to runtime **neo-javaee7-wp** and runtime version **1**. See [Java EE 7 Web Profile TomEE 7](../30-development-neo/java-ee-7-web-profile-tomee-7-f177a15.md).

-   Java Web Tomcat 9 corresponds to runtime **neo-java-web** and runtime version **4**. See [Java Web Tomcat 9](../30-development-neo/java-web-tomcat-9-41b1ee9.md).

-   Java Web Tomcat 8 corresponds to runtime **neo-java-web** and runtime version **3**. See [Java Web Tomcat 8](../30-development-neo/java-web-tomcat-8-fd6b72f.md).


> ### Note:  
> If you choose your runtime version, consider its expiration date and plan updating to a new version regularly.

For more information, see [Choose Application Runtime Version](choose-application-runtime-version-13afe5c.md).



</td>
</tr>
<tr>
<td valign="top" colspan="2">

**Tomcat connector attributes**



</td>
</tr>
<tr>
<td valign="top">

`--compression`



</td>
<td valign="top">

Enable or disable gzip response compression

`Default`: *off*

Possible values: *on* \(allow compression\), *off*\(disable compression\), *force* \(forces compression for all responses\) or an*integer* \(which enables compression and specifies the compression-min-size value in bytes\).

For more information, see [Enable and Configure Gzip Response Compression](enable-and-configure-gzip-response-compression-390594a.md)



</td>
</tr>
<tr>
<td valign="top">

`--compressible-mime-type`



</td>
<td valign="top">

A comma separated list of MIME types for which compression is used

`Default`: *text/html, text/xml, text/plain*

`Condition:` applicable if compression is enabled



</td>
</tr>
<tr>
<td valign="top">

`--compression-min-size`



</td>
<td valign="top">

Responses bigger than this value get compressed

`Condition:` applicable if compression is enabled



</td>
</tr>
<tr>
<td valign="top">

`--connection-timeout`



</td>
<td valign="top">

Defines the number of milliseconds to wait for the request URI line to be presented after accepting a connection.

`Default`: *20000*

> ### Tip:  
> You can use this option to mitigate the threat of slow HTTP attacks by applying the appropriate timeout value for your network setup. See [Protection from Web Attacks](../60-security-neo/protection-from-web-attacks-52750a8.md).



</td>
</tr>
<tr>
<td valign="top">

 `--max-threads`



</td>
<td valign="top">

Specifies the maximum number of simultaneous requests that can be handled

`Default`: *200*



</td>
</tr>
<tr>
<td valign="top">

`--uri-encoding`



</td>
<td valign="top">

Specifies the character encoding used to decode the URI bytes on application request

`Default`: *ISO-8859-1*

For more information, see the encoding sets supported by [Java SE 6](http://docs.oracle.com/javase/6/docs/technotes/guides/intl/encoding.doc.html) and [Java SE 7](http://docs.oracle.com/javase/7/docs/technotes/guides/intl/encoding.doc.html).



</td>
</tr>
</table>



<a name="loio937db4fa204c456f9b7820f83bc87118__section_N1014A_N10012_N10001"/>

## Example

Here are examples of some additional configurations. If your application is already started, stop it and start it again for the changes to take effect.

You can deploy an application on a host different from the default one by specifying the host parameter. For example, to use the region \(host\) located in the United States, execute:

```
neo deploy --host us1.hana.ondemand.com --account mysubaccount --application myapp --source samples/deploy_war/example.war 
--user mymail@example.com 
```

*Choose compute unit size*

To specify the compute unit size on which you want the application to run, use the `--size` parameter with one of the following values:

-   lite - Lite Edition
-   pro - Professional edition
-   prem - Premium edition
-   prem-plus - Premium Plus edition

Available sizes depend on your subaccount type and what options you have purchased. For trial accounts, only the Lite edition is available.

For more information, see [Compute Units](../30-development-neo/compute-units-7612fba.md).

For example, if you have an enterprise account and have purchased a package with Premium edition compute units, then you can run your application on a Premium compute unit size, by executing the following command:

```

neo deploy --size prem myapp.properties
```

*Set the context root of an application*

When deploying an application, name the WAR file with the desired context root.

For example, if you want to deploy your WAR in context root "/hello" then rename your WAR to hello.war.

If you want to deploy it in the "/" context root then rename your WAR to ROOT.war.

*Specify character encoding*

Using the`–uri-encoding` parameter, you can define the character encoding that will be used to decode the URI bytes on application request. For example, to use the UTF-8 encoding that can represent every character in the Unicode character set, execute

```

neo deploy --uri-encoding UTF-8 myapp.properties
```

**Related Information**  


[Console Client for the Neo Environment](console-client-for-the-neo-environment-7613230.md)

[Choose Application Runtime Version](choose-application-runtime-version-13afe5c.md "Applications deployed on SAP BTP are always started on the latest version of the application runtime container. This version contains all released fixes, critical patches and enhancements and is respectively the recommended option for applications. In some special cases, you can choose the version of the runtime container your application uses by specifying it with the parameter --runtime-version when deploying your application. To change this version, you need to redeploy the application without specifying this parameter.")

[Choose JRE Version](choose-jre-version-ee71c1a.md "You can choose the Java Runtime Environment (JRE) version used for an application.")

[Configure VM Arguments](configure-vm-arguments-b82d392.md "Using SAP BTP console client, you can configure the JRE by specifying custom VM arguments.")

[Enable and Configure Gzip Response Compression](enable-and-configure-gzip-response-compression-390594a.md "Usage of gzip response compression can optimize the response time and improve interaction with an application as it reduces the traffic between the Web server and browsers. Enabling compression configures the server to return zipped content for the specified MIME type and size of the response.")

[Scale Applications](scale-applications-745781b.md "Each application is started on a dedicated SAP BTP Runtime. One application can be started on one or many application processes, according to the compute unit quota that you have.")

[Update Application Properties](update-application-properties-cadb1dd.md "You can update a property of an application running on SAP BTP without redeploying it.")

[Deploying and Updating Java Applications](../30-development-neo/deploying-and-updating-java-applications-e5dfbc6.md "The Java application lifecycle management (Java ALM) service for SAP BTP lets you deploy and update Java applications via console client commands, the SAP BTP cockpit, or the Java ALM REST API.")

[Use Delta Deployment](../30-development-neo/use-delta-deployment-7a4aba2.md "By using the delta deployment option, you can apply changes in a deployed application faster without uploading the entire set of files tо SAP BTP.")

[Org Administration Using the Cockpit](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/c4c25cc63ac845779f76202360f98694.html "In the Cloud Foundry enviroment, manage orgs, spaces and space quota plans using the SAP BTP cockpit.") :arrow_upper_right:

[list-applications](list-applications-6942ec5.md "Lists all Java applications in the specified subaccount.")

