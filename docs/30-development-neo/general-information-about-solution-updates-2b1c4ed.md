<!-- loio2b1c4ed52baa47709b292ace285360b1 -->

# General Information About Solution Updates

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**

To enhance your solution with new capabilities or technical improvements, you can update it using the cockpit. Depending on the deployer version \(`hcp-deployer-version`\) described in the MTA deployment descriptor, SAP BTP uses one of the following technical approaches, where several distinctions apply.



<a name="loio2b1c4ed52baa47709b292ace285360b1__section_tv3_dvc_wbb"/>

## Redeployment

When you update your solution against deployer version `1.0` or `1.1.0`, the update is treated as a redeployment, which means:

-   Any new components that have now been described in the MTA deployment descriptor are deployed as usual.
-   Any already existing components are redeployed or updated, depending on their current runtime state in the SAP BTP.
-   Only relations are removed to components, which are no longer present in the MTA deployment descriptor of the new solution version. The component artefacts are **not** removed.



<a name="loio2b1c4ed52baa47709b292ace285360b1__section_jsx_2vc_wbb"/>

## Update with Full Semantics

When you update your solution against deployer version `1.2` or `1.2.0`, the update is treated as an update with full semantics, which means:

-   Any new components that have now been described in the MTA deployment descriptor are deployed as usual.
-   Any already existing components are redeployed or updated, depending on their current runtime state in the SAP BTP.
-   Components that are no longer present in the MTA deployment descriptor are removed.

> ### Note:  
> The version of the MTA has to follow the “semver” Semantic Versioning specification, for example `1.1.2`.

**Related Information**  


[Updating Solutions](updating-solutions-4bec3f1.md)

[Update Options and Examples](update-options-and-examples-ed31d24.md)

[http://semver.org](http://semver.org)

