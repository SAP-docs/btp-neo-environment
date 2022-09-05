<!-- loio7612fbaf711e1014839a8273b0e91070 -->

# Compute Units

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**



A compute unit is the virtualized hardware resources used by an SAP BTP application.

After being deployed to the cloud, the application is hosted on a compute unit with certain central processing unit \(CPU\), main memory, disk space, and an installed OS.



<a name="loio7612fbaf711e1014839a8273b0e91070__section_EBE262EA90354403B5B61132C06C6AA2"/>

## Compute Unit Sizes

SAP BTP offers four standard sizes of compute units according to the provided resources.

Depending on their needs, customers can choose from the following compute unit configurations:


<table>
<tr>
<th valign="top">

Compute Unit



</th>
<th valign="top">

Configuration



</th>
<th valign="top">

Size Parameter Value



</th>
</tr>
<tr>
<td valign="top">

Lite edition



</td>
<td valign="top">

1 CPU Core; 3072 MB Main memory



</td>
<td valign="top">

 *lite* 



</td>
</tr>
<tr>
<td valign="top">

Professional edition



</td>
<td valign="top">

2 CPU Cores; 4096 MB Main memory



</td>
<td valign="top">

 *pro* 



</td>
</tr>
<tr>
<td valign="top">

Premium edition



</td>
<td valign="top">

4 CPU Cores; 8192 MB Main memory



</td>
<td valign="top">

 *prem* 



</td>
</tr>
<tr>
<td valign="top">

Premium Plus edition



</td>
<td valign="top">

8 CPU Cores; 16384 MB Main memory



</td>
<td valign="top">

 *prem-plus* 



</td>
</tr>
</table>

The third column in the table shows what value of the `-z` or `--size` parameter you need to use for a console command.

For customer accounts, all sizes of compute units are available. During deployment, customers can specify the compute unit on which they want their application to run.

For more information, see [deploy](../50-administration-and-ops-neo/deploy-937db4f.md).

**Related Information**  


[Sign up for a Customer Account](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/d61c2819034b48e68145c45c36acba6e.html#loioa71a081b39e343e097046bf487f57af3 "A customer account is an enterprise account that allows you to host productive, business-critical applications with 24x7 support.") :arrow_upper_right:

[Account Model](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/8ed4a705efa0431b910056c0acdbf377.html#loio8ed4a705efa0431b910056c0acdbf377 "Learn more about the different types of accounts on SAP BTP and how they relate to each other.") :arrow_upper_right:

[Configure Entitlements and Quotas for Subaccounts](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/5ba357b4fa1e4de4b9fcc4ae771609da.html "Assign entitlements to subaccounts by adding service plans and distribute the quotas available in your global account to your subaccounts using the SAP BTP cockpit.") :arrow_upper_right:

