<!-- loio113e95746d63472a801ba8339a67b021 -->

# set-application-property

Use this command to change the value of a single property of a deployed application without the need to redeploy it. Execute the command separately for each property that you want to set. For the changes to take effect, restart the application.



> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**



To execute the command successfully, you need to to specify the new value of one property from the optional parameters table below.

```
neo set-application-property --host <host> --account <subaccount_technical_name> --application <application_name> --user <e-mail_or_user> 
--<property> <new_property_value>
```



<a name="loio113e95746d63472a801ba8339a67b021__section_N1001E_N10012_N10001"/>

## Parameters

To list all parameters available for this command, execute the `neo help set-application-property` in the command line.


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



</td>
</tr>
<tr>
<td valign="top">

`-h`, `--host`



</td>
<td valign="top">

Enter a region host.

`Type`: URL, for acceptable values see [Regions](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/350356d1dc314d3199dca15bd2ab9b0e.html "You can deploy applications in different regions. Each region represents a geographical location (for example, Europe, US East) where applications, data, or services are hosted.") :arrow_upper_right:.



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

Use your email, SAP ID or user name

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

`--ev`



</td>
<td valign="top">

Environment variables for configuring the environment in which the application runs.

Sets the new environment variable without removing the previously set value; can be used multiple times in one execution.

`Type`: --ev <KEY1\>=<VALUE1\> --ev <KEY2\>=<VALUE2\>, where a key-value pair specifies one environment variable.

If you provide a key without any value \(--ev <KEY1\>=\), the environment variable KEY1 will be deleted.

For a value that contains spaces, use quotation marks.



</td>
</tr>
<tr>
<td valign="top">

`-j`, `--java-version`



</td>
<td valign="top">

Java Virtual Machine version

`Default`: depends on the SAP BTP SDK for Neo environment

`Type`: the version number of the JRE 7.

\(beta\) You can use JRE 8 with the Java Web Tomcat 7 runtime \(neo-java-web version 2.25 or higher\) in subaccounts enabled for beta features.

For more information, see [Choose JRE Version](choose-jre-version-ee71c1a.md)



</td>
</tr>
<tr>
<td valign="top">

`-m`, `--minimum-processes`



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

For more information, see [Configure VM Arguments](configure-vm-arguments-b82d392.md) 



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

For more information, see [Compute Units](../30-development-neo/compute-units-7612fba.md)



</td>
</tr>
<tr>
<td valign="top">

`--runtime-version`



</td>
<td valign="top">

SAP BTP runtime version on which the application will be started and will run on the same version after a restart. Otherwise, by default, the application is started on the latest minor version \(of the same major version\) which is backward compatible and includes the latest corrections \(including security patches\), enhancements, and updates. Note that choosing this option does not affect already started application processes.

You can view the recommended versions by executing the *list-runtime-versions* command.

> ### Note:  
> If you choose your runtime version, consider its expiration date and plan updating to a new version regularly.

For more information, see [Choose Application Runtime Version](choose-application-runtime-version-13afe5c.md) 



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

A comma separated list of MIME types for which compression will be used

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



</td>
</tr>
<tr>
<td valign="top">

 `--max-threads`



</td>
<td valign="top">

Specifies the maximum number of simultaneous requests that can be handled.

`Default`: *200*



</td>
</tr>
<tr>
<td valign="top">

`--uri-encoding`



</td>
<td valign="top">

Specifies the character encoding used to decode the URI bytes on application request.

`Default`: *ISO-8859-1*

For more information, see the encoding sets supported by [Java SE 6](http://docs.oracle.com/javase/6/docs/technotes/guides/intl/encoding.doc.html) and [Java SE 7](http://docs.oracle.com/javase/7/docs/technotes/guides/intl/encoding.doc.html).



</td>
</tr>
</table>



## Example

To change the minimum number of server processes on which you want your deployed application to run, execute:

```
neo set-application-property --host hana.ondemand.com --account mysubaccount --application myapp --user mymail@example.com --minimum-processes 2
```

**Related Information**  


[Update Application Properties](update-application-properties-cadb1dd.md "You can update a property of an application running on SAP BTP without redeploying it.")

[deploy](deploy-937db4f.md "Deploying an application publishes it to SAP BTP. Use the optional parameters to make some specific configurations of the deployed application.")

[display-application-properties](display-application-properties-7ed175c.md "The command displays the set of properties of a deployed application, such as runtime version, minimum and maximum processes, Java version.")

[restart](restart-7c0f7a1.md "Use this command to restart your application or a single application process. The effect of the restart command is the same as executing the stop command first and when the application is stopped, starting it with the start command.")

[Org Administration Using the Cockpit](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/c4c25cc63ac845779f76202360f98694.html "In the Cloud Foundry enviroment, manage orgs, spaces and space quota plans using the SAP BTP cockpit.") :arrow_upper_right:

