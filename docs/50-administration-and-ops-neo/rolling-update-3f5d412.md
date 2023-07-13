<!-- loio3f5d41207b6a4d0b9ad2e46dc6f27e69 -->

# rolling-update

The rolling-update command performs update of an application without downtime in one go.



> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**



## Prerequisites

-   You have at least one application process that is not in use, see your compute unit quota.

-   The command can be used with compatible application changes only.




The rolling-update command performs the following steps:

1.  Deploys a new version of the application.
2.  Starts a new application process.
3.  Disables new connection requests for one of the old application processes.
4.  Waits for the given timeout.
5.  Stops the disabled application process.
6.  Repeats steps 2 to 5 for all remaining old application processes.

```
neo rolling-update --host <host> --account <subaccount_technical_name> --application <application_name> 
--source <file_location> --user <e-mail_or_user>
  
```



<a name="loio3f5d41207b6a4d0b9ad2e46dc6f27e69__section_N10015_N10012_N10001"/>

## Parameters

To list all parameters available for this command, execute `neo help rolling-update` in the command line.


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

`-s`, `--source`



</td>
<td valign="top">

A comma-separated list of file locations, pointing to WAR files, or folders containing them

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

`Type`: URL. For acceptable values see [Regions](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/350356d1dc314d3199dca15bd2ab9b0e.html "You can deploy applications in different regions. Each region represents a geographical location (for example, Europe, US East) where applications, data, or services are hosted.") :arrow_upper_right:.



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

`--connections`



</td>
<td valign="top">

The number of connections used to deploy an application. Use it to speed up deployment of application archives bigger than 5 MB in slow networks. Choose the optimal number of connections depending on the overall network speed to the cloud.

`Default`: *1*

`Acceptable values`: `1-6`

`Type`: integer



</td>
</tr>
<tr>
<td valign="top">

 `--ev` 



</td>
<td valign="top">

Environment variables for configuring the environment in which the application runs.

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

JRE version

`Default`: depends on the SDK for SAP BTP, Neo environment

`Type`: the version number of the JRE 7.

For more information, see [Choose JRE Version](choose-jre-version-ee71c1a.md)



</td>
</tr>
<tr>
<td valign="top">

`--timeout`



</td>
<td valign="top">

Timeout before stopping the old application processes \(in seconds\)

`Default`: 60 seconds



</td>
</tr>
<tr>
<td valign="top">

`-V`, `--vm-arguments`



</td>
<td valign="top">

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

Compute Unit size:

lite, pro, prem, prem-plus

The compute unit size defines the default memory settings.

For more information, see [Compute Units](../30-development-neo/compute-units-7612fba.md)

`Default`:*lite*



</td>
</tr>
<tr>
<td valign="top">

`--runtime-version`



</td>
<td valign="top">

The runtime version on which the application will be started and will run on the same version after a restart. Otherwise, by default, the application is started on the latest minor version \(of the same major version\) which is backward compatible and includes the latest corrections \(including security patches\), enhancements, and updates. Note that choosing this option does not affect already started application processes.

You can view the recommended versions by executing the *list-runtime-versions* command.

> ### Note:  
> If you choose your runtime version, consider its expiration date and plan updating to a new version regularly.

For more information, see [Choose Application Runtime Version](choose-application-runtime-version-13afe5c.md) 



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



<a name="loio3f5d41207b6a4d0b9ad2e46dc6f27e69__section_N1014A_N10012_N10001"/>

## Example

```
neo rolling-update --host us1.hana.ondemand.com --account mysubaccount --application myapp --source samples/deploy_war/example.war 
--user mymail@example.com --timeout 5
```

**Related Information**  


[deploy](deploy-937db4f.md "Deploying an application publishes it to SAP BTP. Use the optional parameters to make some specific configurations of the deployed application.")

[Update Applications with Zero Downtime](update-applications-with-zero-downtime-a10f6c2.md "The platform allows you to update an application in a manner in which the application remains operable all the time and your users do not experience downtime.")

