<!-- loioe7f54c25bb571014baee8ae351acd8d5 -->

# SAP BTP SDK for Neo Environment

The SAP BTP SDK for Neo environment contains everything you need to work with SAP BTP, including a local server runtime and a set of command line tools.

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**



## Prerequisites

You have the SDK installed. See [Install the SAP BTP SDK for Neo Environment](../30-development-neo/install-the-sap-btp-sdk-for-neo-environment-7613843.md).



The location of the SDK is the folder you have chosen when you downloaded and unzipped it.

An overview of the structure and content of the SDK is shown in the table below. The folders and files are located directly below the common root directory in the order given:


<table>
<tr>
<th valign="top">

Folder/File

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

`api`

</td>
<td valign="top">

The platform API containing the SAP and third-party API JARs required to compile Web applications for SAP BTP \(for more information about the platform API, see the "Supported APIs" section further below\).

</td>
</tr>
<tr>
<td valign="top">

`javadoc`

</td>
<td valign="top">

Javadoc for the SAP platform APIs \(also available as online documentation via the *API Documentation* link in the title bar of the SAP BTP Documentation Center\). Javadoc for the third-party APIs is cross-referenced from the online documentation.

</td>
</tr>
<tr>
<td valign="top">

`repository`

</td>
<td valign="top">

The P2 repository from which the local server runtime is created.

</td>
</tr>
<tr>
<td valign="top">

`samples`

</td>
<td valign="top">

Samples demonstrating how to develop for SAP BTP. The samples can be imported as Eclipse or Maven projects.

</td>
</tr>
<tr>
<td valign="top">

`server`

</td>
<td valign="top">

Initially not present, but created once you install a local server runtime.

</td>
</tr>
<tr>
<td valign="top">

`tools`

</td>
<td valign="top">

Command line tools required for interacting with the cloud runtime \(for example, to deploy and start applications\) and the local server runtime \(for example, to install and start the local server\).

</td>
</tr>
<tr>
<td valign="top">

`licenses.txt`

</td>
<td valign="top">

Licenses of third-party components contained in the SAP BTP SDK for Neo environment.

</td>
</tr>
<tr>
<td valign="top">

`readme.txt`

</td>
<td valign="top">

Brief introduction to the SAP BTP SDK for Neo environment, its content, and how to set it up.

</td>
</tr>
<tr>
<td valign="top">

`sdk.version`

</td>
<td valign="top">

SDK version information for use by other tools interacting with the SAP BTP SDK for Neo environment.

</td>
</tr>
</table>



<a name="loioe7f54c25bb571014baee8ae351acd8d5__section_4E18236B50684A48A52CFEF5C004CD98"/>

## Local Server Runtime

The cloud server runtime consists of the application server, the platform API, and the cloud implementations of the provided services \(connectivity, SAP HANA and SAP ASE, document, and identity\). The SDK, on the other hand, contains a local server runtime that consists of the same application server, the same platform API, but local implementations of the provided services. These are designed to emulate the cloud server runtime as closely as possible to support the local development and test process.



<a name="loioe7f54c25bb571014baee8ae351acd8d5__section_E95A3B9EA3364F41B4A647E67F95A25A"/>

## Supported APIs

The SAP BTP SDK for Neo environment contains the API for SAP BTP. All web applications that should be deployed in the cloud should be compiled against this platform API. The platform API is used by the SAP BTP Tools for Java to set the compile-time classpath.

All JARs contained in the platform API are considered part of the provided scope and must therefore be used for compilation. This means that they must not be packaged with the application, since they are provided and wired at runtime in the SAP BTP runtime, irrespective of whether you run your application locally for development and test purposes or centrally in the cloud.

When you develop applications to run on the SAP BTP, you should be aware of which APIs are supported and provisioned by the runtime environment of the platform:

-   Third-party APIs: These include Java EE standard APIs \(standards based and backwards compatible as defined in the Java EE Specification\) and other APIs released by third parties.
-   SAP APIs: The platform APIs provided by the SAP BTP services.


**Related Information**  


[Using Samples](../30-development-neo/using-samples-937ce0d.md "The sample applications allow you to explore the core functionality of SAP BTP and show how this functionality can be used to develop more complex Web applications. The samples are included in the SAP BTP SDK for Neo environment or presented as blogs in the SAP Community.")

[Console Client for the Neo Environment](../50-administration-and-ops-neo/console-client-for-the-neo-environment-7613230.md)

[API Documentation](../30-development-neo/api-documentation-4570e92.md "API documentation for the Neo environment.")

[Supported Java APIs](../30-development-neo/supported-java-apis-e836a95.md)

[Deploy Locally with the Console Client](../30-development-neo/deploy-locally-with-the-console-client-937c833.md "The console client allows you to install a server runtime in a local folder and use it to deploy your application.")

