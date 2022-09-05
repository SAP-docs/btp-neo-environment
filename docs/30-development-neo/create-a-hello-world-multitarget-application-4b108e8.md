<!-- loio4b108e8150a54f15ab052c8a7fd67e6c -->

# Create a Hello World Multitarget Application

In the context of the SAP BTP, a solution is comprised of:

-   A Multitarget Application \(MTA\) archive that bundles all the deployable modules and configurations together with the accompanying MTA deployment descriptor, which describes the content of the MTA archive, the module interdependencies, and required and exposed interfaces
-   An optional MTA extension descriptor that contains data complementary to the MTA deployment descriptor

In this tutorial, you will create the following:

1.  A module that describes a Java application
2.  A resource that describes your database binding
3.  Additional metadata required for the deployment



<a name="loio4b108e8150a54f15ab052c8a7fd67e6c__prereq_r4y_2gj_nz"/>

## Prerequisites

-   You have created a Java application `.war` file.
-   You have an SAP BTP database configured in your subaccount, and valid credentials.



## Context

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**



<a name="loio4b108e8150a54f15ab052c8a7fd67e6c__steps_yrd_3gj_nz"/>

## Procedure

1.  Modeling the MTA deployment descriptor

    You define the entities that have to be deployed, namely modules and resources related to other modules, in the MTA deployment descriptor. This is a YAML file that defines the contract between you as a deployable artifact provider and the SAP BTP as a deployer tool. Initially, you have to describe the metadata required for the deployment.

    1.  Create an empty text file and name it `mtad.yaml`.

    2.  Using a text editor, enter the following data in the file:

        > ### Note:  
        > Strictly adhere to the correct indentations when working with YAML files, and do not use the tabulator character.

        > ### Example:  
        > ```
        > _schema-version: '3.1'
        >  
        > parameters:
        >   hcp-deployer-version: '1.1.0'
        >  
        > ID: com.example.demo.basic
        > version: 0.1.0
        > ```

        The example above instructs the SAP BTP to:

        -   Validate the Multitarget Application against the MTA specification version `3.1`
        -   Use deploy features specific to the SAP BTP marked as version `1.0`
        -   Deploy the Multitarget Application as a Solution with ID `com.example.demo.basic`
        -   Consider the Multitarget Application version as a version `0.1.0`

    3.  Create the module that describes the Java application. In the `mtad.yaml`, add the following data:

        > ### Example:  
        > ```
        > modules:
        >   - name: example-java-app
        >     type: com.sap.java
        >     requires:
        >       - name: db-binding
        >     parameters:
        >        name: example
        >        jvm-arguments: -server
        >        java-version: JRE 7
        >        runtime: neo-java-web
        >        runtime-version: 1
        > ```

        The example above instructs the SAP BTP to:

        -   Deploy a Java application with a specific runtime, Java version, and runtime arguments
        -   Require a MTA resource called `db-bindings`, where you describe your binding data

    4.  Describe the database binding `id` and the database credentials the Java application has to use by adding the following to the `mtad.yaml`:

        > ### Example:  
        > ```
        > 
        > resources:
        >   - name: db-binding
        >     type: com.sap.hcp.persistence
        >     parameters:
        >       id:
        > ```

        The example above instructs the SAP BTP to create a database binding during the deployment process.


2.  At this point of the procedure, no database `id` or credentials for your database binding have been added. The reason for this is that all the content of the `mtad.yaml` so far is a target-platform independent, meaning that the same `mtad.yaml` could be deployed to multiple SAP BTP subaccounts. The information about your database `id` and credentials are, however, subaccount-specific. To keep the `mtad.yaml` target platform independent, you have to create an MTA extension descriptor. This file is used in addition to your primary descriptor file, and contains data that is account-specific.

    > ### Note:  
    > Security-sensitive data, for example database credentials, should be always deployed using an MTA extension descriptor, so that this data is encrypted.

3.  Create the MTA extension descriptor:

    1.  Create an empty text file, and name it `dev.mtaext`.

    2.  Using a text editor, enter the following data in the file:

        > ### Example:  
        > ```
        > _schema-version: '3.1'
        > ID: com.example.demo.basic.config
        > extends: com.example.demo.basic
        > parameters:
        >   title: Basic Solution
        >   description: This is a sample of a basic Solution.
        >    
        > resources:
        >   - name: db-binding
        >     parameters:
        >       id: dbalias
        >       user-id: myuser
        >       password : mypassword
        > ```

        The example above instructs the SAP BTP to:

        -   Extend the `com.example.demo.basic` MTA deployment descriptor with the `com.example.demo.basic.config` MTA extension descriptor
        -   Define the title and description for the target solution that will be visible in the SAP BTP
        -   Extend the `db-binding` resource and define within the following parameters:

            -   Alias of the database
            -   User for the database schema that you own
            -   Password for the database schema that you own.

            At this point of the procedure, the MTA deployment descriptor, MTA extension descriptor, and the Java application `.war` files are compiled. You can now package your Multitarget Application archive and deploy it to the SAP BTP. The MTA archive contains all entities that have to be deployed. It also contains a manifest file, which links the modules and resources described into the MTA deployment descriptor file using their location in the archive. Using this data, the SAP BTP deploys the Multitarget Application archive as a solution.



4.  Packaging your Multitarget Application

    1.  Create an empty text file and name it `MANIFEST.MF`. Explicitly use upper-case letters.

    2.  Using a text editor, enter the following data in the file:

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

        The example above instructs the SAP BTP to link the module `example-java-app` to the archive `example.war`.

        > ### Caution:  
        > Make sure that the `MANIFEST.MF` is compliant to the JAR file specification.


5.  Create your Multitarget Application archive.

    MTA archives are compliant to the JAR file specification. This allows you to use commonly available tools for creating, modifying, and signing such archives. For the sake of the tutorial, we assume that you have a root directory named `/` where you place all the parts of the Multitarget Application before creating the archive.

    1.  Create a folder called `META-INF` in the root directory.

    2.  Place the `mtad.yaml` and the `MANIFEST.MF` files inside the `META-INF` directory.

    3.  Place the `example.war` archive inside the root directory.

        > ### Note:  
        > The MTA extension descriptor file is deployed separately from the MTA archive.

        The root directory should now be structured as follows::

        > ### Example:  
        > ```
        > /example.war
        > /META-INF
        > /META-INF/mtad.yaml
        > /META-INF/MANIFEST.MF
        > ```

    4.  Archive the content of the root directory in an `.mtar` format using an archiving tool capable of producing a JAR archive.





<a name="loio4b108e8150a54f15ab052c8a7fd67e6c__result_dvm_41l_nz"/>

## Results

After you have created your Multitarget Application archive, you are ready to deploy it into the SAP BTP as a solution. To deploy the archive, proceed as described in [Deploy a Standard Solution](deploy-a-standard-solution-fea07de.md).

