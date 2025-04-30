<!-- loioe3a38548b9c247ed925a5f9b3ecd6f69 -->

# Modeling Security Groups and Role Assignments

To organize application security roles and to manage user access, you create authorization groups in SAP BTP.

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of the following technology portfolios: application development; process automation; integration; data, analytics, and enterprise planning; artificial intelligence. The platform offers users the ability to turn data into business value, compose end-to-end business processes, connect entire IT landscapes, and personalize, build and extend SAP applications. This reduces the overall total cost of ownership maintaining SAP landscapes and third-party software across end-to-end business processes.") :arrow_upper_right:.**

You model security groups in the MTA deployment descriptor using the module type `com.sap.hcp.group`. You can also assign any roles defined in a Java application to these authorization groups.

The following rules apply when you deploy a solution containing authorization groups:

-   If the group already exists, it is updated with the new roles assignment defined in the MTA deployment descriptor.
-   If you delete a solution, a group is not deleted, as it might be used by other applications.

> ### Example:  
> We assume that you have defined as follows a set of security roles in the `web.xml` of your Java application.
> 
> ```
> <!DOCTYPE web-app PUBLIC
> "-//Sun Microsystems, Inc.//DTD Web Application 2.3//EN"
> "http://java.sun.com/dtd/web-app_2_3.dtd" >
>  
> <web-app>
>   <display-name>My Java Web Application</display-name>
>   <security-role>
>     <role-name>administrator</role-name>
>   </security-role> 
> </web-app>
> 
> ```

For a complete list of the supported properties, see [MTA Module Types, Resource Types, and Parameters for Applications in the Neo Environment](mta-module-types-resource-types-and-parameters-for-applications-in-the-neo-environment-f1caa87.md).

The security roles can be assigned to a group modeled in the MTA deployment descriptor.

> ### Example:  
> ```
> ID: com.sap.mta.demo
> _schema-version: '2.1'
> 
> parameters:
>   hcp-deployer-version: '1.1.0'
> 
> modules:
> - name: administratorGroup
>    parameters:
>       name: &adminGroup AdministratorGroup
>    type: com.sap.hcp.group
> - name: demowebapp
>    parameters:
>       name: demowebapp
>       title: Demo MTA Application
>       runtime-version: '3'
>       java-version: JRE 8
>       roles:
>        - name: administrator
>          groups:
>           - *adminGroup
>    requires:
>     - name: administratorGroup
> 
> ```

When you deploy the above example, a new authorization group named `AdministratorGroup` is created, and the `administrator` application security role form the `demowebapp` is assigned to this group. In case the roles already exists, only the application security role is assigned to the existing group.

**Related Information**  


[Role Assignment of HTML 5 Roles to Security Groups](role-assignment-of-html-5-roles-to-security-groups-43edba2.md "You can assign security roles on subscription level for use with HTML5 applications.")

[Role Assignment of Fiori Roles to Security Groups](role-assignment-of-fiori-roles-to-security-groups-6a012da.md "You can assign security roles on subscription level for use with SAP Fiori applications.")

[Operating Solutions](operating-solutions-2abf7d4.md "You can deploy, update, monitor, and delete a solution.")

[The Multitarget Application Model v.2](https://help.sap.com/doc/multitarget-application-modelv2/Cloud/en-US/The%20Multitarget%20Application%20Model.pdf)

[The Multitarget Application Model v.3](https://help.sap.com/doc/multitarget-application-modelv3/Cloud/en-US/The%20Multitarget%20Application%20M%D0%BEdel.pdf)

