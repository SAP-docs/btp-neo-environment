<!-- loio0cb7e601bac244f0820dfc4b286d120a -->

# Assign Trust Stores to HTTP Destinations

To be able to call SAP BTP services from SAP HANA XS applications, you need to assign a predefined trust store to the HTTP destination that defines the connection details for a specific service. The trust store contains the certificate required to authenticate the calling application.



## Prerequisites

In the SAP HANA repository, you have created the HTTP destination \(`.xshttpdest` file\) to the service to be called. The file must have the `.xshttpdest` extension and be located in the same package as the application that uses it or in one of the application's subpackages.



## Context

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**



<a name="loio0cb7e601bac244f0820dfc4b286d120a__steps_g22_fqz_mm"/>

## Procedure

1.  Log on to the cockpit and choose *Applications* \> *HANA XS Applications*.

2.  In the *HANA XS Applications* screen, select the relevant application.

    The *Application Details* section lists all destinations created for the selected application, together with the subpackage name if the destination file is contained in a subpackage.

3.  Select the relevant destination and choose *Assign Trust Store*.

4.  In the dialog box, select the ***DEFAULT*** trust store from the dropdown box and save your entry. Note that ***DEFAULT*** specifies a predefined trust store containing the certificate required by SAP HANA XS applications.


**Related Information**  


[Maintaining HTTP Destinations](http://help.sap.com/saphelp_hanaplatform/helpdata/en/ca/340c09551c40b7837e773b9d051821/content.htm?frameset=/en/4f/ae6b385138476fa8f3f840240a5dd8/frameset.htm)

