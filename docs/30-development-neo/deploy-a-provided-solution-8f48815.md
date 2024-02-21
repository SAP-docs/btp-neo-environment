<!-- loio8f48815322ee4b9890b31b92ba673b97 -->

# Deploy a Provided Solution

You can deploy a solution locally to your subaccount and provide it for a subscription to another subaccount.



## Prerequisites

-   Ensure that the MTA archive containing your solution is created as described in [Multitarget Applications in the Cloud Foundry Environment](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/d04fc0e2ad894545aebfd7126384307c.html "A Multitarget application (MTA) is essentially a single application that consists of multiple parts. These parts are created using various technologies and share the same lifecycle.") :arrow_upper_right:.
-   Optionally, you have created an extension description as described in [Defining MTA Extension Descriptors](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/50df803465324d36851c79fd07e8972c.html "") :arrow_upper_right:.

    > ### Note:  
    > Several extension descriptors can be additionally used after initial deployment, that is, you can extend one extension descriptor with another unlimited times. You can use this approach if you want your subscribers to define their own data.

-   You have a valid role for your subaccount as described in [Operating Solutions](operating-solutions-2abf7d4.md).
-   You have sufficient resources available in your subaccount to deploy the content of the Multi-Target Application.

    > ### Note:  
    > -   If you are performing a re-deploy, the already deployed parts of the Multi-Target Application are deleted first, so you are not required to have additional resources available in your subaccount.
    > -   If parts of your solution have to be deployed to the subscribers subaccounts, note that those parts consume the resources of those subaccounts.




## Context

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**



<a name="loio8f48815322ee4b9890b31b92ba673b97__steps_fgc_ykz_sy"/>

## Procedure

1.  Log on to the cockpit and select a subaccount.

2.  Choose *Solutions* in the navigation area.

3.  Choose *Deploy*.

    The *Deploy a Solution from an MTA Archive* dialog box appears.

4.  Navigate to the location of the MTA archive and select the one you want to deploy.

5.  \(Optional\) You can provide the location of an MTA extension descriptor file.

    Alternatively, as of `_schema version` `3.1`, if you do not provide it and your solution has missing data required for productive use, you can enter that data manually in the dialog subsection that appears. Keep in mind that you have to input complex parameters such as lists and maps in JSON format. For example, an account-level destination parameter `additional-properties` should be a map that has a value similar to `{"additional.property.1": "1", "additional.property.2": "2"}`.

6.  Select the *Provider deploy* checkbox.

7.  Choose *Deploy* to deploy the MTA archive and the optional MTA extension descriptor to the cloud platform.

    The *Deploy a Solution from an MTA Archive* dialog remains on the screen while the deployment is in progress. When the deployment is completed, a confirmation appears that the solution has been successfully deployed. If you close the dialog during deployment, you can open it again by choosing *Check Progress* of the corresponding operation, located on the *Ongoing Operations* table in the Solution overview page. You can open the page by choosing the tile of the solution that is being deployed.

    > ### Note:  
    > If you experience issues during the deployment process, see [Troubleshooting](troubleshooting-b3f6b49.md).

8.  \(Optional\) When deploying against `_schema version``3.1`, if you have manually entered parameters during deployment, at the end of the process you can use the option to download an extension descriptor containing only those parameters.

    > ### Note:  
    > Parameters marked as security sensitive, either by default or as set in the `mtad.yaml`, are not saved to this extension descriptor.




## Results

Your newly deployed solution appears in the *Solutions Provided for Subscription* category in the *Solutions* page in the cockpit. Each solution component originates from a certain MTA module or resource that in turn can result in several solution components. That is, one MTA module or resource corresponds to given solution components.

> ### Note:  
> If you want to create an MTA extension descriptor, for the еxtension ID you have to use the value of the *Еxtension ID* parameter, which you can find in the page of the solution you have just deployed.

**Related Information**  


[deploy-mta](../50-administration-and-ops-neo/deploy-mta-1e12331.md "This command deploys Multitarget Application (MTA) archives. One or more than one MTA archives can be deployed to your subaccount in one go.")

