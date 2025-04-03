<!-- loio001180644f8a428bb422cd41caebb95f -->

# Disaster Recovery as Part of the Business Continuity Plan

The cloud platform disaster recovery \(DR\) plan is part of the overall cloud platform business continuity plan, which includes crisis management and process continuity activities that are triggered by a declared disaster.



<a name="loio001180644f8a428bb422cd41caebb95f__section_nmy_cj4_c3b"/>

## What Constitutes a Disaster?

A disaster is declared by SAP when there is a loss of utilities and services, and uncertainty about whether they can be restored within a reasonable period of time. A disaster can be caused by a natural catastrophe or a man-made incident. As long as the production site has power and is connected to the Internet, it’s not considered a disaster.



<a name="loio001180644f8a428bb422cd41caebb95f__section_xzb_dj4_c3b"/>

## How Is a Disaster Declared?

Emergency incidents are assessed by SAP as part of its business continuity plan and an SAP management member with proper authorization must officially declare a disaster to initiate a disaster recovery plan.

If a disaster is declared, operations are moved to a disaster recovery site based on the process laid out in the business continuity plan.



<a name="loio001180644f8a428bb422cd41caebb95f__section_knl_qqp_j3b"/>

## Standard Disaster Recovery

SAP can restore productive tenants from backups as soon as practicable in case of a disaster resulting in the loss of the primary production data center.

As the magnitude of a disaster is unpredictable, a region might not be restored in a reasonable time. In addition, a new infrastructure might need to be set up at a different location, which might require the purchase and setup of new hardware. Therefore, we can't guarantee any fixed recovery timelines.



<a name="loio001180644f8a428bb422cd41caebb95f__section_rtk_bfv_fcc"/>

## In-Metro Disaster Recovery

In-Metro DR is a disaster recovery solution that utilizes synchronous data replication. It has been designed to protect our customers from the impact of local disasters that may affect a single availability zone \(AZ\). By deploying services across multiple AZs within a single region, In-Metro DR ensures that if a disaster occurs in one AZ, the issue is contained within that zone. Meanwhile, the other unaffected AZs continue to function normally, efficiently handling incoming requests.

-   In-Metro DR is offered to customers of SAP BTP cloud services as contractual obligations and includes:

    -   Recovery Point Objective \(RPO\): No more than 5 minutes of data loss.

    -   Recovery Time Objective \(RTO\): Full-service restoration within 2 hours.


-   In-Metro DR solution leverages an active/active HA set up across 2 or more availability zones with a failover for all customers from primary to secondary site. That is, availability zones within a single region

-   Fully functioning availability zones are paired with every primary availability zone, application stack is pre-built with same capacity and compute as the primary availability zone.

-   A written, customer facing DR plan exist and is updated at least once every 12 months.

-   A DR test is performed at least once every 12 months, and the DR documents are revised as needed based on the results.

-   The In-Metro DR solution passes annual audits and receives certifications \(for example, SOC2\).

-   Scope:

    -   For the scope of SAP BTP services, see [SAP BTP Disaster Recovery Overview](https://www.sap.com/about/agreements/policies/cloud-service-specifications.html?search=disaster%20recovery&sort=latest_desc&pdf-asset=caacc9ac-d97e-0010-bca6-c68f7e60039b&page=2).

    -   Includes SAP BTP regions on AWS and Azure



For more information, see [Announcing the New "In-Metro" Disaster Recovery Solution for SAP BTP](https://community.sap.com/t5/technology-blogs-by-sap/announcing-the-new-quot-in-metro-quot-disaster-recovery-solution-for-sap/ba-p/13904013).

