<!-- loio93d5ce5346424596ac8dbe43b98a49ec -->

# Create the Resource File with Role Definitions

You create the resource file containing the SAP SuccessFactors HXM role definitions.



## Prerequisites

-   The corresponding SAP SuccessFactors HXM Suite roles exist in the SAP SuccessFactors system.

-   You have admin access to the SAP SuccessFactors OData API and have a valid subaccount with user name and password.




## Context

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**

To create the resource file with the role definitions required for your application, you use the SAP SuccessFactors OData API to query the permissions defined for this role, and create a `roles.json` file containing the role definitions. You use HTTP Basic Authentication for the OData API call.



## Procedure

1.  Call the OData API to query the permissions defined for the required role using the following URL:

    <code>https://<i class="varname">&lt;SAP_SuccessFactors_host_name&gt;</i>/odata/v2/RBPRole?$filter=roleName eq '<i class="varname">&lt;role_name&gt;</i>'&amp;$expand=permissions&amp;$format=json</code>

    Where:

    -   *<host\_name\>* is the fully qualified domain name of the OData API host depending on the region hosting your SAP SuccessFactors instance. For more information about the OData API endpoints, see [https://help.sap.com/viewer/d599f15995d348a1b45ba5603e2aba9b/LATEST/en-US/03e1fc3791684367a6a76a614a2916de.html](https://help.sap.com/viewer/d599f15995d348a1b45ba5603e2aba9b/LATEST/en-US/03e1fc3791684367a6a76a614a2916de.html).

    -   *<role\_name\>* is the name of the role as defined in the SAP SuccessFactors system.

    The response is a JSON object containing the following properties for each of the permissions defined for the specified role:


    <table>
    <tr>
    <th valign="top">

    Property
    
    </th>
    <th valign="top">

    Include in `roles.json`
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    permissionID
    
    </td>
    <td valign="top">
    
    No
    
    </td>
    <td valign="top">
    
    \(Key\)Permission ID, the sequence ID in permission table
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    permissionType
    
    </td>
    <td valign="top">
    
    Yes
    
    </td>
    <td valign="top">
    
    Permission\_Type column
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    permissionStringValue
    
    </td>
    <td valign="top">
    
    Yes
    
    </td>
    <td valign="top">
    
    Permission\_string\_value column
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    permissionLongValue
    
    </td>
    <td valign="top">
    
    Yes
    
    </td>
    <td valign="top">
    
    Permission\_long\_value column
    
    </td>
    </tr>
    </table>
    
    **Example response**

    ```json
    {
    	"d": {
    		"__metadata": {
    			"uri": "https://localhost:443/odata/v2/RBPRole(82L)",
    			"type": "SFOData.RBPRole"
    		},
    		"roleId": "82",
    		"roleDesc": "Testing role permissions",
    		"lastModifiedBy": "admin",
    		"lastModifiedDate": "\/Date(1404299328000)\/",
    		"roleName": "Test Role Permissions",
    		"userType": "null",
    		"permissions": {
    			"results": [{
    				"__metadata": {
    					"uri": "https://localhost:443/odata/v2/RBPBasicPermission(60L)",
    					"type": "SFOData.RBPBasicPermission"
    				},
    				"permissionId": "60",
    				"permissionType": "user_admin",
    				"permissionStringValue": "change_info_user_admin",
    				"permissionLongValue": "-1"
    				
    			},
    			{
    				"__metadata": {
    					"uri": "https://localhost:443/odata/v2/RBPBasicPermission(4L)",
    					"type": "SFOData.RBPBasicPermission"
    				},
    				"permissionId": "4",
    				"permissionStringValue": "detail_report",
    				"permissionLongValue": "-1",
    				"permissionType": "report"
    				}]
    ]
    		}
    	}
    }
    
    ```

2.  Create a `roles.json` file using the following properties. To list all the available permissions in your SAP SuccessFactors system, use this OData API call: <code>https://<i class="varname">&lt;SAP_SuccessFactors_host_name&gt;</i>/odata/v2/RBPBasicPermission?$format=json</code>. There you can find the properties that you need to create the `roles.json` file.


    <table>
    <tr>
    <th valign="top">

    Property
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    `roleName`
    
    </td>
    <td valign="top">
    
    Name of the role as defined in the response to the OData API call
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    `roleDesc`
    
    </td>
    <td valign="top">
    
    Role description as defined in the response to the OData API call
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    `permissionType`
    
    </td>
    <td valign="top">
    
    Value of the `permissionType` property as defined in the response to the OData API call
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    `permissionStringValue`
    
    </td>
    <td valign="top">
    
    Value of the `permissionStringValue` property as defined in the response to the OData API call
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    `permissionLongValue`
    
    </td>
    <td valign="top">
    
    Value of the `permissionLongValue` property as defined in the response to the OData API call
    
    </td>
    </tr>
    </table>
    
    **Target `roles.json` file**

    ```json
    [{
    	         "roleDesc": "My role description",
    	         "roleName": "My Application Role Name",
    	         "permissions": [{
    		         "permissionStringValue": "change_info_user_admin",
    		         "permissionLongValue": "-1",
    		         "permissionType": "user_admin"
    	         },
    	         {
    		         "permissionStringValue": "detail_report",
    		         "permissionLongValue": "-1",
    		         "permissionType": "report"
    	}]
    }]
    
    ```

3.  Save the file locally.




## Results

You have created the role definition resource file.

