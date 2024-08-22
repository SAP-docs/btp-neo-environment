<!-- loio44dc673f6dd7454993969b6d6f1ed1be -->

# sdk-upgrade



> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of the following technology portfolios: application development; process automation; integration; data, analytics, and enterprise planning; artificial intelligence. The platform offers users the ability to turn data into business value, compose end-to-end business processes, connect entire IT landscapes, and personalize, build and extend SAP applications. This reduces the overall total cost of ownership maintaining SAP landscapes and third-party software across end-to-end business processes.") :arrow_upper_right:.**



Use this command to upgrade the SAP BTP SDK for Neo environment that you are currently working with.

```
neo sdk-upgrade
```

The command checks for a more recent version of the SDK and then upgrades the SDK. There are two possible cases:

-   Your SDK version is up to date and no upgrade is needed.

-   Your SDK version is not up to date and an upgrade process is triggered.

    Then an upgrade of the SDK is triggered. The old SDK is backed up in case something goes wrong with the upgrade.

    > ### Note:  
    > All files and servers that you add to your SDK will be preserved during upgrade.




## Example

```
neo sdk-upgrade
```

