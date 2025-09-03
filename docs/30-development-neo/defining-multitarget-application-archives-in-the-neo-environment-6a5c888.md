<!-- copy6a5c8888f89f404eb38b5bf30e17c2ad -->

# Defining Multitarget Application Archives in the Neo Environment

You package the MTA deployment descriptor and module binaries in an MTA archive. You can manually do so as described below, or alternatively use the Cloud MTA Build tool.

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/docs/btp/sap-business-technology-platform/sap-business-technology-platform?version=Cloud) .**

> ### Note:  
> There could be more than one module of the same type in an MTA archive.

The Multitarget Application \(MTA\) archive is created in a way compatible with the JAR file specification. This allows us to use common tools for creating, modifying, and signing such types of archives.

> ### Caution:  
> The maximum size of an MTA archive is limited to 500 MB. Deployment is denied for archives with larger size.

An MTA archive consists of the following:

-   The `MANIFEST.MF` file
-   The `mtad.yaml` MTA deployment descriptor file
-   Application binaries, content, or configuration files

> ### Note:  
> -   The MTA extension descriptor is not part of the MTA archive. During deployment you provide it as a separate file, or as parameters you enter manually when the SAP BTP requests them.
> -   Using a `resources` directory, as shown in some examples, is not mandatory. You can store the necessary resource files on root level of the MTA archive, or in another directory with name of your choice.

The following example shows the basic structure of an MTA archive. It contains a Java application `.war` file and a `META-INF` directory, which contains an MTA deployment descriptor with a module and a `MANIFEST.MF` file.

> ### Example:  
> ```
> /example.war
> /META-INF
> /META-INF/mtad.yaml
> /META-INF/MANIFEST.MF
> ```

The `MANIFEST.MF` file has to contain a name section for each MTA module part of the archive that has a file content. In the name section, the following information has to be added:

-   `Name` - the path within the MTA archive, where the corresponding module is located. If it leads to a directory, add a forward slash \(/\) at the end.
-   `Content-Type` - the type of the file that is used to deploy the corresponding module
-   `MTA-module` - the name of the module as it has been defined in the deployment descriptor

> ### Note:  
> -   You can store one application in two or more application binaries contained in the MTA archive.
> -   According to the JAR specification, there must be an empty line at the end of the file.

Sample content of the `META-INF/MANIFEST.MF` file:

> ### Example:  
> ```
> Manifest-Version: 1.0
> Created-By: example.com
> 
> Name: example.war
> Content-Type: application/zip
> MTA-Module: example-java-app
> 
> 
> ```

The example above instructs the SAP BTP to:

-   Look for the `example.war` file within the root of the MTA archive when working with module `example-java-app`
-   Interpret the content of the `example.war` file as an `application/zip`

> ### Note:  
> The example above is incomplete. To deploy a solution, you have to create an MTA deployment descriptor. Then you have to create the MTA archive.

> ### Tip:  
> As an alternative to the procedure described above, you can also use the Cloud MTA Build Tool. See its official documentation at [Cloud MTA Build Tool](https://sap.github.io/cloud-mta-build-tool/).

**Related Information**  


[Cloud MTA Build Tool](https://sap.github.io/cloud-mta-build-tool/)

[The Multitarget Application Model v.2](https://help.sap.com/doc/multitarget-application-modelv2/Cloud/en-US/The%20Multitarget%20Application%20Model.pdf)

[The Multitarget Application Model v.3](https://help.sap.com/doc/multitarget-application-modelv3/Cloud/en-US/The%20Multitarget%20Application%20M%D0%BEdel.pdf)

[JAR File Specification](http://docs.oracle.com/javase/7/docs/technotes/guides/jar/jar.html)

[Defining MTA Deployment Descriptors for the Neo Environment](defining-mta-deployment-descriptors-for-the-neo-environment-ef90452.md)

[Defining MTA Extension Descriptors](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/50df803465324d36851c79fd07e8972c.html "") :arrow_upper_right:

[MTA Module Types, Resource Types, and Parameters for Applications in the Neo Environment](mta-module-types-resource-types-and-parameters-for-applications-in-the-neo-environment-f1caa87.md)

