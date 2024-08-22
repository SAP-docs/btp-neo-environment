<!-- loiofea07defe09f44c09e03269705550335 -->

# Deploy a Standard Solution

You can deploy a solution that can be consumed only within your subaccount.



## Prerequisites

-   The MTA archive containing your solution is created according to the information in [Multitarget Applications for the Neo Environment](multitarget-applications-for-the-neo-environment-e1bb7eb.md).
-   Optionally, you have created an extension descriptor as described in [Defining MTA Extension Descriptors](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/50df803465324d36851c79fd07e8972c.html "") :arrow_upper_right:.
-   You have a valid role for your subaccount as described in [Operating Solutions](operating-solutions-2abf7d4.md).
-   You have sufficient resources available in your subaccount to deploy the content of the Multitarget Application.

    > ### Note:  
    > If you are performing a redeployment of an MTA, the existing components are first deleted, which means that you do not need additional available resources.




## Context

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of the following technology portfolios: application development; process automation; integration; data, analytics, and enterprise planning; artificial intelligence. The platform offers users the ability to turn data into business value, compose end-to-end business processes, connect entire IT landscapes, and personalize, build and extend SAP applications. This reduces the overall total cost of ownership maintaining SAP landscapes and third-party software across end-to-end business processes.") :arrow_upper_right:.**



## Procedure

1.  Log on to the cockpit and select a subaccount.

2.  Choose *Solutions* in the navigation area.

3.  Choose *Deploy*.

    The *Deploy a Solution from an MTA Archive* dialog box appears.

4.  Navigate to the location of the MTA archive and select it.

5.  \(Optional\) You can provide the location of an MTA extension descriptor file.

    Alternatively, as of `_schema version` `3.1`, if you do not provide it and your solution has missing data required for productive use, you can enter that data manually in the dialog subsection that appears. Keep in mind that you have to input complex parameters such as lists and maps in JSON format. For example, an account-level destination parameter `additional-properties` should be a map that has a value similar to `{"additional.property.1": "1", "additional.property.2": "2"}`.

    > ### Note:  
    > Make sure that you do not select the *Provider deploy* checkbox. If you select it, you will provide your solution for a subscription. For more information, see [Deploy a Provided Solution](deploy-a-provided-solution-8f48815.md).

6.  Choose *Deploy* to deploy the MTA archive and the optional MTA extension descriptor to the SAP BTP.

    The *Deploy a Solution from an MTA Archive* dialog remains on the screen during the process. When the deployment is completed, a confirmation appears that the solution has been successfully deployed. If you close the dialog during deployment, you can open it again by choosing *Check Progress* of the corresponding operation, located on the *Ongoing Operations* table in the solution overview page. You can open the page by choosing the tile of the solution that is being deployed.

    > ### Note:  
    > If you experience issues during the process, see [Troubleshooting](troubleshooting-b3f6b49.md).

7.  \(Optional\) When deploying against `_schema version` `3.1`, if you have manually entered parameters during deployment, at the end of the process you can download an extension descriptor containing only those parameters.

    > ### Note:  
    > Parameters marked as security sensitive, either by default or as set in the `mtad.yaml`, are not saved to this extension descriptor.




## Results

Your newly deployed solution appears in the *Standard Solutions* category in the *Solutions* page in the cockpit.

Each solution component originates from a certain MTA module or resource, which in turn can result in several solution components. That is, one MTA module or resource corresponds to given solution components.

**Related Information**  


[Multitarget Applications for the Neo Environment](multitarget-applications-for-the-neo-environment-e1bb7eb.md "A Multitarget Application (MTA) is a package comprised of multiple application and resource modules, which have been created using different technologies and deployed to different runtimes, but having a common lifecycle. You bundle the modules together, describe them along with their interdependencies to other modules, services, and interfaces, and package them in an MTA.")

[Defining MTA Extension Descriptors](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/50df803465324d36851c79fd07e8972c.html "") :arrow_upper_right:

[Troubleshooting](troubleshooting-b3f6b49.md "")

[Monitor Solutions Using the Cockpit](monitor-solutions-using-the-cockpit-5d5debc.md "When deployed to your SAP BTP subaccount, a solution consists of various solution components. Each solution component originates from a certain MTA module that in turn can result in several solution components. That is, one MTA module corresponds to given solution components.")

[Delete Solutions Using the Cockpit](delete-solutions-using-the-cockpit-0f1844f.md "Delete a solution from your subaccount following the steps for the corresponding solution types.")

