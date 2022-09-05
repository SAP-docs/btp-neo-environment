<!-- loio298a207f33c4484b9894b7c4e2900566 -->

# create-jmx-check

Creates a JMX check.



> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**



```
neo create-jmx-check -a <subaccount_technical_name> -u <e-mail_or_user> -n <JMX_check_name> -O <MBean_object_name> -A <MBean_object_attribute> -h <host>
```



## Parameters

> ### Note:  
> The JMX check settings support the JMX specification. For more information, see [Java Management Extensions \(JMX\) Specification](https://docs.oracle.com/javase/8/docs/technotes/guides/jmx/JMX_1_4_specification.pdf).


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

`-u`, `--user`



</td>
<td valign="top">

Use your email, SAP ID or user name

`Type`: string



</td>
</tr>
<tr>
<td valign="top">

`-n`, `--name`



</td>
<td valign="top">

Name of the JMX check

The name must be up to 99 characters long and must not contain the following symbols: \` ~ ! $ % ^ & \* | ' " < \> ? , \( \) =

`Type`: string



</td>
</tr>
<tr>
<td valign="top">

`-O`, `--object-name`



</td>
<td valign="top">

Object name of the MBean that you want to call

If it contains quotation marks, they should be escaped with ‘\\’.

`Type`: string



</td>
</tr>
<tr>
<td valign="top">

`-A`, `--attribute`



</td>
<td valign="top">

Name of the attribute inside the class with the specified object name.

`Type`: string



</td>
</tr>
<tr>
<td valign="top">

`-h`, `--host`



</td>
<td valign="top">

Enter a region host.

`Type`: URL. For acceptable values see [Regions](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/350356d1dc314d3199dca15bd2ab9b0e.html "You can deploy applications in different regions. Each region represents a geographical location (for example, Europe, US East) where applications, data, or services are hosted.") :arrow_upper_right:



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

`-b`, `--application` 



</td>
<td valign="top">

Application name

 `Type`: string \(up to 30 characters; lowercase letters and numbers, starting with a letter\)

> ### Note:  
> If the parameter is not used, the JMX check will be on subaccount level for all running applications in the subaccount.



</td>
</tr>
<tr>
<td valign="top">

`-K`, `--key`



</td>
<td valign="top">

Attribute key

It is needed only if the attribute is a composite data structure. This key defines the item in the composite data structure. For more information about the composite data structure, see [Class CompositeDataSupport](http://docs.oracle.com/javase/1.5.0/docs/api/javax/management/openmbean/CompositeDataSupport.html).

`Type`: string



</td>
</tr>
<tr>
<td valign="top">

`-o`, `--operation`



</td>
<td valign="top">

Operation that has to be called on the MBean after checking the attribute value.

It is useful for resetting statistical counters to restart an operation on the same MBean.

`Type`: string



</td>
</tr>
<tr>
<td valign="top">

`-U`, `--unit`



</td>
<td valign="top">

Unit of measurement

`Type`: string



</td>
</tr>
<tr>
<td valign="top">

`-W`, `--warning`



</td>
<td valign="top">

Warning threshold

The threshold can be a regular expression in case of string values or compliant with the official nagios threshold/ranges format. For more information about the format in case it is a number, see the [official nagios documentation](https://nagios-plugins.org/doc/guidelines.html#THRESHOLDFORMAT).



</td>
</tr>
<tr>
<td valign="top">

`-C`, `--critical`



</td>
<td valign="top">

Critical threshold

The threshold can be a regular expression in case of string values or compliant with the official nagios threshold/ranges format. For more information about the format in case it is a number, see the [official nagios documentation](https://nagios-plugins.org/doc/guidelines.html#THRESHOLDFORMAT).



</td>
</tr>
<tr>
<td valign="top">

`-w`, `--overwrite`



</td>
<td valign="top">

Overwrites an existing check.

`Default`: false

`Type`: boolean

> ### Note:  
> When you use this parameter, a new JMX check is created if the one you specify does not exist.



</td>
</tr>
</table>



## Example 1: Configuring a JMX Check

For a typical example how to configure a JMX check for your application and subscribe recipients to receive notification alerts, see [Configure JMX Checks for Java Applications from the Console Client](https://help.sap.com/viewer/64f7d2b06c6b40a9b3097860c5930641/Cloud/en-US/21d734fa88f44298a8a9cb1f759f8fb9.html "Configure a JMX check from the console client to monitor your Java application.") :arrow_upper_right:.



## Example 2: Using Warning and Critical Thresholds

The following example creates a JMX check that returns a warning state of the metric if the value is between 10 and 100 bytes, and returns a critical state if the value is greater than 100 bytes. If the value is less than 10 bytes, the returned state is OK.

```
neo create-jmx-check -a mysubaccount -b demo -u p1234567 -n "JVM Heap Memory Used" -O java.lang:type=Memory -A HeapMemoryUsage -K used -U B -W 10 -C 100 -h hana.ondemand.com
```



## Example 3: Using an Operation on an MBean

```
neo create-jmx-check -a mysubaccount -b demo -u p1234567 -n "JVM Heap Memory Used" -O Catalina:type=GlobalRequestProcessor,name="http-bio-8041" -A HeapMemoryUsage –o resetCounters -h hana.ondemand.com
```

**Related Information**  


[JMX Checks](https://help.sap.com/viewer/64f7d2b06c6b40a9b3097860c5930641/Cloud/en-US/ef5c05a713154945b347f87b54446c2b.html "Registering JMX checks allows alerting on any metric that is based on JMX MBean attribute.") :arrow_upper_right:

[Monitoring Java Applications](https://help.sap.com/viewer/64f7d2b06c6b40a9b3097860c5930641/Cloud/en-US/cf4b2953c2534c0a9b491abf5a4847d7.html "") :arrow_upper_right:

