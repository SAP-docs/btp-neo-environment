<!-- loiof1caa871360c40e7be7ce4264ab9c336 -->

# MTA Module Types, Resource Types, and Parameters for Applications in the Neo Environment

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**

> ### Tip:  
> This section contains collapsible subsections. By clicking on the arrow-shaped icon next to a subsection, you can expand it to see additional information.

This section contains the parameters and options that can be used to compose the structure of an MTA deployment descriptor or an MTA extension descriptor.

> ### Note:  
> As both descriptor types use the YAML file format, strictly adhere to the following syntax practices:
> 
> -   The parameter names are case-sensitive
> -   The indents and spacing are specific



<a name="loiof1caa871360c40e7be7ce4264ab9c336__section_ltd_4yg_mz"/>

## Supported Target Platform Options

The supported target platform options describe general behavior and information about the deployed Multitarget Application. The according options are placed within the primary part of the МТА deployment descriptor or МТА extension descriptor. That is, they are not placed within any modules or resources.

> ### Note:  
> -   Note that any sensitive data should be placed within the MTA extension descriptor.
> -   To ensure that numeric values, such as product version and IDs, are not automatically interpreted as numbers, always wrap them in single quotes.


<table>
<tr>
<th valign="top" colspan="2">

Option



</th>
<th valign="top">

Description



</th>
<th valign="top">

Type



</th>
<th valign="top">

Default Value



</th>
<th valign="top">

Mandatory



</th>
</tr>
<tr>
<td valign="top" colspan="2">

`_schema-version`



</td>
<td valign="top">

Version of the MTA specification to which the MTA deployment descriptor complies. The current supported versions by the SAP Business Technology Platform\(SAP BTP\) are:

-   `2.1`
-   `3.1`



</td>
<td valign="top">

Enclosed String, use single quotes



</td>
<td valign="top">

n/a



</td>
<td valign="top">

yes



</td>
</tr>
<tr>
<td valign="top" colspan="2">

`ID`



</td>
<td valign="top">

The identifier of the deployed artifact. The ID should follow the convention for a reverse-URL dot-notation, and it has to be unique within a particular subaccount.



</td>
<td valign="top">

String



</td>
<td valign="top">

n/a



</td>
<td valign="top">

yes



</td>
</tr>
<tr>
<td valign="top" colspan="2">

`extends`



</td>
<td valign="top">

Used in MTA extension descriptor to denote which MTA deployment descriptor should be extended. Applicable only in extension descriptors.



</td>
<td valign="top">

String



</td>
<td valign="top">

The ID of the deployment descriptor that is to be extended



</td>
<td valign="top">

yes



</td>
</tr>
<tr>
<td valign="top" colspan="2">

`version`



</td>
<td valign="top">

Version of the current Multitarget Application. The format of the version is a numeric string of **`<major>.<minor>.<micro>`**

> ### Note:  
> The value must not exceed 64 symbols.



</td>
<td valign="top">

Enclosed String, use single quotes



</td>
<td valign="top">

n/a



</td>
<td valign="top">

yes



</td>
</tr>
<tr>
<td valign="top" rowspan="4">

`parameters:`



</td>
<td valign="top">

`hcp-deployer-version`



</td>
<td valign="top">

Version of the deploy service of the \(SAP BTP\) . This version differs from the schema version. The current supported versions are:

-   `1.0.0`
-   `1.1.0`
-   `1.2.0`

> ### Note:  
> -   Deployer version `1.0.0` is going to be deprecated. Use version `1.1.0` and higher.
> -   During a solution update, a different technical approach is employed. For more information, see [General Information About Solution Updates](general-information-about-solution-updates-2b1c4ed.md).



</td>
<td valign="top">

Enclosed String, use single quotes



</td>
<td valign="top">

n/a



</td>
<td valign="top">

yes



</td>
</tr>
<tr>
<td valign="top">

`title`



</td>
<td valign="top">

Human-readable title of the application.



</td>
<td valign="top">

The ID of the Multitarget Application



</td>
<td valign="top">

n/a



</td>
<td valign="top">

no



</td>
</tr>
<tr>
<td valign="top">

`description`



</td>
<td valign="top">

Human-readable description of the application.



</td>
<td valign="top">

String



</td>
<td valign="top">

n/a



</td>
<td valign="top">

no



</td>
</tr>
<tr>
<td valign="top">

`logo`



</td>
<td valign="top">

Base64-encoded logotype image. Optimize your image to be displayed for size 45x45 pixels. The supported formats are:

-   png
-   jpeg
-   gif

The following syntax is for a `.png` logotype that has been encoded in Base64:

> ### Example:  
> ```
> logo: "data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAFoAAABaCAMAAAAPdrEwAAAAnFBMVEX///..."
> ```



</td>
<td valign="top">

String



</td>
<td valign="top">

n/a



</td>
<td valign="top">

no



</td>
</tr>
</table>



<a name="loiof1caa871360c40e7be7ce4264ab9c336__section_xzh_p13_mz"/>

## Supported Multitarget Application Module Types

This section contains the modules that are supported by the SAP BTP and their parameters and properties.

> ### Note:  
> -   The relation between a module and the entities created in the SAP BTP is not one-to-one, that is, it is possible for one module to contain several SAP BTP entities and vice versa.
> -   Any security-sensitive data, such as user credentials and passwords, has to be placed in the MTA extension descriptor.



<a name="loiof1caa871360c40e7be7ce4264ab9c336__section_rjm_v23_mz"/>

## Supported Module Types and Parameters

> ### Tip:  
> Expand the following subsections by clicking on the arrow-shaped element to see the available parameters and values.

The following module types are currently supported:



### `com.sap.hcp.html5` - used for deploying HTML5 applications


<table>
<tr>
<th valign="top">

Supported Parameter



</th>
<th valign="top">

Parameter Description



</th>
<th valign="top">

Type



</th>
<th valign="top">

Default Value



</th>
<th valign="top">

Mandatory



</th>
</tr>
<tr>
<td valign="top">

`name`



</td>
<td valign="top">

HTML5 application name, which has to be unique within the current subaccount.



</td>
<td valign="top">

String



</td>
<td valign="top">

n/a



</td>
<td valign="top">

yes



</td>
</tr>
<tr>
<td valign="top">

`display-name`



</td>
<td valign="top">

Human-readable name of the application.

> ### Note:  
> The `display-name` and `name` parameters belong to an application level that is different from the one of the application versions. If another application version is defined in the MTA deployment descriptor, then its display name has to be identical to display names of other already defined versions of the application or has to be omitted.



</td>
<td valign="top">

String



</td>
<td valign="top">

n/a



</td>
<td valign="top">

no



</td>
</tr>
<tr>
<td valign="top">

`version`



</td>
<td valign="top">

Application version to be used in the HTML5 runtime. Used for deploying Java HTML5 modules with the same version can be deployed only once. In the `version` parameter, the usage of a *<timestamp\>* read-only variable is supported. Thus, a new version string is generated with every deploy. For example, version: `'0.1.0-${timestamp}'` 



</td>
<td valign="top">

String



</td>
<td valign="top">

n/a



</td>
<td valign="top">

yes



</td>
</tr>
<tr>
<td valign="top">

`active`



</td>
<td valign="top">

This flag indicates whether the related version of the application should be activated or not. The default value is `true`.



</td>
<td valign="top">

Boolean



</td>
<td valign="top">

`true`



</td>
<td valign="top">

no



</td>
</tr>
<tr>
<td valign="top">

`description`



</td>
<td valign="top">

Application description.



</td>
<td valign="top">

String



</td>
<td valign="top">

n/a



</td>
<td valign="top">

no



</td>
</tr>
<tr>
<td valign="top">

`subscribe`



</td>
<td valign="top">

When a provided solution is consumed, а subscription and designated entities might be created in the consumer subaccount, unless the parameter is set to `false`.



</td>
<td valign="top">

Boolean



</td>
<td valign="top">

`true`



</td>
<td valign="top">

no



</td>
</tr>
<tr>
<td valign="top">

`sfsf-idp-access` 



</td>
<td valign="top">

If true, the extension application is registered as an authorized assertion consumer service for the SAP SuccessFactors system to enable the application to use the SAP SuccessFactors identity provider \(IdP\) for authentication.



</td>
<td valign="top">

Boolean



</td>
<td valign="top">

`false`



</td>
<td valign="top">

no



</td>
</tr>
<tr>
<td valign="top">

`sfsf-home-page-tiles`



</td>
<td valign="top">

Registers SAP SuccessFactors Employee Central \(EC\) home page tiles in the SAP SuccessFactors company instance.

This parameter is a YAML dictionary with one element with key `resource` and value `<path to resource>`. The resource is a descriptor file that defines the SAP SuccessFactors tiles. The resource has to be in JSON format.

For more information, see [Home Page Tiles JSON File](../40-extensions-neo/home-page-tiles-json-file-872d124.md). Ensure that each tile `name` is unique within the current subaccount.



</td>
<td valign="top">

Binary



</td>
<td valign="top">

n/a



</td>
<td valign="top">

no



</td>
</tr>
<tr>
<td valign="top">

`permissions`



</td>
<td valign="top">

HTML5 role assignment to specified permissions.

The parameter is applicable for both a standard HTML5 application, as well as for subscribing to one as a consumer.

-   `name` - name of the permission
-   `role` - the role to which the permission is assigned to



</td>
<td valign="top">

List



</td>
<td valign="top">

n/a



</td>
<td valign="top">

no



</td>
</tr>
</table>



### `com.sap.java` - used for deploying Java applications with the full Java EE 7 Web Profile container.

For more information about runtime containers, see [Application Runtime Container](application-runtime-container-7613bd2.md).


<table>
<tr>
<th valign="top">

Supported Parameter



</th>
<th valign="top">

Parameter Description



</th>
<th valign="top">

Type



</th>
<th valign="top">

Default Value



</th>
<th valign="top">

Mandatory



</th>
</tr>
<tr>
<td valign="top">

`name`



</td>
<td valign="top">

Java application name, which has to be unique within the current subaccount. The `name` value length has to be between 1 and 255 symbols.



</td>
<td valign="top">

String



</td>
<td valign="top">

n/a



</td>
<td valign="top">

yes



</td>
</tr>
<tr>
<td valign="top">

`runtime`



</td>
<td valign="top">

Only runtime `neo-javaee7-wp` is supported.



</td>
<td valign="top">

String



</td>
<td valign="top">

`neo-javaee7-wp`



</td>
<td valign="top">

no



</td>
</tr>
<tr>
<td valign="top">

`runtime-version`



</td>
<td valign="top">

Only runtime version `1` is supported.



</td>
<td valign="top">

Enclosed String, use single quotes



</td>
<td valign="top">

`1`



</td>
<td valign="top">

no



</td>
</tr>
<tr>
<td valign="top">

`java-version`



</td>
<td valign="top">

Only java version `JRE 8` is supported.



</td>
<td valign="top">

String



</td>
<td valign="top">

`JRE 8`



</td>
<td valign="top">

no



</td>
</tr>
<tr>
<td valign="top">

`compute-unit-size`



</td>
<td valign="top">

The virtual machine computing unit size. The available sizes are `LITE`, `PRO`, `PREMIUM`, `PREMIUM_PLUS`. For more information, see [Compute Units](compute-units-7612fba.md).



</td>
<td valign="top">

String



</td>
<td valign="top">

`LITE`



</td>
<td valign="top">

no



</td>
</tr>
<tr>
<td valign="top">

`minimum-processes`



</td>
<td valign="top">

Minimum number of process instances. The allowed range is from `1` to `99`.

> ### Note:  
> -   You either have to use both the `minimum-processes` and `maximum-processes` parameters, or neither.
> -   The `minimum-processes` should be equal to or lower than the `maximum-processes` value.



</td>
<td valign="top">

Integer



</td>
<td valign="top">

`1`



</td>
<td valign="top">

no



</td>
</tr>
<tr>
<td valign="top">

`maximum-processes`



</td>
<td valign="top">

Maximum number of process instances. The allowed range is from `1` to `99`.

> ### Note:  
> -   You either have to use both the `minimum-processes` and `maximum-processes` parameters, or neither.
> -   The `maximum-processes` should be equal to or higher than the `minimum-processes` value.



</td>
<td valign="top">

Integer



</td>
<td valign="top">

`1`



</td>
<td valign="top">

no



</td>
</tr>
<tr>
<td valign="top">

`rolling-update`



</td>
<td valign="top">

Performs update of an application without downtime in one go.

> ### Note:  
> At least `hcp-deployer-version` 1.2.0 is required.



</td>
<td valign="top">

Boolean



</td>
<td valign="top">

`false`



</td>
<td valign="top">

no



</td>
</tr>
<tr>
<td valign="top">

`rolling-update-timeout`



</td>
<td valign="top">

Defines how long the old process will be disabled before it is stopped.

> ### Note:  
> At least `hcp-deployer-version` 1.2.0 is required.



</td>
<td valign="top">

Integer



</td>
<td valign="top">

`60`



</td>
<td valign="top">

no



</td>
</tr>
<tr>
<td valign="top">

`running-processes`



</td>
<td valign="top">

Specifies how many processes will run at the end of the state of the Java application. If not specified, the minimum number is used.



</td>
<td valign="top">

Integer



</td>
<td valign="top">

n/a



</td>
<td valign="top">

no



</td>
</tr>
<tr>
<td valign="top">

`jvm-arguments`



</td>
<td valign="top">

The relevant JVM arguments employed by the customer application.



</td>
<td valign="top">

String



</td>
<td valign="top">

n/a



</td>
<td valign="top">

no



</td>
</tr>
<tr>
<td valign="top">

`max-threads`



</td>
<td valign="top">

The maximum allowed number of threads.



</td>
<td valign="top">

Integer



</td>
<td valign="top">

`200`



</td>
<td valign="top">

no



</td>
</tr>
<tr>
<td valign="top">

`connection-timeout`



</td>
<td valign="top">

The maximum timeout period for the connection, in milliseconds.



</td>
<td valign="top">

Integer



</td>
<td valign="top">

`20000`



</td>
<td valign="top">

no



</td>
</tr>
<tr>
<td valign="top">

`encoding`



</td>
<td valign="top">

The used Uniform Resource Identifier \(URI\) encoding standard.



</td>
<td valign="top">

String



</td>
<td valign="top">

`ISO-8859-1`



</td>
<td valign="top">

no



</td>
</tr>
<tr>
<td valign="top">

`compression`



</td>
<td valign="top">

The use of gzip compression for optimizing HTTP response time between the Web server and its clients. The available values are `on`, `off`, `forced`.

> ### Note:  
> Explicitly specify the `compression-mime-types` and `compression-min-size` parameters only when you use the value `on`.



</td>
<td valign="top">

String



</td>
<td valign="top">

`off`



</td>
<td valign="top">

no



</td>
</tr>
<tr>
<td valign="top">

`compression-mime-types`



</td>
<td valign="top">

The used compression mime type, for example `text/json text/xml text/html`



</td>
<td valign="top">

String



</td>
<td valign="top">

n/a



</td>
<td valign="top">

no



</td>
</tr>
<tr>
<td valign="top">

`compression-min-size`



</td>
<td valign="top">

The threshold size above which an HTTP response package is compressed to reduce traffic.



</td>
<td valign="top">

Integer



</td>
<td valign="top">

n/a



</td>
<td valign="top">

no



</td>
</tr>
<tr>
<td valign="top">

`role-provider` 



</td>
<td valign="top">

Defines the application that provides the role for the Java application. Use one of the following:

-   `sfsf`
-   `hcp`



</td>
<td valign="top">

String



</td>
<td valign="top">

n/a



</td>
<td valign="top">

no



</td>
</tr>
<tr>
<td valign="top">

`roles` 



</td>
<td valign="top">

Maps predefined Java application roles to the groups they have to be assigned to. It has to specify the following parameters:

-   `name` - its value has to be the name of the role
-   `groups` - its value has to be a list of group names to which the role is assigned to



</td>
<td valign="top">

List



</td>
<td valign="top">

n/a



</td>
<td valign="top">

no



</td>
</tr>
<tr>
<td valign="top">

`subscribe`



</td>
<td valign="top">

When a provided solution is consumed, а subscription and designated entities might be created in the consumer subaccount, unless the parameter is set to `false`.



</td>
<td valign="top">

Boolean



</td>
<td valign="top">

`true`



</td>
<td valign="top">

no



</td>
</tr>
<tr>
<td valign="top">

`sfsf-idp-access` 



</td>
<td valign="top">

If true, the extension application is registered as an authorized assertion consumer service for the SAP SuccessFactors system to enable the application to use the SAP SuccessFactors identity provider \(IdP\) for authentication.



</td>
<td valign="top">

Boolean



</td>
<td valign="top">

`false`



</td>
<td valign="top">

no



</td>
</tr>
<tr>
<td valign="top">

`sfsf-connections` 



</td>
<td valign="top">

Use this to configure the connectivity of a Java extension application to an SAP SuccessFactors system. It creates the required HTTP destination and registers an OAuth client for the Java application in SAP SuccessFactors.

> ### Note:  
> Note that SFSF connections can only be created after the corresponding Java application has been deployed and started. This means that an `sfsf-connections` module depends on a `com.sap.java` module.

-   You can create connections to one or more applications, and employ one or more connection types.
-   Registers the SAP SuccessFactors Employee Central \(EC\) home page. Note that existing SAP Fiori custom roles are skipped during deployment.

The `sfsf-connections` parameter is a YAML list comprised of entries with the following attributes:

-   `type` - values can be `default` or `technical-user`. Note that if you choose `default`, you cannot define a `technical-user-id`.
-   `sfsf-module` - possible value is `BizX` \(default value\) . Use this parameter to configure a connection to the SAP SuccessFactors BizX Suite.
-   `additional-properties` - any additional properties defining the connection, specified as name-value pairs.
-   `technical-user-id` - if you use the `technical-user` value for the `type` parameter, you have to define a technical user ID.

You can create more than one SAP SuccessFactors connections.

For a comprehensive example of a `sfsf-connections`, see [Modeling SAP SuccessFactors Extensions](modeling-sap-successfactors-extensions-ec35793.md).



</td>
<td valign="top">

List



</td>
<td valign="top">

n/a



</td>
<td valign="top">

no



</td>
</tr>
<tr>
<td valign="top">

`sfsf-home-page-tiles`



</td>
<td valign="top">

Registers SAP SuccessFactors Employee Central \(EC\) home page tiles in the SAP SuccessFactors company instance.

This parameter is a YAML dictionary with one element with key `resource` and value `<path to resource>`. The resource is a descriptor file that defines the SAP SuccessFactors tiles. The resource has to be in JSON format.

For more information, see [Home Page Tiles JSON File](../40-extensions-neo/home-page-tiles-json-file-872d124.md). Ensure that each tile `name` is unique within the current subaccount.



</td>
<td valign="top">

Binary



</td>
<td valign="top">

n/a



</td>
<td valign="top">

no



</td>
</tr>
<tr>
<td valign="top">

`destinations` 



</td>
<td valign="top">

This parameter is a YAML list comprised of one or more connectivity destinations. To see the available parameters and values, see the table “Destination Parameters” below.

> ### Note:  
> -   If you have sensitive data, all destination parameters have to be moved to the MTA extension descriptor.
> -   When you redeploy a destination, any parameter changes performed after deployment of the destination are removed. Your custom changes have to be performed again.



</td>
<td valign="top">

List



</td>
<td valign="top">

n/a



</td>
<td valign="top">

no



</td>
</tr>
</table>



### `java.tomcat` - used for deploying Java applications with the Java Web Tomcat runtime container.

For more information about runtime containers, see [Application Runtime Container](application-runtime-container-7613bd2.md).


<table>
<tr>
<th valign="top">

Supported Parameter



</th>
<th valign="top">

Parameter Description



</th>
<th valign="top">

Type



</th>
<th valign="top">

Default Value



</th>
<th valign="top">

Mandatory



</th>
</tr>
<tr>
<td valign="top">

`name`



</td>
<td valign="top">

Java application name, which has to be unique within the current subaccount. The `name` value length has to be between 1 and 255 symbols.



</td>
<td valign="top">

String



</td>
<td valign="top">

n/a



</td>
<td valign="top">

yes



</td>
</tr>
<tr>
<td valign="top">

`runtime-version`



</td>
<td valign="top">

If defining a specific runtime version is required, use one of the following:

-   `3` \(Tomcat 8\).
-   `4` \(Tomcat 9\).



</td>
<td valign="top">

Enclosed String, use single quotes



</td>
<td valign="top">

`3`



</td>
<td valign="top">

no



</td>
</tr>
<tr>
<td valign="top">

`java-version`



</td>
<td valign="top">

If defining a specific `java-version` is required, use one of the following:

-   `JRE 8` \(default\).
-   `JRE 17` \(in `runtime-version` 4.16 or higher\).
-   `JRE 11` \(in `runtime-version` 4.15 or lower\).



</td>
<td valign="top">

String



</td>
<td valign="top">

`JRE 8`



</td>
<td valign="top">

no



</td>
</tr>
<tr>
<td valign="top">

`compute-unit-size`



</td>
<td valign="top">

The virtual machine computing unit size. The available sizes are `LITE`, `PRO`, `PREMIUM`, `PREMIUM_PLUS`. For more information, see [Compute Units](compute-units-7612fba.md).



</td>
<td valign="top">

String



</td>
<td valign="top">

`LITE`



</td>
<td valign="top">

no



</td>
</tr>
<tr>
<td valign="top">

`minimum-processes`



</td>
<td valign="top">

Minimum number of process instances. The allowed range is from `1` to `99`.

> ### Note:  
> -   You either have to use both the `minimum-processes` and `maximum-processes` parameters, or neither
> -   The `minimum-processes` should be equal to or lower than the `maximum-processes` value.



</td>
<td valign="top">

Integer



</td>
<td valign="top">

`1`



</td>
<td valign="top">

no



</td>
</tr>
<tr>
<td valign="top">

`maximum-processes`



</td>
<td valign="top">

Maximum number of process instances. The allowed range is from `1` to `99`.

> ### Note:  
> -   You either have to use both the `minimum-processes` and `maximum-processes` parameters, or neither.
> -   The `maximum-processes` should be equal to or higher than the `minimum-processes` value.



</td>
<td valign="top">

Integer



</td>
<td valign="top">

`1`



</td>
<td valign="top">

no



</td>
</tr>
<tr>
<td valign="top">

`rolling-update`



</td>
<td valign="top">

Performs update of an application without downtime in one go.

> ### Note:  
> At least `hcp-deployer-version` 1.2.0 is required.



</td>
<td valign="top">

Boolean



</td>
<td valign="top">

`false`



</td>
<td valign="top">

no



</td>
</tr>
<tr>
<td valign="top">

`rolling-update-timeout`



</td>
<td valign="top">

Defines how long the old process will be disabled before it is stopped.

> ### Note:  
> At least `hcp-deployer-version` 1.2.0 is required.



</td>
<td valign="top">

Integer



</td>
<td valign="top">

`60`



</td>
<td valign="top">

no



</td>
</tr>
<tr>
<td valign="top">

`running-processes`



</td>
<td valign="top">

Specifies how many processes will run at the end of the state of the Java application. If not specified, the minimum number is used.



</td>
<td valign="top">

Integer



</td>
<td valign="top">

n/a



</td>
<td valign="top">

no



</td>
</tr>
<tr>
<td valign="top">

`jvm-arguments`



</td>
<td valign="top">

The relevant JVM arguments employed by the customer application.



</td>
<td valign="top">

String



</td>
<td valign="top">

n/a



</td>
<td valign="top">

no



</td>
</tr>
<tr>
<td valign="top">

`max-threads`



</td>
<td valign="top">

The maximum allowed number of threads.



</td>
<td valign="top">

Integer



</td>
<td valign="top">

`200`



</td>
<td valign="top">

no



</td>
</tr>
<tr>
<td valign="top">

`connection-timeout`



</td>
<td valign="top">

The maximum timeout period for the connection, in milliseconds.



</td>
<td valign="top">

Integer



</td>
<td valign="top">

`20000`



</td>
<td valign="top">

no



</td>
</tr>
<tr>
<td valign="top">

`encoding`



</td>
<td valign="top">

The used Uniform Resource Identifier \(URI\) encoding standard.



</td>
<td valign="top">

String



</td>
<td valign="top">

`ISO-8859-1`



</td>
<td valign="top">

no



</td>
</tr>
<tr>
<td valign="top">

`compression`



</td>
<td valign="top">

The use of gzip compression for optimizing HTTP response time between the Web server and its clients. The available values are `on`, `off`, `forced`.

> ### Note:  
> Explicitly specify the `compression-mime-types` and `compression-min-size` parameters only when you use the value `on`.



</td>
<td valign="top">

String



</td>
<td valign="top">

`off`



</td>
<td valign="top">

no



</td>
</tr>
<tr>
<td valign="top">

`compression-mime-types`



</td>
<td valign="top">

The used compression mime type, for example `text/json text/xml text/html`



</td>
<td valign="top">

String



</td>
<td valign="top">

n/a



</td>
<td valign="top">

no



</td>
</tr>
<tr>
<td valign="top">

`compression-min-size`



</td>
<td valign="top">

The threshold size above which an HTTP response package is compressed to reduce traffic.



</td>
<td valign="top">

Integer



</td>
<td valign="top">

n/a



</td>
<td valign="top">

no



</td>
</tr>
<tr>
<td valign="top">

`role-provider` 



</td>
<td valign="top">

Defines the application that provides the role for the Java application. Use one of the following:

-   `sfsf`
-   `hcp`



</td>
<td valign="top">

String



</td>
<td valign="top">

n/a



</td>
<td valign="top">

no



</td>
</tr>
<tr>
<td valign="top">

`roles` 



</td>
<td valign="top">

Maps predefined Java application roles to the groups they have to be assigned to. It has to specify the following parameters:

-   `name` - its value has to be the name of the role
-   `groups` - its value has to be a list of group names to which the role is assigned to



</td>
<td valign="top">

List



</td>
<td valign="top">

n/a



</td>
<td valign="top">

no



</td>
</tr>
<tr>
<td valign="top">

`subscribe`



</td>
<td valign="top">

When a provided solution is consumed, а subscription and designated entities might be created in the consumer subaccount, unless the parameter is set to `false`.



</td>
<td valign="top">

Boolean



</td>
<td valign="top">

`true`



</td>
<td valign="top">

no



</td>
</tr>
<tr>
<td valign="top">

`sfsf-idp-access` 



</td>
<td valign="top">

If true, the extension application is registered as an authorized assertion consumer service for the SAP SuccessFactors system to enable the application to use the SAP SuccessFactors identity provider \(IdP\) for authentication.



</td>
<td valign="top">

Boolean



</td>
<td valign="top">

`false`



</td>
<td valign="top">

no



</td>
</tr>
<tr>
<td valign="top">

`sfsf-connections` 



</td>
<td valign="top">

Use this to configure the connectivity of a Java extension application to an SAP SuccessFactors system. It creates the required HTTP destination and registers an OAuth client for the Java application in SAP SuccessFactors.

> ### Note:  
> Note that SFSF connections can only be created after the corresponding Java application has been deployed and started. This means that an `sfsf-connections` module depends on a `com.sap.java` module.

-   You can create connections to one or more applications, and employ one or more connection types.
-   Registers the SAP SuccessFactors Employee Central \(EC\) home page. Note that existing SAP Fiori custom roles are skipped during deployment.

The `sfsf-connections` parameter is a YAML list comprised of entries with the following attributes:

-   `type` - values can be `default` or `technical-user`. Note that if you choose `default`, you cannot define a `technical-user-id`.
-   `sfsf-module` - possible value is `BizX` \(default value\) . Use this parameter to configure a connection to the SAP SuccessFactors BizX Suite.
-   `additional-properties` - any additional properties defining the connection, specified as name-value pairs.
-   `technical-user-id` - if you use the `technical-user` value for the `type` parameter, you have to define a technical user ID.

You can create more than one SAP SuccessFactors connections.

For a comprehensive example of a `sfsf-connections`, see [Modeling SAP SuccessFactors Extensions](modeling-sap-successfactors-extensions-ec35793.md).



</td>
<td valign="top">

List



</td>
<td valign="top">

n/a



</td>
<td valign="top">

no



</td>
</tr>
<tr>
<td valign="top">

`sfsf-home-page-tiles`



</td>
<td valign="top">

Registers SAP SuccessFactors Employee Central \(EC\) home page tiles in the SAP SuccessFactors company instance.

This parameter is a YAML dictionary with one element with key `resource` and value `<path to resource>`. The resource is a descriptor file that defines the SAP SuccessFactors tiles. The resource has to be in JSON format.

For more information, see [Home Page Tiles JSON File](../40-extensions-neo/home-page-tiles-json-file-872d124.md). Ensure that each tile `name` is unique within the current subaccount.



</td>
<td valign="top">

Binary



</td>
<td valign="top">

n/a



</td>
<td valign="top">

no



</td>
</tr>
<tr>
<td valign="top">

`destinations` 



</td>
<td valign="top">

This parameter is a YAML list comprised of one or more connectivity destinations. To see the available parameters and values, see the table “Destination Parameters” below.

> ### Note:  
> -   If you have sensitive data, all destination parameters have to be moved to the MTA extension descriptor.
> -   When you redeploy a destination, any parameter changes performed after deployment of the destination are removed. Your custom changes have to be performed again.



</td>
<td valign="top">

List



</td>
<td valign="top">

n/a



</td>
<td valign="top">

no



</td>
</tr>
</table>



### `com.sap.fiori` - used for deploying SAP Fiori configurations


<table>
<tr>
<th valign="top">

Supported Parameter



</th>
<th valign="top">

Parameter Description



</th>
<th valign="top">

Type



</th>
<th valign="top">

Default Value



</th>
<th valign="top">

Mandatory



</th>
</tr>
<tr>
<td valign="top">

`owner`



</td>
<td valign="top">

Indicates in which subaccount the content should be imported. The possible values are `provider` or `consumer`.



</td>
<td valign="top">

String



</td>
<td valign="top">

`provider`



</td>
<td valign="top">

no



</td>
</tr>
<tr>
<td valign="top">

`mta-id`



</td>
<td valign="top">

The same as the global ID.

> ### Note:  
> -   To reduce the risk of being out of sync, we recommend that you use YAML anchors.
> -   The value must not exceed 64 symbols.



</td>
<td valign="top">

String



</td>
<td valign="top">

n/a



</td>
<td valign="top">

no



</td>
</tr>
<tr>
<td valign="top">

`mta-version`



</td>
<td valign="top">

The same as the global version.

> ### Note:  
> -   To reduce the risk of being out of sync, we recommend that you use YAML anchors.
> -   The value must not exceed 64 symbols.



</td>
<td valign="top">

Enclosed String

> ### Note:  
> Use single quotes.



</td>
<td valign="top">

n/a



</td>
<td valign="top">

no



</td>
</tr>
<tr>
<td valign="top">

`back-end-ppms-product-version-id`



</td>
<td valign="top">

ID of the PPMS product version backend.



</td>
<td valign="top">

Enclosed String

> ### Note:  
> Use single quotes.



</td>
<td valign="top">

n/a



</td>
<td valign="top">

no



</td>
</tr>
<tr>
<td valign="top">

`back-end-ppms-support-package-stack-id`



</td>
<td valign="top">

ID of the PPMS support-package stack backend



</td>
<td valign="top">

Enclosed String

> ### Note:  
> Use single quotes.



</td>
<td valign="top">

n/a



</td>
<td valign="top">

no



</td>
</tr>
<tr>
<td valign="top">

`back-end-cross-product-stack-id`



</td>
<td valign="top">

ID of the cross product stack backend



</td>
<td valign="top">

Enclosed String

> ### Note:  
> Use single quotes.



</td>
<td valign="top">

n/a



</td>
<td valign="top">

no



</td>
</tr>
<tr>
<td valign="top">

`back-end-cross-product-stack-solution-id`



</td>
<td valign="top">

ID of the cross product stack solution backend



</td>
<td valign="top">

Enclosed String

> ### Note:  
> Use single quotes.



</td>
<td valign="top">

n/a



</td>
<td valign="top">

no



</td>
</tr>
<tr>
<td valign="top">

`release`



</td>
<td valign="top">

If it is set to `true`, it marks a released product.



</td>
<td valign="top">

Boolean



</td>
<td valign="top">

`false`



</td>
<td valign="top">

no



</td>
</tr>
<tr>
<td valign="top">

`target-site-id`



</td>
<td valign="top">

It specifies the target site in which the content will be deployed.



</td>
<td valign="top">

String



</td>
<td valign="top">

n/a



</td>
<td valign="top">

no



</td>
</tr>
<tr>
<td valign="top">

`minimum-sapui5-version`



</td>
<td valign="top">

Version of the minimum required SAPUI5 Runtime. The format of the version is a numeric string of `<major>.<minor>` or `<major>.<minor>.<micro>`



</td>
<td valign="top">

Enclosed String

> ### Note:  
> Use single quotes.



</td>
<td valign="top">

n/a



</td>
<td valign="top">

no



</td>
</tr>
</table>

> ### Note:  
> You have to ensure that the `back-end-*-id` parameter values are numeric strings of exactly 20 digits.



### `com.sap.fiori.app` - used for deploying SAP Fiori applications


<table>
<tr>
<th valign="top">

Supported Parameter



</th>
<th valign="top">

Parameter Description



</th>
<th valign="top">

Type



</th>
<th valign="top">

Default Value



</th>
<th valign="top">

Mandatory



</th>
</tr>
<tr>
<td valign="top">

`html5-app-name`



</td>
<td valign="top">

SAP Fiori application name, which has to be unique within the current subaccount.



</td>
<td valign="top">

String



</td>
<td valign="top">

n/a



</td>
<td valign="top">

yes



</td>
</tr>
<tr>
<td valign="top">

`html5-app-display-name`



</td>
<td valign="top">

Human-readable name of the application.

> ### Note:  
> The `html5-app-display-name` and `html5-app-name` parameters belong to an application level that is different from the one of the application versions. If another application version is defined in the MTA deployment descriptor, then its display name has to be identical to display names of other already defined versions of the application or has to be omitted.



</td>
<td valign="top">

String



</td>
<td valign="top">

n/a



</td>
<td valign="top">

no



</td>
</tr>
<tr>
<td valign="top">

`html5-app-version`



</td>
<td valign="top">

SAP Fiori application version

> ### Note:  
> The same rules apply as for the `sap.com.hcp.html5 version` parameter with the difference that this parameter is optional. Default value: `'${timestamp}'` 



</td>
<td valign="top">

String



</td>
<td valign="top">

`${timestamp}`



</td>
<td valign="top">

no



</td>
</tr>
<tr>
<td valign="top">

`html5-app-active`



</td>
<td valign="top">

This flag indicates whether the related version of the application should be activated or not. The default value is `true`.



</td>
<td valign="top">

Boolean



</td>
<td valign="top">

`true`



</td>
<td valign="top">

no



</td>
</tr>
<tr>
<td valign="top">

`html5-app-permissions`



</td>
<td valign="top">

HTML5 role assignment to specified permissions.

The parameter is applicable for both an HTML5 standard application, as well as for subscribing as a consumer.

-   `name` - name of the permission
-   `role` - the role to which the permission is assigned to



</td>
<td valign="top">

List



</td>
<td valign="top">

n/a



</td>
<td valign="top">

no



</td>
</tr>
</table>



### `com.sap.fiori.role` - used for deploying custom SAP Fiori roles


<table>
<tr>
<th valign="top">

Supported Parameter



</th>
<th valign="top">

Parameter Description



</th>
<th valign="top">

Type



</th>
<th valign="top">

Default Value



</th>
<th valign="top">

Mandatory



</th>
</tr>
<tr>
<td valign="top">

`name`



</td>
<td valign="top">

SAP Fiori custom role name, which has to be unique within the current subaccount. The `name` value length has to be between 1 and 255 symbols.



</td>
<td valign="top">

String



</td>
<td valign="top">

n/a



</td>
<td valign="top">

yes



</td>
</tr>
<tr>
<td valign="top">

`groups`



</td>
<td valign="top">

List of group names to which the role has to be assigned.



</td>
<td valign="top">

List



</td>
<td valign="top">

n/a



</td>
<td valign="top">

no



</td>
</tr>
</table>

For more information, see [Role Assignment of Fiori Roles to Security Groups](role-assignment-of-fiori-roles-to-security-groups-6a012da.md).



### `com.sap.hcp.html5.role` - used for deploying custom HTML5 application roles


<table>
<tr>
<th valign="top">

Supported Parameter



</th>
<th valign="top">

Parameter Description



</th>
<th valign="top">

Type



</th>
<th valign="top">

Default Value



</th>
<th valign="top">

Mandatory



</th>
</tr>
<tr>
<td valign="top">

`name`



</td>
<td valign="top">

HTML5 application custom role name, which has to be unique within the current subaccount. The `name` value length has to be between 1 and 255 symbols.



</td>
<td valign="top">

String



</td>
<td valign="top">

n/a



</td>
<td valign="top">

yes



</td>
</tr>
<tr>
<td valign="top">

`groups`



</td>
<td valign="top">

List of group names to which the role has to be assigned.



</td>
<td valign="top">

List



</td>
<td valign="top">

n/a



</td>
<td valign="top">

no



</td>
</tr>
</table>

For more information, see [Role Assignment of HTML 5 Roles to Security Groups](role-assignment-of-html-5-roles-to-security-groups-43edba2.md).



### `com.sap.odp.config` - used for deploying OData Provisioning configuration

> ### Remember:  
> The use of this module type with parameters valid for `hcp-deployer-version: '1.0.0'` will soon be de-supported. We recommend that you use the parameters valid for `hcp-deployer-version: '1.1.0'`, or adapt your module type accordingly.

-   Supported parameters when used with `hcp-deployer-version: '1.0.0'`

    > ### Remember:  
    > This deployer version will soon be de-supported. We recommend you use `1.1.0`.


    <table>
    <tr>
    <th valign="top">

    Supported Parameter


    
    </th>
    <th valign="top">

    Parameter Description


    
    </th>
    <th valign="top">

    Type


    
    </th>
    <th valign="top">

    Default Value


    
    </th>
    <th valign="top">

    Mandatory


    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
        `metadata-validation-setting`


    
    </td>
    <td valign="top">
    
        Enable or disable metadata validation, for example `true`.


    
    </td>
    <td valign="top">
    
        Boolean


    
    </td>
    <td valign="top">
    
        n/a


    
    </td>
    <td valign="top">
    
        yes


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
        `metadata-cache-setting`


    
    </td>
    <td valign="top">
    
        Enable or disable metadata cache, for example `false`.


    
    </td>
    <td valign="top">
    
        Boolean


    
    </td>
    <td valign="top">
    
        n/a


    
    </td>
    <td valign="top">
    
        yes


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
        `services`


    
    </td>
    <td valign="top">
    
        List of OData services. Parameters required for an OData service are:

    -   `name` - name of the service from the SAP on-premise back-end system that needs to be registered, for example `EPM_DEVELOPER_SCENARIO_SRV`. This name has to be unique within the current subaccount.
    -   `namespace` - namespace for the above service being registered from the SAP on-premise back-end system, for example `IWBEP`
    -   `version` - version of service being registered from the SAP on-premise back-end system, for example `1`
    -   `description` - description of the service being registered, for example `/IWBEP/CL_EPM_DEVELOPE_DPC_EXT`
    -   `initial-status` - status of the service registered in the OData Provisioning Administration cockpit that is set during the initial deployment of the OData service, whether it is active or inactive, for example `true`
    -   `overwrite-existing` - this flag declares whether an existing OData service is going to be updated or not, for example `false`
    -   `model-id` - the model ID corresponding to the metadata of the service being registered, for example `/IWBEP/EPM_DEVELOPER_SCENARIO_MD_0001`
    -   `initial-default-destination` - the SAP on-premise back-end system destination where the service exists that is set during the initial deployment of the OData service. `Default` means that if the service does not specify any origin in the URL, then the metadata and data requests are going to be fulfilled from the destination mentioned against `initial-default-destination`, for example `AP2`.


    
    </td>
    <td valign="top">
    
        List


    
    </td>
    <td valign="top">
    
        n/a


    
    </td>
    <td valign="top">
    
        yes


    
    </td>
    </tr>
    </table>
    
-   Supported parameters when used with `hcp-deployer-version: '1.1.0'`:


    <table>
    <tr>
    <th valign="top">

    Supported Parameter


    
    </th>
    <th valign="top">

    Parameter Description


    
    </th>
    <th valign="top">

    Type


    
    </th>
    <th valign="top">

    Default Value


    
    </th>
    <th valign="top">

    Mandatory


    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
        `metadata-validation-setting`


    
    </td>
    <td valign="top">
    
        Enable or disable metadata validation, for example `true`.


    
    </td>
    <td valign="top">
    
        Boolean


    
    </td>
    <td valign="top">
    
        n/a


    
    </td>
    <td valign="top">
    
        yes


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
        `metadata-cache-setting`


    
    </td>
    <td valign="top">
    
        Enable or disable metadata cache, for example `false`.


    
    </td>
    <td valign="top">
    
        Boolean


    
    </td>
    <td valign="top">
    
        n/a


    
    </td>
    <td valign="top">
    
        yes


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
        `services`


    
    </td>
    <td valign="top">
    
        List of OData services. Parameters required for an OData service are:

    -   `name` - name of the service from the SAP on-premise back-end system that needs to be registered, for example `EPM_DEVELOPER_SCENARIO_SRV`. This name has to be unique within the current subaccount.
    -   `namespace` - namespace for the above service being registered from the SAP on-premise back-end system, for example `IWBEP`
    -   `version` - version of service being registered from the SAP on-premise back-end system, for example `1`
    -   `status` - status of the service registered in the OData Provisioning Administration cockpit. To make the service active use `true`, or `false` to keep it inactive.
    -    `initial-description` – description of the service. For example `/IWBEP/CL_EPM_DEVELOPE_DPC_EXT`. Use only when the service is created for the first time.

        > ### Note:  
        > If a service with the same `name/namespace/version` combination already exists but has different description, the import will fail.

    -   `initial-model-id` - the model ID corresponding to the metadata of the service, for example `/IWBEP/EPM_DEVELOPER_SCENARIO_MD_0001`. Use only when the service is created for the first time.

        > ### Note:  
        > If a service with the same `name/namespace/version` combination already exists but has different `model-id`, the import will fail.

    -   `initial-default-destination` - the name of the default SAP on-premise back-end system destination that is going to be used by the OData Provisioning service when no-multi origin composition \(MOC\) is specified as a parameter in the OData URL. Use only when the service is created for the first time.

        > ### Note:  
        > If a service with the same `name/namespace/version` combination already exists but has different default destination, the import will fail.



    
    </td>
    <td valign="top">
    
        List


    
    </td>
    <td valign="top">
    
        n/a


    
    </td>
    <td valign="top">
    
        yes


    
    </td>
    </tr>
    </table>
    



### `com.sap.hcp.sfsf-roles` - used for uploading and importing SAP SuccessFactors HCM Suite roles from the SAP BTP system repository into the SAP SuccessFactors customer instance.

The role definitions must be described in a JSON file. For more information about creating `roles.json` file, see [Create the Resource File with Role Definitions](../40-extensions-neo/create-the-resource-file-with-role-definitions-93d5ce5.md).

Ensure that each role has a unique `roleName` within the current subaccount.



### `com.sap.hcp.group` - used for modeling the SAP BTP authorization groups.


<table>
<tr>
<th valign="top">

Supported Parameter



</th>
<th valign="top">

Parameter Description



</th>
<th valign="top">

Type



</th>
<th valign="top">

Default



</th>
<th valign="top">

Mandatory



</th>
</tr>
<tr>
<td valign="top">

`name`



</td>
<td valign="top">

Group name, which has to be unique within the current subaccount. The `name` value length has to be between 1 and 255 symbols.



</td>
<td valign="top">

String



</td>
<td valign="top">

n/a



</td>
<td valign="top">

yes



</td>
</tr>
</table>



### `com.sap.hcp.destination` - A generic subaccount-level destination.

To see the available parameters and values, see the table “Destination Parameters” below.



### `com.sap.hcp.portal.destination` - A service-level destination for theSAP Cloud Portal service.

To see the available parameters and values, see the table “Destination Parameters” below.



### `com.sap.hcp.odp.destination` - A service-level destination for the SAP OData Provisioning.

To see the available parameters and values, see the table “Destination Parameters” below.



### `com.sap.integration` - used for modeling the content for the SAP Cloud Integration.


<table>
<tr>
<th valign="top">

Supported Parameter



</th>
<th valign="top">

Parameter Description



</th>
<th valign="top">

Type



</th>
<th valign="top">

Default



</th>
<th valign="top">

Mandatory



</th>
</tr>
<tr>
<td valign="top">

`resource-type`



</td>
<td valign="top">

Type of the resource



</td>
<td valign="top">

String



</td>
<td valign="top">

n/a



</td>
<td valign="top">

yes



</td>
</tr>
<tr>
<td valign="top">

`resource-id`



</td>
<td valign="top">

ID of the resource



</td>
<td valign="top">

String



</td>
<td valign="top">

n/a



</td>
<td valign="top">

yes



</td>
</tr>
<tr>
<td valign="top">

`version` 



</td>
<td valign="top">

Version of the `com.sap.integration` module type



</td>
<td valign="top">

String



</td>
<td valign="top">

n/a



</td>
<td valign="top">

yes



</td>
</tr>
<tr>
<td valign="top">

`technical-name`



</td>
<td valign="top">

Technical name of the `com.sap.integration` module type



</td>
<td valign="top">

String



</td>
<td valign="top">

n/a



</td>
<td valign="top">

yes



</td>
</tr>
</table>

> ### Note:  
> To use the `com.sap.integration` module type, first you have to:
> 
> -   Enable the SAP Solution Lifecycle Management service for SAP BTP service in a subaccount that supports SAP Cloud Integration. For more information, see [Content Transport](https://help.sap.com/viewer/368c481cd6954bdfa5d0435479fd4eaf/Cloud/en-US/e3c79d65aa604b80992e20609881ad7a.html) in the SAP Cloud Integration documentation.
> -   Create a destination with named `CloudIntegration` with the following properties:
>     -   Type - ***HTTP***
>     -   URL - URL pointing to the `/itspaces` of the TMN node for the SAP Cloud Integration tenant in the current subaccount
>     -   Proxy Type - ***Internet***
>     -   Authentication - ***BasicAuthentication***
>     -   User and password - credentials of a user that has the `AuthGroup.IntegrationDeveloper` role for the above-mentioned TMN node
> 
> 
> For more information, see [Using Services in the Neo Environment](using-services-in-the-neo-environment-a32d3d5.md#loioa32d3d532e2d4dceaaca4ebab68df037).



<a name="loiof1caa871360c40e7be7ce4264ab9c336__section_wvf_gj4_mz"/>

## Supported Multitarget Application Resource Types

This section contains the resource types and their parameters that are supported by the SAP BTP.

> ### Note:  
> -   The relation between a module and the entities created in the SAP BTP is not one-to-one, that is, it is possible for one module to contain several SAP BTP entities.
> -   Any security-sensitive data, such as user credentials and passwords, has to be placed in the MTA extension descriptor.


<table>
<tr>
<th valign="top">

Resource Type



</th>
<th valign="top">

Description



</th>
</tr>
<tr>
<td valign="top">

`com.sap.hcp.persistence`



</td>
<td valign="top">

Used for binding a database with a specified identifier to a Java application



</td>
</tr>
<tr>
<td valign="top">

`<untyped>`



</td>
<td valign="top">

Used for adding any properties that you might require and which you define. It does not have a lifecycle.

> ### Note:  
> The untyped resource is unclassified, that is, it does not have a type.



</td>
</tr>
</table>

Resource types support the following parameters:


<table>
<tr>
<th valign="top">

Resource type



</th>
<th valign="top">

Parameter



</th>
<th valign="top">

Parameter Description



</th>
<th valign="top">

Type



</th>
<th valign="top">

Default



</th>
<th valign="top">

Mandatory



</th>
</tr>
<tr>
<td valign="top" rowspan="4">

`com.sap.hcp.persistence`



</td>
<td valign="top">

`id`



</td>
<td valign="top">

Identifier of the database that will be bound to a deployed Java application You can model a named data source by using the parameter

> ### Note:  
> If you want to use a `<DEFAULT>` database binding, the standard data source `jdbc/DefaultDB` has to be set up at the stage of the Java application development.



</td>
<td valign="top">

String



</td>
<td valign="top">

n/a



</td>
<td valign="top">

yes



</td>
</tr>
<tr>
<td valign="top">

`user-id`



</td>
<td valign="top">

The user ID parameter allows a database to be bound to a preexisting schema. If not used, a new schema has to be created.

> ### Note:  
> We recommend that you place this parameter in the MTA extension descriptor, if you are using one.



</td>
<td valign="top">

String



</td>
<td valign="top">

n/a



</td>
<td valign="top">

no



</td>
</tr>
<tr>
<td valign="top">

`password`



</td>
<td valign="top">

You can model a named data source by using the parameter. The password parameter allows a database to be bound to a preexisting schema. If not used, a new schema has to be created.

> ### Note:  
> We recommend that you place this parameter in the MTA extension descriptor, if you are using one.



</td>
<td valign="top">

String



</td>
<td valign="top">

n/a



</td>
<td valign="top">

no



</td>
</tr>
<tr>
<td valign="top">

`account`



</td>
<td valign="top">

This is the provider subaccount of the database. The subaccount parameter is needed only when the database is consumed from another subaccount.

> ### Note:  
> The provider subaccount must meet the following criteria:
> 
> -   It has to be part of the same global account.
> -   It has to provide permissions that allow a database to be used from another subaccount.

For more information, see [Add New Access Permissions](https://help.sap.com/viewer/3fa880aa54b74110ae99ad01503fcd60/Cloud/en-US/d848edea0e4f4136922d7edcb47a7b7a.html "You use the cockpit or the console client in the Neo environment to create a new access permission, allowing a subaccount to use a database that is owned by another subaccount in the same global account.") :arrow_upper_right:.



</td>
<td valign="top">

String



</td>
<td valign="top">

n/a



</td>
<td valign="top">

no



</td>
</tr>
</table>

`binding-name` that is added to the database binding resource required in the `requires` section of the `com.sap.java` and `java.tomcat` module types.


<table>
<tr>
<th valign="top">

Required Sections



</th>
<th valign="top">

Parameter



</th>
<th valign="top">

Parameter Description



</th>
<th valign="top">

Type



</th>
<th valign="top">

Default



</th>
<th valign="top">

Mandatory



</th>
</tr>
<tr>
<td valign="top">

`com.sap.java` and `java.tomcat` 



</td>
<td valign="top">

`binding-name`



</td>
<td valign="top">

Data source name

> ### Note:  
> If you want to use a named database binding, the corresponding data source `jdbc/<name>` has to be set up at the stage of the Java application development.

For more information, see [Modeling Database Bindings](modeling-database-bindings-0acf332.md).



</td>
<td valign="top">

String



</td>
<td valign="top">

n/a



</td>
<td valign="top">

yes



</td>
</tr>
</table>



<a name="loiof1caa871360c40e7be7ce4264ab9c336__section_ezr_vsh_mz"/>

## Supported Metadata Options

The MTA specification `_schema-version` `3.1` introduces the notion for metadata, which can be added to a certain property or parameter.


<table>
<tr>
<th valign="top">

Metadata Option



</th>
<th valign="top">

Description



</th>
<th valign="top">

Type



</th>
<th valign="top">

Default Value



</th>
<th valign="top">

Mandatory



</th>
</tr>
<tr>
<td valign="top">

`consumer-optional`



</td>
<td valign="top">

Used when you want to provide your Multitarget Application for consumption by other subaccounts. You can add the `consumer-optional` metadata to a property to indicate that it should be populated with an MTA extension descriptor when your subscribers consume the Multitarget Application. If you do not provide the `consumer-optional` metadata, the deployment of the MTA deployment descriptor within your subaccount will fail due to missing data.

The following example will require the consumer of your Multitarget Application to provide a user and a password value:

> ### Example:  
> ```
> resources:
>   - name: example-resource
>     properties:
>       user:
>       password:
>     properties-metadata:
>       user:
>         optional: true
>         consumer-optional: false
>       password:
>         optional: true
>         consumer-optional: false
>     ...
> ```

> ### Note:  
> -   The `optional` parameter has to be explicitly defined and set to `true` if you want to use the option `consumer-optional`. See the MTA specification for additional information.
> -   Тhis option is available for Multitarget Application schema 3.1.0 and higher



</td>
<td valign="top">

Boolean



</td>
<td valign="top">

`true`



</td>
<td valign="top">

no



</td>
</tr>
<tr>
<td valign="top">

`description`



</td>
<td valign="top">

If it is used as metadata about a parameter without a value, it provides a user-friendly description of the missing parameter in the cockpit.

> ### Example:  
> ```
> resources:
>   - name: example-resource
>     properties:
>       user:
>     properties-metadata:
>       user:
>         description: Еxample resource user name
>     ...
> ```



</td>
<td valign="top">

String



</td>
<td valign="top">

 



</td>
<td valign="top">

no



</td>
</tr>
<tr>
<td valign="top">

`sensitive`



</td>
<td valign="top">

If it is used as metadata about a parameter without a value, it prompts the cockpit to use a password input field, that is, with hidden content.

> ### Example:  
> ```
> resources:
>   - name: example-resource
>     properties:
>       password:
>     properties-metadata:
>       password:
>         sensitive: true
>     ...
> ```



</td>
<td valign="top">

Boolean



</td>
<td valign="top">

`false`



</td>
<td valign="top">

no



</td>
</tr>
<tr>
<td valign="top">

`complex`



</td>
<td valign="top">

If it is used as metadata about a parameter without a value, it prompts the cockpit to use an input field for free text, for example, a description of a solution in several lines of text.

> ### Example:  
> ```
> resources:
>   - name: example-resource
>     properties:
>       description:
>     properties-metadata:
>       description:
>         complex: true
>     ...
> ```

> ### Note:  
> This parameter is not taken into account if you use it in conjunction with the `sensitive` parameter. The *Password* input field is used instead.



</td>
<td valign="top">

Boolean



</td>
<td valign="top">

`false`



</td>
<td valign="top">

no



</td>
</tr>
<tr>
<td valign="top">

`default-value`



</td>
<td valign="top">

If it is used as metadata about a parameter without a value, it provides a cockpit-relevant default value of the missing parameter.

> ### Example:  
> ```
> resources:
>   - name: example-resource
>     properties:
>       user:
>     properties-metadata:
>       user:
>         default-value: John Doe
>     ...
> ```



</td>
<td valign="top">

String



</td>
<td valign="top">

 



</td>
<td valign="top">

no



</td>
</tr>
</table>



<a name="loiof1caa871360c40e7be7ce4264ab9c336__section_tsg_pj4_mz"/>

## Destination Parameters

Depending on the type of the destination that you wish to create \(subaccount-level, application-level, subscription destination, and so on\), the destination can be modeled as a module `com.sap.hcp.destination`, or as a parameter of the modules `com.sap.java` or `java.tomcat`. However, the options available when you create a destination are the same for all of the destination types.


<table>
<tr>
<th valign="top">

MTA Parameter



</th>
<th valign="top">

Type



</th>
<th valign="top">

Mandatory



</th>
<th valign="top">

Possible Values



</th>
<th valign="top">

Default Value



</th>
<th valign="top">

Description or Comment



</th>
</tr>
<tr>
<td valign="top">

`force-overwrite`



</td>
<td valign="top">

String



</td>
<td valign="top">

 



</td>
<td valign="top">

`true` or `false`



</td>
<td valign="top">

`false`



</td>
<td valign="top">

If `true`, an already existing destination with the same name will be overwritten.



</td>
</tr>
<tr>
<td valign="top">

`owner`



</td>
<td valign="top">

String



</td>
<td valign="top">

 



</td>
<td valign="top">

 



</td>
<td valign="top">

`provider`



</td>
<td valign="top">

Indicates in which subaccount the destination should be created. The possible values are `provider` or `consumer`.



</td>
</tr>
<tr>
<td valign="top">

`name`



</td>
<td valign="top">

String



</td>
<td valign="top">

Yes



</td>
<td valign="top">

 



</td>
<td valign="top">

n/a



</td>
<td valign="top">

Technical name of the destination. It can be used later on to get an instance of that destination programmatically.



</td>
</tr>
<tr>
<td valign="top">

`type`



</td>
<td valign="top">

String



</td>
<td valign="top">

Yes



</td>
<td valign="top">

`HTTP, LDAP, MAIL, RFC`



</td>
<td valign="top">

HTTP



</td>
<td valign="top">

 



</td>
</tr>
<tr>
<td valign="top">

`description`



</td>
<td valign="top">

String



</td>
<td valign="top">

 



</td>
<td valign="top">

 



</td>
<td valign="top">

 



</td>
<td valign="top">

 



</td>
</tr>
<tr>
<td valign="top">

`url`



</td>
<td valign="top">

URL



</td>
<td valign="top">

Yes



</td>
<td valign="top">

 



</td>
<td valign="top">

 



</td>
<td valign="top">

Use when the parameter `type` has the `HTTP` or `LDAP` values. Mandatory only for these types.



</td>
</tr>
<tr>
<td valign="top">

`proxy-type`



</td>
<td valign="top">

Enumeration



</td>
<td valign="top">

 



</td>
<td valign="top">

`Internet, OnPremise`



</td>
<td valign="top">

Internet



</td>
<td valign="top">

Use with `HTTP` or `LDAP` destination `type`.



</td>
</tr>
<tr>
<td valign="top">

`authentication`



</td>
<td valign="top">

Enumeration



</td>
<td valign="top">

 



</td>
<td valign="top">

`NoAuthentication, BasicAuthentication, AppToAppSSO, ClientCertificateAuthentication, OAuth2SAMLBearerAssertion, PrincipalPropagation, SAPAssertionSSO` 



</td>
<td valign="top">

`NoAuthentication`



</td>
<td valign="top">

Use with `HTTP` or `LDAP` destination `type`.



</td>
</tr>
<tr>
<td valign="top">

`user`



</td>
<td valign="top">

String



</td>
<td valign="top">

 



</td>
<td valign="top">

 



</td>
<td valign="top">

 



</td>
<td valign="top">

When to use:

-   if `BasicAuthentication` is the `Authentication` type. Mandatory only for this type.
-   if the parameter `type` has the values `MAIL`, or `RFC`.



</td>
</tr>
<tr>
<td valign="top">

`password`



</td>
<td valign="top">

String



</td>
<td valign="top">

 



</td>
<td valign="top">

 



</td>
<td valign="top">

 



</td>
<td valign="top">

When to use:

-   if `BasicAuthentication` is the `Authentication` type. Mandatory only for this type.
-   if `MAIL`, or `RFC` are the destination `type`.



</td>
</tr>
<tr>
<td valign="top">

`audience`



</td>
<td valign="top">

String



</td>
<td valign="top">

Yes



</td>
<td valign="top">

 



</td>
<td valign="top">

 



</td>
<td valign="top">

Use when `OAuth2SAMLBearerAssertion` is the `Authentication` type. Mandatory only for this authentication.



</td>
</tr>
<tr>
<td valign="top">

`client-key`



</td>
<td valign="top">

String



</td>
<td valign="top">

Yes



</td>
<td valign="top">

 



</td>
<td valign="top">

 



</td>
<td valign="top">

Use when `OAuth2SAMLBearerAssertion` is the `Authentication` type. Mandatory only for this authentication.



</td>
</tr>
<tr>
<td valign="top">

`token-service-url`



</td>
<td valign="top">

URL



</td>
<td valign="top">

Yes



</td>
<td valign="top">

 



</td>
<td valign="top">

 



</td>
<td valign="top">

Use when `OAuth2SAMLBearerAssertion` is the `Authentication` type. Mandatory only for this authentication.



</td>
</tr>
<tr>
<td valign="top">

`token-service-user`



</td>
<td valign="top">

String



</td>
<td valign="top">

 



</td>
<td valign="top">

 



</td>
<td valign="top">

 



</td>
<td valign="top">

Use when `OAuth2SAMLBearerAssertion` is the `Authentication` type.



</td>
</tr>
<tr>
<td valign="top">

`token-service-password`



</td>
<td valign="top">

String



</td>
<td valign="top">

 



</td>
<td valign="top">

 



</td>
<td valign="top">

 



</td>
<td valign="top">

Use when `OAuth2SAMLBearerAssertion` is the `Authentication` type.



</td>
</tr>
<tr>
<td valign="top">

`system-user`



</td>
<td valign="top">

String



</td>
<td valign="top">

 



</td>
<td valign="top">

 



</td>
<td valign="top">

 



</td>
<td valign="top">

Use when `OAuth2SAMLBearerAssertion` is the `Authentication` type.



</td>
</tr>
<tr>
<td valign="top">

`issuer-sid`



</td>
<td valign="top">

String



</td>
<td valign="top">

Yes



</td>
<td valign="top">

 



</td>
<td valign="top">

 



</td>
<td valign="top">

Use when `SAPAssertionSSO` is the `Authentication` type. Mandatory only for this type.



</td>
</tr>
<tr>
<td valign="top">

`issuer-client`



</td>
<td valign="top">

String



</td>
<td valign="top">

Yes



</td>
<td valign="top">

 



</td>
<td valign="top">

 



</td>
<td valign="top">

Use when `SAPAssertionSSO` is the `Authentication` type. Mandatory only for this type.



</td>
</tr>
<tr>
<td valign="top">

`recipient-sid`



</td>
<td valign="top">

String



</td>
<td valign="top">

Yes



</td>
<td valign="top">

 



</td>
<td valign="top">

 



</td>
<td valign="top">

Use when `SAPAssertionSSO` is the `Authentication` type. Mandatory only for this type.



</td>
</tr>
<tr>
<td valign="top">

`recipient-client`



</td>
<td valign="top">

String



</td>
<td valign="top">

Yes



</td>
<td valign="top">

 



</td>
<td valign="top">

 



</td>
<td valign="top">

Use when `SAPAssertionSSO` is the `Authentication` type. Mandatory only for this type.



</td>
</tr>
<tr>
<td valign="top">

`certificate`



</td>
<td valign="top">

String



</td>
<td valign="top">

Yes



</td>
<td valign="top">

 



</td>
<td valign="top">

 



</td>
<td valign="top">

Use when `SAPAssertionSSO` is the `Authentication` type. Mandatory only for this type.



</td>
</tr>
<tr>
<td valign="top">

`signing-key`



</td>
<td valign="top">

String



</td>
<td valign="top">

Yes



</td>
<td valign="top">

 



</td>
<td valign="top">

 



</td>
<td valign="top">

Use when `SAPAssertionSSO` is the `Authentication` type. Mandatory only for this type.



</td>
</tr>
<tr>
<td valign="top">

`system-user`



</td>
<td valign="top">

String



</td>
<td valign="top">

 



</td>
<td valign="top">

 



</td>
<td valign="top">

 



</td>
<td valign="top">

Use when `OAuth2SAMLBearerAssertion` or `SAPAssertionSSO` are the `Authentication` type.



</td>
</tr>
<tr>
<td valign="top">

`repository-user`



</td>
<td valign="top">

String



</td>
<td valign="top">

 



</td>
<td valign="top">

 



</td>
<td valign="top">

 



</td>
<td valign="top">

Use with the `RFC` parameter `type`.



</td>
</tr>
<tr>
<td valign="top">

`repository-password`



</td>
<td valign="top">

String



</td>
<td valign="top">

 



</td>
<td valign="top">

 



</td>
<td valign="top">

 



</td>
<td valign="top">

Use with the `RFC` parameter `type`.



</td>
</tr>
<tr>
<td valign="top">

`client`



</td>
<td valign="top">

String



</td>
<td valign="top">

Yes



</td>
<td valign="top">

3 digits, in single quotes



</td>
<td valign="top">

 



</td>
<td valign="top">

Use with the `RFC` parameter `type`. Mandatory only for this type.



</td>
</tr>
<tr>
<td valign="top">

`client-ashost`



</td>
<td valign="top">

String



</td>
<td valign="top">

 



</td>
<td valign="top">

00-99, in single quotes



</td>
<td valign="top">

 



</td>
<td valign="top">

Use with the `RFC` parameter `type`. Either this or `client-mshost` must be specified.



</td>
</tr>
<tr>
<td valign="top">

`client-sysnr`



</td>
<td valign="top">

String



</td>
<td valign="top">

 



</td>
<td valign="top">

 



</td>
<td valign="top">

 



</td>
<td valign="top">

Use with the `RFC` parameter `type`, if `client-ashost` is specified.



</td>
</tr>
<tr>
<td valign="top">

`client-mshost`



</td>
<td valign="top">

String



</td>
<td valign="top">

 



</td>
<td valign="top">

 



</td>
<td valign="top">

 



</td>
<td valign="top">

Use with the `RFC` parameter `type`. Either this or `client-ashost` must be specified.



</td>
</tr>
<tr>
<td valign="top">

`client-r3name`



</td>
<td valign="top">

String



</td>
<td valign="top">

 



</td>
<td valign="top">

3 letters or digits



</td>
<td valign="top">

 



</td>
<td valign="top">

Use with the `RFC` parameter `type`, if `client-mshost` is specified.



</td>
</tr>
<tr>
<td valign="top">

`client-msserv`



</td>
<td valign="top">

String



</td>
<td valign="top">

 



</td>
<td valign="top">

 



</td>
<td valign="top">

 



</td>
<td valign="top">

Use with the `RFC` parameter `type`., if `client-mshost` is specified.



</td>
</tr>
<tr>
<td valign="top">

`additional-properties`



</td>
<td valign="top">

Map



</td>
<td valign="top">

 



</td>
<td valign="top">

 



</td>
<td valign="top">

 



</td>
<td valign="top">

Use this section to define arbitrary properties as a map of keys and values used in the destination. and are also validated by the SAP BTP. The additional parameters are denoted as follows:

> ### Example:  
> ```
> ldap.
> mail.
> jco.client.
> jco.destination.
> ```



</td>
</tr>
<tr>
<td valign="top">

 `location-id` 



</td>
<td valign="top">

String



</td>
<td valign="top">

 



</td>
<td valign="top">

 



</td>
<td valign="top">

 



</td>
<td valign="top">

The value defines the location ID identifying the Cloud Connector over which the connection is opened. The default value is an empty string identifying the Cloud Connector that is connected without any location ID.



</td>
</tr>
</table>

> ### Note:  
> The `additional-properties` values are not strictly verified during deployment, since they may vary excessively. For example, such values might depend on the destination type or authentication type. In case you are using such additional values, after deployment you have to ensure that the required elements have been properly created, and they operate as expected.



<a name="loiof1caa871360c40e7be7ce4264ab9c336__section_vck_p44_mz"/>

## Destinations Target Platform Keyword Options

In regard to modeling destinations the SAP BTP offers several keyword properties, which you can use to optimize your declaration about deploying a destination. You can have the following destination types:


<table>
<tr>
<th valign="top">

Keyword Option



</th>
<th valign="top">

Description



</th>
</tr>
<tr>
<td valign="top">

`application-url`



</td>
<td valign="top">

This keyword can be placed only within the properties category of the `provides` section of the `com.sap.java` and `java.tomcat` module types. It is used when you want to extract the URL of the Java Application and link it to a destination that you have modeled.

The following example contains a Java application that has a destination that leads to itself. Note that this example uses the MTA placeholder concept. For more information, see “Destination with Specific Target Platform Data Options” below.

> ### Example:  
> ```
> modules:
>   - name: java-module
>     type: com.sap.java
>     provides:
>       - name: java-module
>         properties:
>           application-url: ${default-url}
>     requires:
>       - name: java-module
>     parameters:
>       name: exampleapp
>       destinations:
>         - name: ExampleWebsite
>           type: HTTP
>           url: ${java-module/application-url}
>       ...
> ```



</td>
</tr>
</table>



<a name="loiof1caa871360c40e7be7ce4264ab9c336__section_l5s_mp4_mz"/>

## Destinations with Target Platform Specific Data Options

When modeling destinations the SAP BTP offers several keyword properties that allow you to express your intention when deploying a destination more clearly. There might be cases, in which some of the destination data prior deploying the MTA archive is not known to you. Such data might be, for example, the URL of a Java Application that you want your destination to point to. To address these cases, SAP BTP provides several placeholders that you can use when you model your MTA. Placeholders are part of the Multitarget Application specification, and are strings resolved depending on the scope in which they are used. They have the syntax `${<name>}`.

Currently all types of destinations support the following placeholders, which are automatically resolved with their valid values during deployment.


<table>
<tr>
<th valign="top">

Placeholder Option



</th>
<th valign="top">

Description



</th>
</tr>
<tr>
<td valign="top">

`${default-url}`



</td>
<td valign="top">

Instructs SAP BTP to resolve the placeholder value to the default Java Application URL when deploying the destination. Тhis placeholder can be part only of the property named `application-url`, which serves as a `provided` dependency of the `com.sap.java` and `java.tomcat` module types.

This example shows the usage of the `${default-url}` placeholder. The modeled java-module provides the `application-url` dependency:

> ### Example:  
> ```
> modules:
>   - name: java-module
>     type: com.sap.java
>     provides:
>       - name: java-module
>         properties:
>           application-url: ${default-url}
>     parameters:
>       name: exampleapp
>       ...
> ```

> ### Note:  
> -   This placeholder can be used only with destination types that have a URL within their properties, that is, destination types such as an HTTP destination.
> -   This URL can be automatically resolved only if the Java Application has only one URL.



</td>
</tr>
<tr>
<td valign="top">

`${account-name}`



</td>
<td valign="top">

Instructs SAP BTP to resolve the placeholder value to your subaccount name when deploying the destination. This placeholder can be used only in the `url` parameter for a destination, the `token-service-url` parameter, and in the `application-url` property, which serves as a `provided` dependency of the `com.sap.java` and `java.tomcat` module types.

> ### Example:  
> ```
> modules:
>   - name: java-module
>     type: com.sap.java
>     provides:
>       - name: java-module
>         properties:
>           application-url: ${default-url}/accounts/${account-name}/example
>     parameters:
>       name: exampleapp
>       ...
>   - name: abc-java
>     type: com.sap.java
>     parameters:
>       destinations:
>         - name: ExampleWebsite
>           type: HTTP
>           url: http://abc.example.com/accounts/${account-name}
>           ....
> ```



</td>
</tr>
<tr>
<td valign="top">

`${provider-account-name}`



</td>
<td valign="top">

Instruct SAP BTP to resolve the placeholder value to the subaccount name of the provider when the destination is being deploying. This placeholder can be used only in the `url` parameter for a destination and the `token-service-url` parameter. You can use it if you want to employ a model, where a destination is created within your subscribers subaccount and you want it to point to a URL in your provider subaccount.

> ### Example:  
> ```
> modules:
>   - name: abc-java
>     type: com.sap.java
>     parameters:
>       destinations:
>         - name: ExampleWebsite
>           type: HTTP
>           url: http://abc.example.com/accounts/${provider-account-name}
>           owner: consumer
>           ....
> ```

> ### Note:  
> -   In the example the subscriber subaccount is consuming a Solution that is provided by you.
> -   The consumer property of the destination indicates that this destination is going to be deployed into the subaccount of the consumer.



</td>
</tr>
<tr>
<td valign="top">

`${landscape-url}`



</td>
<td valign="top">

Instructs the SAP BTP to resolve the placeholder value to the current landscape URL when deploying the destination. This placeholder can be used only in the `url` property for a destination, the `token-service-url` parameter, and in the `application-url` property that serves as a `provided` dependency of the `com.sap.java` and `java.tomcat` module types.

> ### Example:  
> ```
> modules:
>   - name: java-module
>     type: com.sap.java
>     provides:
>       - name: java-module
>         properties:
>           application-url: myjava.${landscape-url}/
>     parameters:
>       name: exampleapp
>       ...
>   - name: abc-java
>     type: com.sap.java
>     parameters:
>       destinations:
>         - name: ExampleWebsite
>           type: HTTP
>           url: abc.${landscape-url}/
>           ....
> ```



</td>
</tr>
</table>

