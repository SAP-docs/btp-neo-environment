<!-- loioad423da413994430bfd9564633f7bc52 -->

# Build Samples from the Command Line

You can use the Apache Maven command line tool to run local and cloud integration tests for any of the SDK samples.



## Prerequisites

-   You have downloaded the Apache Maven command line tool. For more information, see the detailed Maven documentation at [http://maven.apache.org](http://maven.apache.org).
-   You are familiar with the Maven build lifecycle. For more information, see [http://maven.apache.org/guides/introduction/introduction-to-the-lifecycle.html](http://maven.apache.org/guides/introduction/introduction-to-the-lifecycle.html).



## Context

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of the following technology portfolios: application development; process automation; integration; data, analytics, and enterprise planning; artificial intelligence. The platform offers users the ability to turn data into business value, compose end-to-end business processes, connect entire IT landscapes, and personalize, build and extend SAP applications. This reduces the overall total cost of ownership maintaining SAP landscapes and third-party software across end-to-end business processes.") :arrow_upper_right:.**



## Procedure

1.  Open the folder of the relevant project, for example, `<sdk>/samples/hello-world`, and then open the command prompt.

2.  Enter the `verify` command with the following profile in order to activate the local integration test:

    ```
    mvn clean verify -P local-integration-tests ...
    ```

    If you are using a proxy, you need to define additional Maven properties as described below in step 4 \(see proxy details\).

3.  Press [ENTER\] to start the build process.

    All phases of the default lifecycle are executed up to and including the verify phase, with the resulting build status shown on completion.

4.  To activate the cloud integration test, which involves deploying the built Web application on a landscape in the cloud, enter the following profile with the additional Maven properties given below:

    ```
    mvn clean verify -P cloud-integration-tests ...
    ```

    -   Landscape host

        The landscape host \(default: `hana.ondemand.com`\) is predefined in the parent `pom.xml` file \(`<sdk>/samples/pom.xml`\) and can be overwritten, as necessary. If you have a developer account, for example, and are therefore using the trial landscape, enter the following:

        ```
        mvn clean verify -P cloud-integration-tests -Dsap.cloud.host=hanatrial.ondemand.com ...
        ```

    -   Account details

        Provide your account, user name, and password:

        ```
        mvn clean verify -P cloud-integration-tests -Dsap.cloud.account=<account> -Dsap.cloud.username=<user name> -Dsap.cloud.password=<password> ...
        ```

    -   Proxy details

        If you use a proxy for HTTPS Internet access, provide your proxy host \(`https.proxyHost`\) and if necessary your proxy port \(`https.proxyPort`\):

        ```
        mvn clean verify -P cloud-integration-tests -Dhttps.proxyHost=<proxy host> -Dhttps.proxyPort=<proxy port> ...
        ```

        > ### Tip:  
        > If your proxy requires authentication, you might want to use the Authenticator class to pass the proxy user name and password. For more information, see [Authenticator](http://docs.oracle.com/javase/7/docs/api/java/net/Authenticator.html). Note that for the sake of simplicity this feature has not been included in the samples.


    > ### Tip:  
    > To avoid having to repeatedly enter the Maven properties as described above, you can add them directly to the `pom.xml` file, as shown in the example below:
    > 
    > ```
    > <sap.cloud.username>p0123456789</sap.cloud.username>
    > ```
    > 
    > You might also want to use environment variables to set the property values dynamically, in particular when handling sensitive information such as passwords, which should not be stored as plain text:
    > 
    > ```
    > <sap.cloud.password>${env.SAP_CLOUD_PASSWORD}</sap.cloud.password>
    > ```


**Related Information**  


[Regions and Hosts Available for the Neo Environment](../10-concepts-neo/regions-and-hosts-available-for-the-neo-environment-d722f7c.md "Each region represents a geographical location (for example, Europe, US East) where applications, data, or services are hosted.")

