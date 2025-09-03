<!-- loio98a017874d5d405b93d07f928b156415 -->

# Managing Application Versions

An HTML5 application can have multiple versions, but only one of these can be active. This active version is then available to end-users of the application.

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/docs/btp/sap-business-technology-platform/sap-business-technology-platform?version=Cloud) .**

However, developers can access all versions of an application using unique URLs for testing purposes.

The *Versioning* view in the cockpit displays the list of available versions of an HTML5 application. Each version is marked either as active or inactive. You can activate an inactive version using the activation button.

For every version, the required destinations are displayed in a details table. To assign a destination from your subaccount global destinations to a required destination, choose *Edit* in the details table. By default, the destination with the same name as the name you defined for the route in the application descriptor is assigned. If this destination does not exist, you can either create the destination or assign another one.

When you activate a version, the destinations that are currently assigned to this version are copied to the active application version.

**Related Information**  


[Create a Version](../30-development-neo/create-a-version-d9e260b.md "You create a version of your application from one of the commits.")

[Activate a Version](../30-development-neo/activate-a-version-e7e3ec6.md "As end users can only access the active version of an application, you must create and activate a version of your application.")

