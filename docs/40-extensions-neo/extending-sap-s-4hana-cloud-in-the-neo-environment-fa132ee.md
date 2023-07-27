<!-- loiofa132ee4bd3a4505a315ed3a8af8feae -->

# Extending SAP S/4HANA Cloud in the Neo Environment

This section guides you through the configuration tasks that you need to perform to enable the SAP BTP, Neo environment for developing extension applications for your SAP S/4HANA Cloud tenant.

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://launchpad.support.sap.com/#/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**



<a name="loiofa132ee4bd3a4505a315ed3a8af8feae__section_h3w_wdk_ndb"/>

## Overview

With the extension capabilities of SAP BTP, you can create SAP S/4HANA Cloud side-by-side extensions: they extend the SAP S/4HANA Cloud functionality but reside on the cloud platform.

To do that, you need to own an SAP S/4HANA Cloud tenant. The authentication against the SAP S/4HANA Cloud tenant is based on the Identity Authentication tenant that is provided together with the SAP S/4HANA Cloud tenant. Typically, you configure this Identity Authentication tenant to forward authentication requests to your corporate identity provider.



<a name="loiofa132ee4bd3a4505a315ed3a8af8feae__section_hyx_4vl_2bb"/>

## Prerequisites

-   Your company has an enterprise account for the cloud platform.
-   You have a user account on the platform with administrative permissions for the enterprise of your company and you can use the SAP BTP cockpit.




<a name="loiofa132ee4bd3a4505a315ed3a8af8feae__section_mdb_34b_mdb"/>

## Process Flow

You have to configure the cloud platform extension integration with SAP S/4HANA Cloud to enable the use of applications running on top of the platform from SAP S/4HANA Cloud.

These are the steps you need to follow:

1.  Set up the subaccount in SAP BTP by configuring the single sign-on \(SSO\). See [Configuring Single Sign-On Between SAP S/4HANA Cloud and SAP BTP, Neo Environment](configuring-single-sign-on-between-sap-s-4hana-cloud-and-sap-btp-neo-environment-a41018f.md) 

2.  Configure the extension application and create the respective destination in the SAP BTP cockpit. See [Configuring the Extension Application](configuring-the-extension-application-4aa230f.md).


