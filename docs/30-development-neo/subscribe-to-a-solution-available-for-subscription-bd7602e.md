<!-- loiobd7602e168604227a0d890c108395da3 -->

# Subscribe to a Solution Available for Subscription

You can subscribe to a solution that has been provided for subscription by another subaccount in the cockpit.



## Prerequisites

-   You have a valid role for your subaccount as described in [Operating Solutions](operating-solutions-2abf7d4.md).
-   There is a solution available for subscription in your subaccount. That is, you have been granted with an entitlement from the provider of the solution.
-   You have sufficient resources available in your subaccount to deploy the content of the Multi-Target Application.

    > ### Note:  
    > Typically, parts of a provided for subscription solution are deployed to the providers subaccount and parts of it within your subaccount. The parts of the solution deployed to your subaccount consume your resources, while the parts of the solution deployed to the providers subaccount consume the resources the provider subaccount.




## Context

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**



<a name="loiobd7602e168604227a0d890c108395da3__steps_x1w_zlz_sy"/>

## Procedure

1.  Log on to the cockpit and select a subaccount.

2.  Choose *Solutions* in the navigation area.

3.  All solutions that you can subscribe to are listed in the *Solutions Available for Subscription* category. Select the tile of a solution that is available for subscription and then choose *Subscribe*.

    The *Subscribe to a Solution* dialog box appears.

4.  \(Optional\) Input the location of the provider-derived MTA extension descriptor file.

    Alternatively, as of `_schema version` `3.1`, if you do not provide it and your solution has missing data required for productive use, you can enter that data manually in the dialog subsection that appears. Keep in mind that you have to input complex parameters such as lists and maps in JSON format. For example, an account-level destination parameter `additional-properties` should be a map that has a value similar to `{"additional.property.1": "1", "additional.property.2": "2"}`.

    > ### Note:  
    > Ensure that your extension descriptor file extends correctly the solution you are subscribing to. To do so, check the `Extension ID` of the solution in the*Additional Details* field of the solution overview page in the cockpit, and input it in the `extends` section of your extension descriptor.

5.  Choose *Subscribe* to subscribe to the provided solution, and deploy the optional MTA extension descriptor to the SAP BTP.

    The *Subscribe to a Solution* dialog remains on the screen while the deployment is in progress. When the deployment is completed, a confirmation appears that the solution has been successfully deployed. If you close the dialog during deployment, you can open it again by choosing *Check Progress* of the corresponding operation, located on the *Ongoing Operations* table in the solution overview page. You can open the page by choosing the tile of the solution that is being deployed.

6.  \(Optional\) When deploying against `_schema version``3.1`, if you have manually entered parameters during deployment, at the end of the process you can use the option to download an extension descriptor containing only those parameters.

    > ### Note:  
    > Parameters marked as security sensitive, either by default or as set in the `mtad.yaml`, are not saved to this extension descriptor.

    > ### Remember:  
    > Any resources created in the subscriber account can be updated to the provided state by resubscribing to the privided solution. You can do this either by using the *Update* option in the *Solutions* view of the SAP Cloud Platrform cockpit, or the `subscribe-mta` command of the command line interface.




## Results

The solution to which you are now subscribed appears in the *Subscribed Solutions* category in the *Solutions* page in the cockpit. Each solution component originates from a certain MTA module or resource, which in turn can result in several solution components. That is, one MTA module or resource corresponds to specific solution components.

**Related Information**  




[Defining MTA Extension Descriptors](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/50df803465324d36851c79fd07e8972c.html "") :arrow_upper_right:

[Troubleshooting](troubleshooting-b3f6b49.md "")

[Monitor Solutions Using the Cockpit](monitor-solutions-using-the-cockpit-5d5debc.md "When deployed to your SAP BTP subaccount, a solution consists of various solution components. Each solution component originates from a certain MTA module that in turn can result in several solution components. That is, one MTA module corresponds to given solution components.")

[Delete Solutions Using the Cockpit](delete-solutions-using-the-cockpit-0f1844f.md "Delete a solution from your subaccount following the steps for the corresponding solution types.")

[subscribe-mta](../50-administration-and-ops-neo/subscribe-mta-ea358be.md "This command subscribes the subaccount of the consumer to a Multitarget Application (MTA), which is available for subscription.")

