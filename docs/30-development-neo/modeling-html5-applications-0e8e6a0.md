<!-- loio0e8e6a0e25fe46b7bc7f98a7fe5c4076 -->

# Modeling HTML5 Applications

You can deploy HTML5 applications to the SAP BTP by modeling it as a part of a Multitarget Application.

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**

When you model an application in the МТА deployment descriptor, you have to specify a set of properties related to thе application. For a complete list of the supported properties, see [MTA Module Types, Resource Types, and Parameters for Applications in the Neo Environment](mta-module-types-resource-types-and-parameters-for-applications-in-the-neo-environment-f1caa87.md).

The following rules apply when you deploy a solution that contains an HTML5 application:

-   If an application with an identical name but a different version already exists in your subaccount, the added new version exists in parallel to the earlier application. Depending on the value of the `active` parameter, the new version is activated.
-   If an application with an identical name and the identical version already exists in your subaccount, the application in the solution to be deployed is going to be skipped.
-   If there is no version specified in the MTA deployment descriptor, it will be deployed with its current timestamp as version.
-   When you delete a solution containing an HTML5 application, the application itself and all of its versions are going to be deleted.

> ### Note:  
> The HTML5 application has to be packed in a ZIP archive.

> ### Example:  

> ### Sample Code:  
> ```
> 
> parameters:
>   hcp-deployer-version: '1.1.0'
> 
> ID: com.sap.example.html5
> version: 0.1.0
> 
> modules:
>   - name: examplehtml5
>     type: com.sap.hcp.html5
>     parameters:
>       name: example 
>       version: '0.1.0'
>       active: true
>       display-name: Example HTML5
> 
> ```

To always create a new version of the HTML5 application, you can also use the `${timestamp}` as a suffix to you version.

> ### Example:  

```
  - name: examplehtml5
    type: com.sap.hcp.html5
    parameters:
      name: example1
      version: '0.1.0-${timestamp}'

```

**Related Information**  


 <?sap-ot O2O class="- topic/link " href="c4f0d850b6ba46089a76d53ab805c9e6.xml" text="" desc="" xtrc="link:1" xtrf="file:/home/builder/src/dita-all/jjq1673438782153/loio9fe952ba277c471bbad80cd40548bb84_en-US/src/content/localization/en-us/0e8e6a0e25fe46b7bc7f98a7fe5c4076.xml" output-class="" current-file="file:/home/builder/tp.net.sf.dita-ot/2.3/plugins/com.elovirta.dita.markdown_1.3.0/xsl/dita2markdownImpl.xsl" ?> 

[Operating Solutions](operating-solutions-2abf7d4.md "You can deploy, update, monitor, and delete a solution.")

[The Multitarget Application Model v.2](http://go.sap.com/documents/2016/06/e2f618e4-757c-0010-82c7-eda71af511fa.html)

[The Multitarget Application Model v.3](https://www.sap.com/documents/2021/09/66d96898-fa7d-0010-bca6-c68f7e60039b.html)

