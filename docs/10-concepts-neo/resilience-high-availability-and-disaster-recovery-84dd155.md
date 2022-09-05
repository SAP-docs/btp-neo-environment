<!-- loio84dd155500224fe4a7f161d48ee226a9 -->

# Resilience, High Availability, and Disaster Recovery

SAP has a number of processes in place to support resilience in SAP BTP, and provides different offerings so that you can support the high availability of your applications.

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**



<a name="loio84dd155500224fe4a7f161d48ee226a9__section_vyk_lgq_xlb"/>

## How SAP Provides Resilience

SAP applies resilience principles when developing, updating, and deploying our SAP BTP applications and services. In the Neo environment, SAP provides resilience through the following:

-   **Backups and Disaster Recovery**

    In the Neo environment, we back up all SAP BTP components every 24 hours. The backups are replicated to a secondary site, from where they can be restored in case of a disaster. For more information, see [Standard Disaster Recovery](https://help.sap.com/viewer/d4790b2de2f4429db6f3dff54e4d7b3a/Cloud/en-US/fbc3e0daaa79402b816c253a7d2374b7.html) and [Disaster Recovery as Part of the Business Continuity Plan](disaster-recovery-as-part-of-the-business-continuity-plan-0011806.md).

-   **High Availability for SAP HANA**

    If you use the SAP BTP, SAP HANA service, you can set up your databases in high availability mode to increase the availability of your systems. For more information, see [Managing Database Systems in a High Availability Setup](https://help.sap.com/viewer/d4790b2de2f4429db6f3dff54e4d7b3a/Cloud/en-US/cda01a35d6e9401fa9ce8be70b572db4.html).




<a name="loio84dd155500224fe4a7f161d48ee226a9__section_kgz_mgq_xlb"/>

## Best Practices for Resilient Applications

In addition to the services offered by SAP BTP, you can follow our best practices for developing and deploying applications, which help you to make your applications running on SAP BTP stable and highly available:

-   **Develop Resilient Applications**

    When developing your applications, apply the principles and patterns of resilient software design that fit your use case. For more information, see [Developing Resilient Apps on SAP BTP](https://help.sap.com/viewer/eadaa45871804b4a974be865f627e791/Cloud/en-US/d1fe5fd8ecfb46c193221ebb991af3d7.html).

-   **Implement Failover**

    Use a multi-region setup and implement automatic failover to ensure the high availability of your applications. For more information, see [Planning Failover on SAP BTP](https://help.sap.com/viewer/df50977d8bfa4c9a8a063ddb37113c43/Cloud/en-US/8c46464783664ac4a748e70a91e08508.html).


