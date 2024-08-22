<!-- loio6a012daa2a70439f8b1a5d307f618acb -->

# Role Assignment of Fiori Roles to Security Groups

You can assign security roles on subscription level for use with SAP Fiori applications.

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of the following technology portfolios: application development; process automation; integration; data, analytics, and enterprise planning; artificial intelligence. The platform offers users the ability to turn data into business value, compose end-to-end business processes, connect entire IT landscapes, and personalize, build and extend SAP applications. This reduces the overall total cost of ownership maintaining SAP landscapes and third-party software across end-to-end business processes.") :arrow_upper_right:.**

These roles are assigned to authorization groups when designed as modules in a descriptor file, as shown in the following example:

> ### Sample Code:  
> ```
> ID: com.sap.mta.demo
> _schema-version: '3.1'
> 
> modules:
> 
>  - name: administratorGroup
>    parameters:
>       name: &adminGroup AdministratorGroup
>    type: com.sap.hcp.group
> 
>  - name: fiori-role
>    type: com.sap.fiori.role
>    parameters:
>      name: HRManager   
>      groups:
>           - *adminGroup
> ```

