<!-- loioe1bb7eb746d34237b8b47035adff5022 -->

# Multitarget Applications for the Neo Environment

A Multitarget Application \(MTA\) is a package comprised of multiple application and resource modules, which have been created using different technologies and deployed to different runtimes, but having a common lifecycle. You bundle the modules together, describe them along with their interdependencies to other modules, services, and interfaces, and package them in an MTA.

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of the following technology portfolios: application development; process automation; integration; data, analytics, and enterprise planning; artificial intelligence. The platform offers users the ability to turn data into business value, compose end-to-end business processes, connect entire IT landscapes, and personalize, build and extend SAP applications. This reduces the overall total cost of ownership maintaining SAP landscapes and third-party software across end-to-end business processes.") :arrow_upper_right:.**

Complex business applications are composed of multiple parts developed with focus on micro-service design principles, API-management, usage of the OData protocol, increased usage of application modules developed with different languages, IDEs, and build methodologies. Thus, development, deployment, and configuration of separate elements introduce a variety of lifecycle and orchestration challenges. To address these challenges, SAP introduces the Multitarget Application \(MTA\) concept. It addresses the complexity of continuous deployment by employing a formal target-independent application model.

You can now benefit from an automated deployment of solutions in an MTA archive format, consisting of several modules as described above. The MTA archive, which includes both single modules, is comprised of its content, the technical prerequisites and interdependencies of the contained modules, as well as their technical description. The deployment infrastructure of SAP BTP is enabled to perform an automated deployment of such solutions, making sure that individual technical prerequisites are fulfilled before deploying the comprised modules to the right target runtimes and in the right order.

Initially, developers describe the modules of the application, the interdependencies to other modules and services, and required and exposed interfaces. Afterward, the SAP BTP validates, orchestrates, and automates the deployment of the MTA.

For more information about the Multitarget Application model, see the official specification documents [The Multitarget Application Model v.2](https://help.sap.com/doc/multitarget-application-modelv2/Cloud/en-US/The%20Multitarget%20Application%20Model.pdf) and [The Multitarget Application Model v.3](https://help.sap.com/doc/multitarget-application-modelv3/Cloud/en-US/The%20Multitarget%20Application%20M%D0%BEdel.pdf).


<table>
<tr>
<th valign="top">

To learn more about

</th>
<th valign="top">

See

</th>
</tr>
<tr>
<td valign="top">

Multitarget Application deployment descriptor

</td>
<td valign="top">

[Defining MTA Deployment Descriptors for the Neo Environment](defining-mta-deployment-descriptors-for-the-neo-environment-ef90452.md)

</td>
</tr>
<tr>
<td valign="top">

Defining MTA Development Descriptors

</td>
<td valign="top">

[Defining MTA Development Descriptors](defining-mta-development-descriptors-379278d.md)

</td>
</tr>
<tr>
<td valign="top">

Multitarget Application archive

</td>
<td valign="top">

[Defining Multitarget Application Archives](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/33a0e0eb1e4a47b3af52596b87fd2cef.html "You package the MTA deployment descriptor and module binaries in an MTA archive. You can manually do so as described below, or alternatively use the Cloud MTA Build tool.") :arrow_upper_right:

</td>
</tr>
<tr>
<td valign="top">

Multitarget Application extension descriptor

</td>
<td valign="top">

[Defining MTA Extension Descriptors](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/50df803465324d36851c79fd07e8972c.html "") :arrow_upper_right:

</td>
</tr>
<tr>
<td valign="top">

Multitarget Application module types and parameters

</td>
<td valign="top">

[MTA Module Types, Resource Types, and Parameters for Applications in the Neo Environment](mta-module-types-resource-types-and-parameters-for-applications-in-the-neo-environment-f1caa87.md)

</td>
</tr>
<tr>
<td valign="top">

How to model the Solution

</td>
<td valign="top">

[Modeling Solutions](modeling-solutions-62f1d91.md)

</td>
</tr>
<tr>
<td valign="top">

How to operate the Solution

</td>
<td valign="top">

[Operating Solutions](operating-solutions-2abf7d4.md)

</td>
</tr>
<tr>
<td valign="top">

How to use transport management tools for moving MTA archives among subaccounts

</td>
<td valign="top">

[Integration with Transport Management Tools](integration-with-transport-management-tools-905baea.md)

</td>
</tr>
</table>

**Related Information**  


[JAR File Specification](http://docs.oracle.com/javase/7/docs/technotes/guides/jar/jar.html)

[Cloud MTA Build Tool](https://github.com/SAP/cloud-mta-build-tool)

