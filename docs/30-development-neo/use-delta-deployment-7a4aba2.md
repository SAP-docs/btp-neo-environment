<!-- loio7a4aba21ee7d42eb86bc70c8787611fa -->

# Use Delta Deployment

By using the delta deployment option, you can apply changes in a deployed application faster without uploading the entire set of files tо SAP BTP.



## Context

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**

The `delta` parameter allows you to deploy only the changes between the provided source and the previously deployed content - new content is added; missing content is deleted; existing content is updated if there are changes. The `delta` parameter is available in two commands – `deploy` and `hot-update`.

> ### Note:  
> Use it to save time for development purposes only. For updating productive applications, deploy the whole application.



<a name="loio7a4aba21ee7d42eb86bc70c8787611fa__steps_iwb_x2j_jq"/>

## Procedure

1.  To upload only the changed files from the application WARs, use one of the two approaches:

    -   Deploy the application specifying the `--delta` parameter:

        ```
        neo deploy myapp.properties  --source <file_location> --delta 
        ```

        For the changes to take effect, restart the application.

    -   Upload the delta and apply the changes on an already running application process with the `hot-update` command:

        ```
        neo hot-update myapp.properties  --source <file_location> --strategy <update_strategy> --delta
        ```


    > ### Note:  
    > With the `source` parameter, provide the whole set of files of your application, not only the changed ones.


**Related Information**  


[hot-update](../50-administration-and-ops-neo/hot-update-7ae6493.md "The hot-update command enables a developer to redeploy and update the binaries of an application started on one process faster than the normal deploy and restart. Use it to apply and activate your changes during development and not for updating productive applications.")

[deploy](../50-administration-and-ops-neo/deploy-937db4f.md "Deploying an application publishes it to SAP BTP. Use the optional parameters to make some specific configurations of the deployed application.")

[Deploy on the Cloud with the Console Client](deploy-on-the-cloud-with-the-console-client-030863c.md "Deploying an application publishes it to SAP BTP. During deploy, you can define various specifics of the deployed application using the deploy command optional parameters.")

