<!-- loio0dd61c3e5d1d4d6cbea9aec94b7f4725 -->

# Launch SAP HANA XS Applications

You can open your SAP HANA XS applications in a Web browser directly from the cockpit.



<a name="loio0dd61c3e5d1d4d6cbea9aec94b7f4725__context_gps_2s1_hcb"/>

## Context

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of the following technology portfolios: application development; process automation; integration; data, analytics, and enterprise planning; artificial intelligence. The platform offers users the ability to turn data into business value, compose end-to-end business processes, connect entire IT landscapes, and personalize, build and extend SAP applications. This reduces the overall total cost of ownership maintaining SAP landscapes and third-party software across end-to-end business processes.") :arrow_upper_right:.**

> ### Note:  
> This feature is only available for SAP HANA XS applications in single container SAP HANA systems. For SAP HANA XS applications in SAP HANA tenant database systems, use SAP Web IDE or SAP HANA cockpit to manage your applications.



## Procedure

1.  In the SAP BTP cockpit, navigate to a subaccount. For more information, see [Navigate in the Cockpit](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/0874895f1f78459f9517da55a11ffebd.html "Learn how to navigate to your global accounts, directories, and subaccounts in the SAP BTP cockpit.") :arrow_upper_right:.

2.  Choose *Applications* \> *HANA XS Applications*.

3.  In the *HANA XS Applications* table, click the application URL link to launch the application.

    > ### Note:  
    > If an HTTP status 404 \(not found\) error is shown, bear in mind that the cockpit displays only the root of an application’s URL path. This means that you might have to either:
    > 
    > -   Add the application name to the URL address in the browser, for example, `hello.xsjs`.
    > 
    > -   Use an `index.html` file, which is the default setting for the file displayed when the package is accessed without specifying a file name in the URL.
    > 
    > -   Override the above default setting by specifying the *default\_file* keyword in the `.xsaccess` file, for example:
    > 
    >     ```json
    >     {
    >     "exposed" : true,
    >     "default_file": "hello.xsjs"
    >     }
    >     ```


