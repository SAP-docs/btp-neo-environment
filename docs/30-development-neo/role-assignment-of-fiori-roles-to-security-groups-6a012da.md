<!-- loio6a012daa2a70439f8b1a5d307f618acb -->

# Role Assignment of Fiori Roles to Security Groups

You can assign security roles on subscription level for use with SAP Fiori applications.

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/docs/btp/sap-business-technology-platform/sap-business-technology-platform?version=Cloud) .**

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

