<!-- loio10b63fe6c3bb41bdb7986c3cebfd140e -->

# Debug Applications on the Cloud

In this section, you can learn how to debug a Web application on SAP BTP.



## Prerequisites

-   You have installed Eclipse IDE and the SAP JVM Tools for Eclipse. For more information, see [Install the SAP JVM Tools in Eclipse](install-the-sap-jvm-tools-in-eclipse-4e97452.md).

-   You have developed a Web application using IDE of your choice. For more information, see [Developing Java Applications](developing-java-applications-ac36e1f.md).
-   You have deployed your Web application. For more information, see [Deploying and Updating Java Applications](deploying-and-updating-java-applications-e5dfbc6.md).

> ### Note:  
> Debugging can be enabled if there is only one VM started for the requested account or application.



## Context

You can use IDE of your choice for developing the application. You must use Eclipse IDE for debugging the application on the cloud.

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/docs/btp/sap-business-technology-platform/sap-business-technology-platform?version=Cloud) .**

<a name="concept_pmx_g25_rn"/>

<!-- concept\_pmx\_g25\_rn -->

## Procedure



1.  Deploy your Web application in the console client and start it.
2.  Go to the Eclipse IDE, open the *Run* menu and choose *Debug Configurations*.
3.  Create a new debug configuration of type *SAP HANA Cloud Debugger*.
4.  In the *Project* section, choose the Java project that is already imported in the Eclipse IDE.
5.  In the *Connection Properties* section, provide the application data.
6.  Choose *Debug*.
7.  Open the *Debug* perspective in the Eclipse IDE.
8.  Set breakpoints in your application.
9.  Request your application.

> ### Note:  
> If you encounter any issues, see [Getting Support, Neo Environment](../70-getting-support-neo/getting-support-neo-environment-fc2bf6a.md).

**Related Information**  


[Eclipse: Debugging a servlet on a server](http://help.eclipse.org/luna/topic/org.eclipse.wst.server.ui.doc.user/topics/tservlet.html)

[Eclipse: Debugging a JSP file on a server](http://help.eclipse.org/luna/topic/org.eclipse.wst.server.ui.doc.user/topics/tdbgjsp.html)

