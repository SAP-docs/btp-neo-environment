<!-- loio56e309f496cc446ba441d862db94cb18 -->

# Console Client Commands



> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**



<a name="loio56e309f496cc446ba441d862db94cb18__section_xfj_hqz_s2b"/>

## Prerequisites

To use the console client commands, you have to:

1.  Download and install the SDK for SAP BTP,Neo environment and set up the console client. See [Set Up the Console Client](../30-development-neo/set-up-the-console-client-7613dee.md).

2.  Open the console client. See [Using the Console Client](using-the-console-client-8900b22.md).




## Commands

> ### Note:  
> You may need admin permissions in the cloud cockpit to be able to run some of these commands listed below.


<table>
<tr>
<th valign="top">

Group



</th>
<th valign="top">

Commands



</th>
</tr>
<tr>
<td valign="top">

Local Server



</td>
<td valign="top">

[install-local](install-local-8527947.md); [deploy-local](deploy-local-8fdc143.md); [start-local](start-local-cd54325.md); [stop-local](stop-local-ee02d4d.md)



</td>
</tr>
<tr>
<td valign="top">

Deployment



</td>
<td valign="top">

[deploy](deploy-937db4f.md); [start](start-cc417d7.md); [status](status-d4f6592.md)

[stop](stop-b5bfcbf.md); [restart](restart-7c0f7a1.md); [undeploy](undeploy-7e09b85.md)

[disable](disable-59fedc1.md); [enable](enable-13a70e0.md);

[list-applications](list-applications-6942ec5.md); [list-runtimes](list-runtimes-49bb201.md); [list-runtime-versions](list-runtime-versions-20e08d3.md);

[display-application-properties](display-application-properties-7ed175c.md); [set-application-property](set-application-property-113e957.md); [start-maintenance](start-maintenance-f42be92.md); [stop-maintenance](stop-maintenance-3fbd6fe.md);

[rolling-update](rolling-update-3f5d412.md); [hot-update](hot-update-7ae6493.md);

 [clear-downtime-app](clear-downtime-app-c9ae25a.md); [set-downtime-app](set-downtime-app-1672997.md) 



</td>
</tr>
<tr>
<td valign="top">

Logging



</td>
<td valign="top">

[list-logs](list-logs-1f6a77c.md); [get-log](get-log-d35f392.md) 

[list-loggers](list-loggers-9033ddc.md); [set-log-level](set-log-level-1b495d7.md); [reset-log-levels](reset-log-levels-b14bd37.md)



</td>
</tr>
<tr>
<td valign="top">

Monitoring



</td>
<td valign="top">

[list-availability-check](list-availability-check-d37bcfc.md); [create-availability-check](create-availability-check-83d4582.md); [delete-availability-check](delete-availability-check-2a387e4.md) 

[list-jmx-checks](list-jmx-checks-c6fedee.md); [create-jmx-check](create-jmx-check-298a207.md); [delete-jmx-check](delete-jmx-check-75a0058.md)

[list-alert-recipients](list-alert-recipients-f326f9d.md); [set-alert-recipients](set-alert-recipients-6dae74f.md); [clear-alert-recipients](clear-alert-recipients-0f2b2cd.md)



</td>
</tr>
<tr>
<td valign="top">

Keystore



</td>
<td valign="top">

 [list-keystores](list-keystores-fa3c4af.md); [upload-keystore](upload-keystore-dea2506.md); [download-keystore](download-keystore-b45597c.md); [delete-keystore](delete-keystore-0c8539c.md);



</td>
</tr>
<tr>
<td valign="top">

Connectivity



</td>
<td valign="top">

[put-destination](put-destination-9b9f742.md)

[get-destination](get-destination-bc62335.md)

[delete-destination](delete-destination-b5ccd2f.md)



</td>
</tr>
<tr>
<td valign="top">

SAP HANA / SAP ASE



</td>
<td valign="top">

[list-application-datasources](list-application-datasources-9fe84fe.md); [list-dbms](list-dbms-1ea1771.md); [list-dbs](list-dbs-f94d5a2.md); [list-schemas](list-schemas-548e187.md) 

[create-schema](create-schema-05ebe39.md); [bind-schema](bind-schema-ce689b2.md); [unbind-schema](unbind-schema-41e70ab.md); [delete-schema](delete-schema-82a9911.md); [display-schema-info](display-schema-info-0a8638d.md)

[bind-hana-dbms](bind-hana-dbms-affa782.md); [unbind-hana-dbms](unbind-hana-dbms-de4022e.md)

[create-db-ase](create-db-ase-01a2177.md); [create-db-user-ase](create-db-user-ase-487b85d.md); [set-db-user-password-ase](set-db-user-password-ase-25a47c8.md); [display-db-info](display-db-info-064d301.md); [set-db-properties-ase](set-db-properties-ase-5b6f210.md); [bind-db](bind-db-2a4e62e.md); [unbind-db](unbind-db-46e24bb.md); [delete-db-ase](delete-db-ase-9f0785d.md); [delete-db-user-ase](delete-db-user-ase-b280fa0.md)

[create-db-hana](create-db-hana-f64390e.md); [set-db-properties-hana](set-db-properties-hana-a1c73b1.md); [start-db-hana](start-db-hana-bf6020d.md); [stop-db-hana](stop-db-hana-c76fc39.md); [delete-db-hana](delete-db-hana-628ae80.md)[copy-db-hana-certificates](copy-db-hana-certificates-acb8f74.md)

[grant-schema-access](grant-schema-access-830e9ec.md); [revoke-schema-access](revoke-schema-access-a92c08a.md); [list-schema-access-grants](list-schema-access-grants-371711d.md)

[open-db-tunnel](open-db-tunnel-9e3f90f.md); [close-db-tunnel](close-db-tunnel-c7c36e6.md)

[restart-hana](restart-hana-6b5dea0.md)

[grant-db-tunnel-access](grant-db-tunnel-access-7791e70.md); [revoke-db-tunnel-access](revoke-db-tunnel-access-616309e.md); [list-db-tunnel-access-grants](list-db-tunnel-access-grants-21e4be8.md)

[grant-db-access](grant-db-access-e7d72bf.md); [list-db-access-permissions](list-db-access-permissions-28a6218.md); [revoke-db-access](revoke-db-access-a0265c4.md)



</td>
</tr>
<tr>
<td valign="top">

Document Service



</td>
<td valign="top">

[add-ecm-tenant](add-ecm-tenant-8b08f49.md); [create-ecm-repository](create-ecm-repository-acf1b72.md); [delete-ecm-repository](delete-ecm-repository-fb09811.md); [display-ecm-repository](display-ecm-repository-ed676ca.md); [edit-ecm-repository](edit-ecm-repository-279edd1.md); [list-ecm-repositories](list-ecm-repositories-169e3ae.md); [reset-ecm-key](reset-ecm-key-5434b2d.md)



</td>
</tr>
<tr>
<td valign="top">

Subaccounts and Entitlements



</td>
<td valign="top">

[create-account](create-account-05f96cf.md); [delete-account](delete-account-8bd9552.md); [list-accounts](list-accounts-2abad16.md); [set-quota](set-quota-4108f0f.md)



</td>
</tr>
<tr>
<td valign="top">

Subscription Management



</td>
<td valign="top">

[subscribe](subscribe-4c6203d.md); [unsubscribe](unsubscribe-862d00e.md); [list-subscribed-accounts](list-subscribed-accounts-034244c.md); [list-subscribed-applications](list-subscribed-applications-67d5c6f.md)



</td>
</tr>
<tr>
<td valign="top">

Application Domains



</td>
<td valign="top">

[add-custom-domain](add-custom-domain-ebc5269.md); [add-platform-domain](add-platform-domain-7afd450.md); [list-application-domains](list-application-domains-51f8bd8.md); [remove-custom-domain](remove-custom-domain-de15ca8.md); [remove-platform-domain](remove-platform-domain-96c6d24.md)



</td>
</tr>
<tr>
<td valign="top">

Custom SSL



</td>
<td valign="top">

[add-ca](add-ca-c102abb.md); [list-cas](list-cas-99d2659.md); [remove-ca](remove-ca-55b61e4.md); [create-ssl-host](create-ssl-host-3c890d5.md); [delete-ssl-host](delete-ssl-host-f7241b7.md); [list-ssl-hosts](list-ssl-hosts-e8fc50c.md); [set-ssl-host](set-ssl-host-2956975.md)

[display-csr](display-csr-d261cd1.md); [generate-csr](generate-csr-f02258d.md)

[bind-domain-certificate](bind-domain-certificate-8722bcb.md); [change-domain-certificate](change-domain-certificate-53aa1f3.md); [delete-domain-certificate](delete-domain-certificate-c3076cc.md); [list-domain-certificates](list-domain-certificates-dfb8438.md); [unbind-domain-certificate](unbind-domain-certificate-f8d24b6.md); [upload-domain-certificate](upload-domain-certificate-bb54abf.md)



</td>
</tr>
<tr>
<td valign="top">

Reverse-Proxy



</td>
<td valign="top">

 [list-proxy-host-mappings](list-proxy-host-mappings-9fbd139.md); [map-proxy-host](map-proxy-host-12b5cc4.md); [unmap-proxy-host](unmap-proxy-host-10ddad9.md) 



</td>
</tr>
<tr>
<td valign="top">

Resources



</td>
<td valign="top">

 [delete-resource \(Beta\)](delete-resource-beta-09aca8e.md) 



</td>
</tr>
<tr>
<td valign="top">

System



</td>
<td valign="top">

 [version](version-7f6d786.md); [sdk-upgrade](sdk-upgrade-44dc673.md) 



</td>
</tr>
<tr>
<td valign="top">

Extensions



</td>
<td valign="top">

 [hcmcloud-create-connection](hcmcloud-create-connection-ba4e8bb.md); [hcmcloud-delete-connection](hcmcloud-delete-connection-1445cb5.md); [hcmcloud-disable-application-access](hcmcloud-disable-application-access-99e8674.md); [hcmcloud-display-application-access-status](hcmcloud-display-application-access-status-75eac93.md); [hcmcloud-enable-application-access](hcmcloud-enable-application-access-da0e8ba.md); [hcmcloud-enable-role-provider](hcmcloud-enable-role-provider-e263f8e.md); [hcmcloud-get-registered-home-page-tiles](hcmcloud-get-registered-home-page-tiles-ba87683.md); [hcmcloud-import-roles](hcmcloud-import-roles-d3dd77e.md); [hcmcloud-list-connections](hcmcloud-list-connections-38f9af2.md); [hcmcloud-register-home-page-tiles](hcmcloud-register-home-page-tiles-d274421.md); [hcmcloud-unregister-home-page-tiles](hcmcloud-unregister-home-page-tiles-60b45a9.md) 



</td>
</tr>
<tr>
<td valign="top">

MTA



</td>
<td valign="top">

 [delete-mta](delete-mta-3d1163e.md);[deploy-mta](deploy-mta-1e12331.md); [display-mta](display-mta-974dbbb.md) ; [list-mtas](list-mtas-b8b51ef.md); [list-mta-operations](list-mta-operations-8029e1a.md); [subscribe-mta](subscribe-mta-ea358be.md) 



</td>
</tr>
<tr>
<td valign="top">

Virtual Machines



</td>
<td valign="top">

[create-vm](create-vm-16f9fab.md); [delete-vm](delete-vm-9adf1b0.md); [list-vms](list-vms-962ccbb.md); [reboot-vm](reboot-vm-bada287.md)

[close-ssh-tunnel](close-ssh-tunnel-c505268.md); [list-ssh-tunnels](list-ssh-tunnels-da73699.md); [open-ssh-tunnel](open-ssh-tunnel-6f8924a.md)

[create-security-rule](create-security-rule-b140be7.md); [delete-security-rule](delete-security-rule-4ffac63.md); [list-security-rules](list-security-rules-64ecd69.md)

[register-access-point](register-access-point-125cba5.md); [unregister-access-point](unregister-access-point-462a3d2.md)

[delete-volume](delete-volume-850e935.md)

[create-volume-snapshot](create-volume-snapshot-04b5e02.md); [delete-volume-snapshot](delete-volume-snapshot-8536a22.md); [display-volume-snapshot](display-volume-snapshot-a96f269.md); [list-volume-snapshots](list-volume-snapshots-b076212.md); [list-volumes](list-volumes-1427051.md)



</td>
</tr>
</table>

