<!-- loio3f61c0f7a2f04e31b3574df6f4fdcd21 -->

# Activating Statistics Gathering in SAP BTP

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**





### HTML5 Applications

The E2E tracing and gathering of statistics is supported by default for HTML5 applications.

**Real User Monitoring**

For HTML5 applications started from the SAP Fiori Launchpad, you have to manually activate the gathering of performance statistics for each site. Proceed as follows:

1.  In the SAP BTP cockpit, go to *Services* \> *Portal service*.
2.  In the navigation area, open the *Site Directory* tab.
3.  Select the Fiori Launchpad \(FLP\) you want to configure and choose *Edit*. This launches the Fiori Configuration Cockpit.
4.  In the navigation area, choose the *Settings* tab.
5.  Choose *Edit* to change the necessary settings.
6.  In the *System Settings* section, choose *On* for the *Collect Performance Data* flag.
7.  Save your settings.



### Java Applications

The E2E tracing and collection of data is disabled by default for Java applications. It has to be activated on demand. As prerequisites, you need a subaccount with a deployed and started Java application, you are a member of the subaccount, and you have the `Developer` role enabled.

To enable E2E tracing and collection of data, proceed as follows:

1.  In the SAP BTP cockpit, navigate to your Java application.
2.  In the navigation area, choose *Monitoring* \> *JMX Console*.
3.  Open bean *com.sap.js* \> *Statistics* \> *Statistics*.
4.  In the *Attributes* tab, check the *Switched* property, and switch it to *false* if it is not.
5.  Go to the *Operations* tab.
6.  For operation `doSwitch` in parameter `p1`, enter `true`, and execute the operation by choosing the triangle icon.

You then receive an activation confirmation with the value`true` to notify you that the procedure is successful.

