<!-- loio2bd48cfaee3f4967b4d3fa3c87cf942b -->

# Configure the SAP Ariba Solution



<a name="loio2bd48cfaee3f4967b4d3fa3c87cf942b__prereq_qdq_zrj_p1b"/>

## Prerequisites

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**

-   Have an SAP Ariba solution with enabled SOAP Web Service APIs.

    To get more information on the available SOAP Web Service APIs, contact your SAP Ariba representative.

-   Be a member of the Customer Administrator or Integration Admin group, or a group with the Administrator or Integration Admin role in the SAP Ariba solution.




## Context

You configure your SAP Ariba solution by creating new integration end point and enabling an integration task.

<a name="loio1fbecef94dd44130a5c54c3fa05ec341"/>

<!-- loio1fbecef94dd44130a5c54c3fa05ec341 -->

## Create New Integration End-Point



## Context

You create an integration end-point in your SAP Ariba solution.



## Procedure

1.  Login into your SAP Ariba solution.

2.  Click the expansion arrow for *Integration Manager*.

    > ### Note:  
    > For example, in the Procure-to-Pay solution, you have to choose *Manage* \> *Core Administration* \> *Integration Manager*.

3.  Choose *End Point Configuration*.

4.  Choose *Create New*. An *End Point Configuration - Create End Point* page opens.

5.  In the *Name* field, enter a name for the end-point.

6.  In the *Type* filed, choose *Inbound*.

7.  In the *HTTP Authentication* section, enter a user ID in the *Login* field and a password in the *Password* field. You will use the user ID and password to authenticate your HTTP calls later.

8.  Save the changes.




<a name="loio1fbecef94dd44130a5c54c3fa05ec341__result_snq_w5j_p1b"/>

## Results

You have created an integration end-point. Now you have to enable an integration task and link it to the integration end-point.

<a name="loioeeaae4b5d8d84e5ba45bddfb8d8ccace"/>

<!-- loioeeaae4b5d8d84e5ba45bddfb8d8ccace -->

## Enable an Integration Task



## Context

You enable an integration task and link it to an already created end-point.



## Procedure

1.  Login into your SAP Ariba solution.

2.  Click the expansion arrow for *Integration Manager*.

    > ### Note:  
    > For example, in the Procure-to-Pay solution, you have to choose *Manage* \> *Core Administration* \> *Integration Manager*.

3.  Choose *Integration Configuration*.

4.  Find the task you want to enable. Select *List All* or enter search criteria and click *Search*.

5.  Choose *Actions* \> *Edit* for this particular task. An *Edit data import/export task* page opens.

6.  For the *Status* field, select *Enabled*.

7.  Use the drop-down menu for the *End point* field to select the end- point you have already created.

    > ### Note:  
    > -   You can view the WSDL file from the *View WSDL* link.
    > 
    > -   Pay attention on the Integration Task *URL* field. This is the web service end-point.

8.  Save the changes.




<a name="loioeeaae4b5d8d84e5ba45bddfb8d8ccace__result_amv_pvj_p1b"/>

## Results

You have successfully enabled an integration task and have linked it to an integration end-point. You can now call the SAP Ariba SOAP Web Service API related to the integration task.

**Related Information**  


[SAP Ariba Strategic Sourcing solutions](https://help.sap.com/viewer/product/ARIBA_SOURCING/cloud/en-US?task=discover_task)

[Common data import and administration guide for SAP Ariba Strategic Sourcing and Supplier Management solutions](https://help.sap.com/viewer/b6d46a2e6c3043d7bb0cbabba4262560/cloud/en-US/0edd1d1418214bcb9cd3579388c4ddf4.html)

[SAP Ariba Procurement solutions](https://help.sap.com/viewer/product/ARIBA_PROCUREMENT/cloud/en-US?task=discover_task)

