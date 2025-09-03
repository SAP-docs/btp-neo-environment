<!-- loioee71c1a4aea84558accb2524785b21bc -->

# Choose JRE Version

You can choose the Java Runtime Environment \(JRE\) version used for an application.



## Prerequisites

You have downloaded and configured SAP BTP console client.

For more information, see [Set Up the Console Client](../30-development-neo/set-up-the-console-client-7613dee.md).



## Context

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/docs/btp/sap-business-technology-platform/sap-business-technology-platform?version=Cloud) .**

The different variants of the SAP BTP SDK for Neo environment provide support for a different set of JRE/Java versions. You can see the list of supported versions per each variant in [Application Runtime Container](../30-development-neo/application-runtime-container-7613bd2.md).

If you want to change this default version, you need to specify the *\--java-version* parameter when deploying the application using the SAP BTP console client.

If you are developing a JSP application using JRE 8, you need to add a configuration in the `web.xml` that sets the compiler target VM and compiler source VM versions to 1.8.



## Procedure

1.  Open the command prompt and navigate to the folder containing neo.bat/sh \(`<SDK installation folder>/tools`\).

2.  Deploy the application specifying *\--java-version*. For example, to use JRE 7, execute the following command:

    ```
    neo deploy --account <subaccount_name> --application <application_name> --source <file_location> 
    --user <e-mail_or_user> --java-version 7
    ```

    For Java Web Tomcat 8, Java version 8 is supported by default, but you can also use Java version 7.


**Related Information**  


[deploy](deploy-937db4f.md "Deploying an application publishes it to SAP BTP. Use the optional parameters to make some specific configurations of the deployed application.")

[Application Runtime Container](../30-development-neo/application-runtime-container-7613bd2.md)

