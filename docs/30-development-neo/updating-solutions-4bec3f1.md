<!-- loio4bec3f17a2f4482292250fb1d18780da -->

# Updating Solutions



<a name="loio4bec3f17a2f4482292250fb1d18780da__context_zjc_2sc_wbb"/>

## Context

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**

You can update all solution types to a newer version.



## Procedure

1.  Log on to the cockpit and select the subaccount containing the solution you want to update.

2.  Choose *Solutions* in the navigation area.

3.  Choose the tile of the solution you want to update.

4.  On the solution overview page that appears, choose *Update*.

5.  **Only for standard and provided solutions**: provide the location of the MTA archive you want to use.

    > ### Note:  
    > When you update a solution as a solution provider, ensure that the solution ID of the new deployed archive matches the ID of the existing solution.

6.  \(Optional\) You can provide the location of an MTA extension descriptor file.

    Alternatively, as of `_schema version` `3.1`, if you do not provide an MTA extension descriptor and your solution has missing data required for productive use, you can enter that data manually in the dialog subsection that appears. Keep in mind that you have to input complex parameters such as lists and maps in JSON format. For example, an account-level destination parameter `additional-properties` should be a map that has a value similar to `{"additional.property.1": "1", "additional.property.2": "2"}`.

7.  Choose *Update* to start the process.

    > ### Note:  
    > -   Alternatively to the *Update* option, to perform the update operation you can also use the *Deploy* option.
    > -   As an alternative to the cockpit procedure, you can update a solution using the following command line comand:
    > 
    >     > ### Sample Code:  
    >     > ```
    >     > neo deploy-mta --host <host> --account <subaccount_name>  --source <file(1)_location>,<file(2)_location>,...,<file(n)_location> --user <e-mail or user>
    >     > ```




<a name="loio4bec3f17a2f4482292250fb1d18780da__result_dqq_rct_2bb"/>

## Results

The existing solution is updated to a newer version.

**Related Information**  


 <?sap-ot O2O class="- topic/link " href="c4f0d850b6ba46089a76d53ab805c9e6.xml" text="" desc="" xtrc="link:1" xtrf="file:/home/builder/src/dita-all/jjq1673438782153/loio9fe952ba277c471bbad80cd40548bb84_en-US/src/content/localization/en-us/4bec3f17a2f4482292250fb1d18780da.xml" ?> 

[Defining MTA Extension Descriptors](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/50df803465324d36851c79fd07e8972c.html "") :arrow_upper_right:

[Troubleshooting](troubleshooting-b3f6b49.md "")

[Monitor Solutions Using the Cockpit](monitor-solutions-using-the-cockpit-5d5debc.md "When deployed to your SAP BTP subaccount, a solution consists of various solution components. Each solution component originates from a certain MTA module that in turn can result in several solution components. That is, one MTA module corresponds to given solution components.")

[Delete Solutions Using the Cockpit](delete-solutions-using-the-cockpit-0f1844f.md "Delete a solution from your subaccount following the steps for the corresponding solution types.")

[deploy-mta](../50-administration-and-ops-neo/deploy-mta-1e12331.md "This command deploys Multitarget Application (MTA) archives. One or more than one MTA archives can be deployed to your subaccount in one go.")

