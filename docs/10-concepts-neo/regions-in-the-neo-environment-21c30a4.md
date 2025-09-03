<!-- loio21c30a4e491544fc927ecf3a5857c54e -->

# Regions in the Neo Environment

You can deploy applications in different regions. Each region represents a geographical location \(for example, Europe, US East\) where applications, data, or services are hosted.



> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/docs/btp/sap-business-technology-platform/sap-business-technology-platform?version=Cloud) .**



All regions that are available for the Neo environment are exclusively provided by SAP. For an overview of all available regions for the Neo environment, see [SAP Cloud Platform Regions and Service Portfolio](https://help.sap.com/doc/aa1ccd10da6c4337aa737df2ead1855b/Cloud/en-US/3b642f68227b4b1398d2ce1a5351389a.html?scp-env=Neo).



<a name="loio21c30a4e491544fc927ecf3a5857c54e__section_q45_ys5_s3b"/>

## Selecting a Region

A region is chosen at the subaccount level. For each subaccount, you select exactly one region and one environment. The selection of a region is dependent on many factors: For example, application performance \(response time, latency\) can be optimized by selecting a region close to the user. For more information, see *Selecting a Region* in [Regions](https://help.sap.com/viewer/df50977d8bfa4c9a8a063ddb37113c43/Cloud/en-US/38ecf59cdda64150a102cfaa62d5faab.html#loioabaaf083a6574edc8ad30d9cd9a062f3 "You can deploy applications in different regions. Each region represents a geographical location (for example, Europe, US East) where applications, data, or services are hosted.") :arrow_upper_right:.



<a name="loio21c30a4e491544fc927ecf3a5857c54e__section_ktk_1rb_jlb"/>

## Deploying Applications in Regions

When deploying applications, consider that a subaccount is associated with a particular region and that this is independent of your own location. You may be located in the United States, for example, but operate your subaccount in a region in Europe.

To deploy an application in more than one region, execute the deployment separately for each host.

