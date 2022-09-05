<!-- loio7f6d7860c67e4870a5538b1af4cdfee5 -->

# version

This command is used to list the SDK for SAP BTP,Neo environment version and the runtime. It also lists the command versions and the JAR files in the SDK and checks whether the SDK is up to date.



> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**



Use this command to show the SDK for SAP BTP, Neo environment version and the runtime. You can use parameters to list the command versions and the JAR files in the SDK and to check whether the SDK version is up to date.

```
neo version --commands
```

```
neo version --jars
```

```
neo version --updates
```



## Parameters

To list all parameters available for this command, execute `neo help` version in the command line.


<table>
<tr>
<th valign="top" colspan="2">

Required



</th>
</tr>
<tr>
<td valign="top">

`-c`, `--commands`



</td>
<td valign="top">

Lists all commands available in the SDK and their versions.



</td>
</tr>
<tr>
<td valign="top">

`-j`, `--jars`



</td>
<td valign="top">

Lists all JAR files in the SDK and their versions.



</td>
</tr>
<tr>
<td valign="top">

`-u`, `--updates`



</td>
<td valign="top">

Checks if there are any updates and hot fixes for the SDK and whether the SDK version is still supported. It also provides the version of the latest available SDK.



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

 `--output` `<value>`



</td>
<td valign="top">

Prints the output in the specified format.

`Acceptable values`: 'json'

`Type`: string



</td>
</tr>
</table>



## Example

To show the SAP BTP SDK for Neo environment version and the runtime, execute:

```
neo version
```

To list all available commands and their versions, execute:

```
neo version -c
```

To list all JAR files in the SDK and their versions, execute:

```
neo version -j
```

To check whether the SDK is up to date, execute:

```
neo version -u
```

There are several possible outcomes:

-   a hot fix is available, you need to update your SDK

-   your SDK is the latest version available

-   your SDK is deprecated, you need to update it

-   your SDK is supported, but it is not the latest version available


**Related Information**  


[Machine-Readable Command Output](machine-readable-command-output-b35e1e9.md "")

