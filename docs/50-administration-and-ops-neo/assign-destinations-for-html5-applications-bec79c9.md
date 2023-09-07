<!-- loiobec79c93f82d407faa333554f8c8647d -->

# Assign Destinations for HTML5 Applications

If an HTML5 application requires connectivity to one or more back-end systems, destinations must be created or assigned.



## Prerequisites

A destination to the back-end system exists.



## Context

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**

For the active application version the referenced destinations are displayed in the *HTML5 Application* section of the cockpit. For a non-active application version the referenced destinations are displayed in the details table in the *Versioning* section. HTML5 applications use HTTP destinations, which can be defined on the level of your subaccount.

By default, the destination with the same name as the name you defined for the route in the application descriptor is assigned. If this destination does not exist, you can create the destination with the same name as described in [Configure Destinations from the Cockpit](https://help.sap.com/viewer/b865ed651e414196b39f8922db2122c7/Cloud/en-US/60735ad11d8a488c83537cdcfb257135.html "") :arrow_upper_right:. Then you can assign this newly created destination. Alternatively, you can assign another destination that already exists in your subaccount. To assign a destination, follow the steps below.



<a name="loiobec79c93f82d407faa333554f8c8647d__steps_g25_5g1_p5"/>

## Procedure

1.  Log on with a user \(who is a subaccount member\) to the SAP BTP cockpit.

2.  Choose *Applications* \> *HTML5 Applications* in the navigation area, and choose the application for which you want to assign a different destination \(than the default one\) from your subaccount global destinations.

3.  Choose *Edit* in the *Required Destinations* table.

4.  In the *Mapped Subaccount Destinations* column, choose an existing destination from the dropdown list.


