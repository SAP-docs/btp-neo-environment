<!-- loio937ce0d172bb101490cf767db0e91070 -->

# Using Samples

The sample applications allow you to explore the core functionality of SAP BTP and show how this functionality can be used to develop more complex Web applications. The samples are included in the SAP BTP SDK for Neo environment or presented as blogs in the SAP Community.

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of the following technology portfolios: application development; process automation; integration; data, analytics, and enterprise planning; artificial intelligence. The platform offers users the ability to turn data into business value, compose end-to-end business processes, connect entire IT landscapes, and personalize, build and extend SAP applications. This reduces the overall total cost of ownership maintaining SAP landscapes and third-party software across end-to-end business processes.") :arrow_upper_right:.**



<a name="loio937ce0d172bb101490cf767db0e91070__section_1CFCFE99AC6D4F62ABAFD23E49D6FC2E"/>

## SDK Samples

The samples provided as part of the SAP BTP SDK for Neo environment introduce important concepts and application features of the SAP BTP and show how common development tasks can be automated using build and test tools. See [Using Samples](using-samples-937ce0d.md).

The samples are located in the `<sdk>/samples` folder. The table below lists the samples currently available:


<table>
<tr>
<th valign="top">

Sample

</th>
<th valign="top">

Feature

</th>
<th valign="top">

More Information

</th>
</tr>
<tr>
<td valign="top">

authentication

</td>
<td valign="top">

HTTP BASIC authentication scheme

</td>
<td valign="top">

[User Authentication](../60-security-neo/authentication-e637f62.md#loioe637f62abb571014857cb0232adc43a7) 

</td>
</tr>
<tr>
<td valign="top">

connectivity

</td>
<td valign="top">

Consumption of Internet services

</td>
<td valign="top">

[Consume Internet Services (Java Web or Java EE 6 Web Profile)](https://help.sap.com/viewer/b865ed651e414196b39f8922db2122c7/Cloud/en-US/e592cf6cbb57101495d3c28507d20f1b.html "") :arrow_upper_right: 

</td>
</tr>
<tr>
<td valign="top">

persistence-with-ejb

</td>
<td valign="top">

Container-managed persistence with JPA

</td>
<td valign="top">

[Tutorial: Adding Container-Managed Persistence with JPA \(SDK for Java EE 7 Web Profile\)](tutorial-adding-container-managed-persistence-with-jpa-sdk-for-java-ee-7-web-profile-7612e18.md#loio7612e180711e1014839a8273b0e91070)

</td>
</tr>
<tr>
<td valign="top">

persistence-with-jpa

</td>
<td valign="top">

Application-managed persistence with JPA

</td>
<td valign="top">

[Tutorial: Adding Application-Managed Persistence with JPA \(SDK for Java Web\)](tutorial-adding-application-managed-persistence-with-jpa-sdk-for-java-web-e4aeacd.md#loioe4aeacd2bb5710148ee99255136d96a5)

</td>
</tr>
<tr>
<td valign="top">

persistence-with-jdbc

</td>
<td valign="top">

Relational persistence with JDBC

</td>
<td valign="top">

[Tutorial: Adding Persistence with JDBC \(SDK for Java Web\)](tutorial-adding-persistence-with-jdbc-sdk-for-java-web-e4c5285.md#loioe4c52854bb571014aeb88753d0dad158) 

</td>
</tr>
<tr>
<td valign="top">

mail

</td>
<td valign="top">

Sending e-mails

</td>
<td valign="top">

[Example: Send E-Mails](https://help.sap.com/viewer/b865ed651e414196b39f8922db2122c7/Cloud/en-US/e70a574cbb57101494a781920e3c9d64.html "This example shows how you can send an e-mail from a simple Web application using an e-mail provider that is accessible on the Internet.") :arrow_upper_right:

</td>
</tr>
<tr>
<td valign="top">

SAP\_Jam\_OData\_HCP

</td>
<td valign="top">

Accessing data in SAP Jam via OData

</td>
<td valign="top">

[Source code for using the SAP Jam API](https://github.com/SAP/SAPJamSampleCode/tree/master/SAP_Jam_OData_HCP)

</td>
</tr>
</table>

All samples can be imported as Maven projects. While the focus has been placed on the Apache Maven tools due to their wide adoption, the principles apply equally to other IDEs and build systems.

For more information about using the samples, see [Building Samples with Maven](building-samples-with-maven-841e3ea.md).



<a name="loio937ce0d172bb101490cf767db0e91070__section_F32010C5E8B64822A7620FA839693CAF"/>

## Community Samples: Paul the Octopus

The Web application "Paul the Octopus" is part of a community blog and shows how the SAP BTP services and capabilities can be combined to build more complex Web applications, which can be deployed on the SAP BTP.

Features of "Paul the Octopus":

-   It is intended for anyone who would like to gain hands-on experience with the SAP BTP.
-   It involves the following platform services: identity, connectivity, SAP HANA and SAP ASE, and document.
-   Its user interface is developed via SAPUI5 and is based on the Model-View-Controller concept. SAPUI5 is based on HTML5 and can be used for building applications with sophisticated UI. Other technologies that you can see in action in "Paul the Octopus" are REST services and job scheduling.

For more information, see the SAP Community blog: [Get Ready for Your Paul Position](http://scn.sap.com/community/developer-center/cloud-platform/blog/2012/12/21/get-ready-for-your-paul-position).

You can get the application source from [https://github.com/SAP/cloud-paulpredicts/](https://github.com/SAP/cloud-paulpredicts/).



## Community Samples: SAP Library

The Web application "SAP Library" is presented in a community blog as another example of demonstrating the usage of several SAP BTP services in one integrated scenario, closely following the product documentation. You can import it as a Maven project, play around with your own library, and have a look at how it is implemented. It allows you to reserve and return books, edit details of existing ones, add new titles, maintain library users' profiles and so on.

Features of "SAP Library":

-   The library users authenticate using the identity service. It supports Single Sign-On \(SSO\).
-   The books’ status and features are persisted using the SAP HANA and SAP ASE service.
-   Book’s details are retrieved using a public Internet Web service, demonstrating usage of the connectivity service.
-   The e-mails you will receive when reserving and returning books to the library, are implemented using a Mail destination.
-   When you upload your profile image, it is persisted using the document service.

For more information, see the SAP Community blog: [Welcome to the Library!](http://scn.sap.com/community/developer-center/cloud-platform/blog/2013/07/01/welcome-to-the-library)

You can get the application source from [https://github.com/SAP/cloud-sample-library/](https://github.com/SAP/cloud-sample-library/)

**Related Information**  


[Building Samples with Maven](building-samples-with-maven-841e3ea.md "All samples provided can be built with Apache Maven. The Maven build shows how a headless build and test can be completely automated.")

[Building Java Web Applications with Maven](http://scn.sap.com/community/developer-center/cloud-platform/blog/2014/05/27/building-java-applications-with-maven)

[Working with the "Neo" Maven Plugin](http://scn.sap.com/community/developer-center/cloud-platform/blog/2014/05/27/working-with-the-neo-maven-plugin)

