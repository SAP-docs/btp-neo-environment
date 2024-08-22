<!-- loioed31d24c41b74e3da07a4befc49b6726 -->

# Update Options and Examples



> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of the following technology portfolios: application development; process automation; integration; data, analytics, and enterprise planning; artificial intelligence. The platform offers users the ability to turn data into business value, compose end-to-end business processes, connect entire IT landscapes, and personalize, build and extend SAP applications. This reduces the overall total cost of ownership maintaining SAP landscapes and third-party software across end-to-end business processes.") :arrow_upper_right:.**



> ### Note:  
> For the examples below we assume that you have an already deployed MTA with a deployment descriptor containing data similar to Version 1, and you want to update it to Version 2.



## Example: Application Name Change While Keeping the Same Module Name


<table>
<tr>
<th valign="top">

Version 1

</th>
<th valign="top">

Version 2

</th>
</tr>
<tr>
<td valign="top">

> ### Sample Code:  
> ```
> ID: com.sap.mta.demo
> _schema-version: '3.1'
> 
> modules:
>  - name: administratorGroup
>    parameters:
>       name: &adminGroup AdministratorGroup
>    type: com.sap.hcp.group
>  - name: demowebapp
>    parameters:
>       name: demowebapp
>       jvm-arguments: -server
>       title: Demo MTA Application
>       runtime-version: '3'
>       java-version: JRE 8
>       minimum-processes: 1
>       maximum-processes: 2
>       roles:
>        - name: administrator
>          groups:
>           - *adminGroup
>    provides:
>     - name: app_url
>       properties:
>          application-url: ${default-url}
>       public: true
>    requires:
>     - name: administratorGroup
>    type: java.tomcat
>  - name: demohtml5app
>    parameters:
>       name: demohtml5app
>       version: 0.1.0-${timestamp}
>    requires:
>     - name: demowebapp-destination
>    type: com.sap.hcp.html5
>  - name: demowebapp-destination
>    parameters:
>       name: DemoAppBackend
>       type: HTTP
>       url: ~{app_url/application-url}
>       proxy-type: Internet
>       authentication: AppToAppSSO
>       owner: provider
>    requires:
>     - name: app_url
>    type: com.sap.hcp.destination
> 
> parameters:
>    hcp-deployer-version: '1.2.0'
>    description: The application demonstrates some of the 
>    main MTA features on SAP CP NEO.
>    title: Demo MTA Application
>    version: 0.1.1
> ```



</td>
<td valign="top">

> ### Sample Code:  
> ```
> ID: com.sap.mta.demo
> _schema-version: '3.1'
> 
> modules:
>  - name: administratorGroup
>    parameters:
>       name: &adminGroup AdministratorGroup
>    type: com.sap.hcp.group
>  - name: demowebapp
>    parameters:
>       name: demowebapp2
>       jvm-arguments: -server
>       title: Demo MTA Application
>       runtime-version: '3'
>       java-version: JRE 8
>       minimum-processes: 1
>       maximum-processes: 2
>       roles:
>        - name: administrator
>          groups:
>           - *adminGroup
>    provides:
>     - name: app_url
>       properties:
>          application-url: ${default-url}
>       public: true
>    requires:
>     - name: administratorGroup
>    type: java.tomcat
>  - name: demohtml5app
>    parameters:
>       name: demohtml5app
>       version: 0.1.0-${timestamp}
>    requires:
>     - name: demowebapp-destination
>    type: com.sap.hcp.html5
>  - name: demowebapp-destination
>    parameters:
>       name: DemoAppBackend
>       type: HTTP
>       url: ~{app_url/application-url}
>       proxy-type: Internet
>       authentication: AppToAppSSO
>       owner: provider
>    requires:
>     - name: app_url
>    type: com.sap.hcp.destination
> 
> parameters:
>    hcp-deployer-version: '1.2.0'
>    description: The application demonstrates some of the 
>    main MTA features on SAP CP NEO.
>    title: Demo MTA Application
>    version: 0.1.2
> ```



</td>
</tr>
</table>

In the example above, the parameter `name` of the `demowebapp` module of the MTA is changed to `demowebapp2`. This change in the MTA deployment descriptor leads to the undeployment of the Java application with name `demowebapp` and deployment of the new application `demowebapp2`. This process takes place as a key or an identifier parameter for the corresponding SAP BTP component is changed.



<a name="loioed31d24c41b74e3da07a4befc49b6726__section_ekx_ycg_xbb"/>

## Example: Module Undeployment


<table>
<tr>
<th valign="top">

Version 1

</th>
<th valign="top">

Version 2

</th>
</tr>
<tr>
<td valign="top">

> ### Sample Code:  
> ```
> ID: com.sap.mta.demo
> _schema-version: '3.1'
> 
> modules:
>  - name: administratorGroup
>    parameters:
>       name: &adminGroup AdministratorGroup
>    type: com.sap.hcp.group
>  - name: demowebapp
>    parameters:
>       name: demowebapp2
>       jvm-arguments: -server
>       title: Demo MTA Application
>       runtime-version: '3'
>       java-version: JRE 8
>       minimum-processes: 1
>       maximum-processes: 2
>       roles:
>        - name: administrator
>          groups:
>           - *adminGroup
>    provides:
>     - name: app_url
>       properties:
>          application-url: ${default-url}
>       public: true
>    requires:
>     - name: administratorGroup
>    type: java.tomcat
>  - name: demohtml5app
>    parameters:
>       name: demohtml5app
>       version: 0.1.0-${timestamp}
>    requires:
>     - name: demowebapp-destination
>    type: com.sap.hcp.html5
>  - name: demowebapp-destination
>    parameters:
>       name: DemoAppBackend
>       type: HTTP
>       url: ~{app_url/application-url}
>       proxy-type: Internet
>       authentication: AppToAppSSO
>       owner: provider
>    requires:
>     - name: app_url
>    type: com.sap.hcp.destination
> 
> parameters:
>    hcp-deployer-version: '1.2.0'
>    description: The application demonstrates some of the 
>    main MTA features on SAP CP NEO.
>    title: Demo MTA Application
>    version: 0.1.2
> ```



</td>
<td valign="top">

> ### Sample Code:  
> ```
> ID: com.sap.mta.demo
> _schema-version: '3.1'
> 
> modules:
>  - name: administratorGroup
>    parameters:
>       name: &adminGroup AdministratorGroup
>    type: com.sap.hcp.group
>  - name: demowebapp2
>    parameters:
>       name: demowebapp2
>       jvm-arguments: -server
>       title: Demo MTA Application
>       runtime-version: '3'
>       java-version: JRE 8
>       minimum-processes: 1
>       maximum-processes: 2
>       roles:
>        - name: administrator
>          groups:
>           - *adminGroup
>    provides:
>     - name: app_url
>       properties:
>          application-url: ${default-url}
>       public: true
>    requires:
>     - name: administratorGroup
>    type: java.tomcat
>  - name: demowebapp-destination
>    parameters:
>       name: DemoAppBackend
>       type: HTTP
>       url: ~{app_url/application-url}
>       proxy-type: Internet
>       authentication: AppToAppSSO
>       owner: provider
>    requires:
>     - name: app_url
>    type: com.sap.hcp.destination
> 
> parameters:
>    hcp-deployer-version: '1.2.0'
>    description: The application demonstrates some of the 
>    main MTA features on SAP CP NEO.
>    title: Demo MTA Application 
>    version: 0.1.3
> ```



</td>
</tr>
</table>

In the example above, the module `demohtml5app` of type `com.sap.hcp.html5` is removed. This change leads to an undeplyment of the corresponding HTML5 application.



<a name="loioed31d24c41b74e3da07a4befc49b6726__section_n2k_mdg_xbb"/>

## Example: New Module Deployment


<table>
<tr>
<th valign="top">

Version 1

</th>
<th valign="top">

Version 2

</th>
</tr>
<tr>
<td valign="top">

> ### Sample Code:  
> ```
> ID: com.sap.mta.demo
> _schema-version: '3.1'
> 
> modules:
>  - name: administratorGroup
>    parameters:
>       name: &adminGroup AdministratorGroup
>    type: com.sap.hcp.group
>  - name: demowebapp2
>    parameters:
>       name: demowebapp2
>       jvm-arguments: -server
>       title: Demo MTA Application
>       runtime-version: '3'
>       java-version: JRE 8
>       minimum-processes: 1
>       maximum-processes: 2
>       roles:
>        - name: administrator
>          groups:
>           - *adminGroup
>    provides:
>     - name: app_url
>       properties:
>          application-url: ${default-url}
>       public: true
>    requires:
>     - name: administratorGroup
>    type: java.tomcat
>  - name: demowebapp-destination
>    parameters:
>       name: DemoAppBackend
>       type: HTTP
>       url: ~{app_url/application-url}
>       proxy-type: Internet
>       authentication: AppToAppSSO
>       owner: provider
>    requires:
>     - name: app_url
>    type: com.sap.hcp.destination
> 
> parameters:
>    hcp-deployer-version: '1.2.0'
>    description: The application demonstrates some of the 
>    main MTA features on SAP CP NEO.
>    title: Demo MTA Application 
>    version: 0.1.3
> ```



</td>
<td valign="top">

> ### Sample Code:  
> ```
> ID: com.sap.mta.demo
> _schema-version: '3.1'
> 
> modules:
>  - name: administratorGroup
>    parameters:
>       name: &adminGroup AdministratorGroup
>    type: com.sap.hcp.group
>  - name: demowebapp2
>    parameters:
>       name: demowebapp2
>       jvm-arguments: -server
>       title: Demo MTA Application
>       runtime-version: '3'
>       java-version: JRE 8
>       minimum-processes: 1
>       maximum-processes: 2
>       roles:
>        - name: administrator
>          groups:
>           - *adminGroup
>    provides:
>     - name: app_url
>       properties:
>          application-url: ${default-url}
>       public: true
>    requires:
>     - name: administratorGroup
>    type: java.tomcat
>  - name: demowebapp-destination
>    parameters:
>       name: DemoAppBackend
>       type: HTTP
>       url: ~{app_url/application-url}
>       proxy-type: Internet
>       authentication: AppToAppSSO
>       owner: provider
>    requires:
>     - name: app_url
>    type: com.sap.hcp.destination
>  - name: demohtml5app
>    parameters:
>       name: demohtml5app
>       version: 0.1.0-${timestamp}
>    requires:
>     - name: demowebapp-destination
>    type: com.sap.hcp.html5
>    
> parameters:
>    hcp-deployer-version: '1.2.0'
>    description: The application demonstrates some of the 
>    main MTA features on SAP CP NEO.
>    title: Demo MTA Application
>    version: 0.1.4
> ```



</td>
</tr>
</table>

In the example above, the previously missing module `demohtml5app` is added. As a result, the corresponding HTML5 application is deployed.

**Related Information**  


[General Information About Solution Updates](general-information-about-solution-updates-2b1c4ed.md)

[Updating Solutions](updating-solutions-4bec3f1.md)

