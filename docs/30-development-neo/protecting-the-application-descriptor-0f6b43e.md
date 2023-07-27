<!-- loio0f6b43e57ee04e67aef43f4f2cd9f08c -->

# Protecting the Application Descriptor

By default end users can access the application descriptor file of an HTML5 application.

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://launchpad.support.sap.com/#/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**

To do so, they enter the URL of the application followed by the filename of the application descriptor in the browser.

> ### Tip:  
> For security reasons we recommend that you use a permission to protect the application descriptor from being accessed by end users.

A permission for the application descriptor can be defined by adding the following security constraint into the application descriptor

```json

...
	"securityConstraints": [
	     {
	          "permission": "AccessApplicationDescriptor",
	          "description": "Access application descriptor",
	          "protectedPaths": [
	             "/neo-app.json"
	          ]
	     }
	]
...

```

After activating the application, a role can be assigned to the new permission in the cockpit to give users with that role access to the application descriptor via the browser. For more information about how to define permissions for an HTML5 application, see [Authorization](authorization-a139548.md).

