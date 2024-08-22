<!-- loio379278db43c1460e8bad881fa28c810b -->

# Defining MTA Development Descriptors

Multitarget Applications are defined in a development descriptor required for design-time and build purposes.

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of the following technology portfolios: application development; process automation; integration; data, analytics, and enterprise planning; artificial intelligence. The platform offers users the ability to turn data into business value, compose end-to-end business processes, connect entire IT landscapes, and personalize, build and extend SAP applications. This reduces the overall total cost of ownership maintaining SAP landscapes and third-party software across end-to-end business processes.") :arrow_upper_right:.**

The development descriptor \(`mta.yaml`\) defines the elements and dependencies of a Multitarget Application \(MTA\) compliant with the Neo environment.

> ### Note:  
> The MTA development descriptor \(`mta.yaml`\) is used to generate the deployment descriptor \(`mtad.yaml`\), which is required for deploying an MTA to the target runtime. The MTA Archive Builder uses the MTA development descriptor in order to create an MTA archive, including the `mtad.yaml` and the `MANIFEST.MF` file.

An MTA development descriptor contains the following main elements, in addition to the deployment descriptor elements:

-   `path`
-   `build-parameters`

> ### Restriction:  
> The WebIDE currently does not support creating MTA development descriptors for the Neo Environment. You have to create it manually by a text editor of your choice that supports the YAML serialization language.

For more information, see [Multitarget Application Archive Builder](https://help.sap.com/viewer/58746c584026430a890170ac4d87d03b/Cloud/en-US/ba7dd5a47b7a4858a652d15f9673c28d.html).

