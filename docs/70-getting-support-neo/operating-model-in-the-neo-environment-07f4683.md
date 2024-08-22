<!-- loio07f468373bb34661b753fb6fa4c592b1 -->

# Operating Model in the Neo Environment

An operating model clearly defines the separation of tasks between SAP and the customer during all phases of an integration project.

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of the following technology portfolios: application development; process automation; integration; data, analytics, and enterprise planning; artificial intelligence. The platform offers users the ability to turn data into business value, compose end-to-end business processes, connect entire IT landscapes, and personalize, build and extend SAP applications. This reduces the overall total cost of ownership maintaining SAP landscapes and third-party software across end-to-end business processes.") :arrow_upper_right:.**



Neo environment and its services have been developed on the assumption that specific processes and tasks are the responsibility of the customer. The following table contains all processes and tasks involved in operating the platform and the services and specifies how the responsibilities are divided between SAP and the customer for each individual task. It does not include the operation of systems and devices residing at operational facilities owned by the customer or any other third party, as these are the customer's responsibility.

Changes to the operating model defined for the services in scope are published using the *What's New* \(release notes\) section of the platform. Customers and other interested parties must review the product documentation on a regular basis. If critical changes are made to the operating model, which require action on the customer side, an explicit notification is sent by e-mail to the affected customers.

It is not the intent of this document to supplement or modify the contractual agreement between SAP and the customer for the purchase of any of the services in scope. In the event of a conflict, the contractual agreement between SAP and the customer as set out in the Order Form, the General Terms and Conditions of SAP Cloud Services, the supplemental terms and conditions, and any resources referenced by those documents always takes precedence over this document.

The responsibilities for operating the Neo environment are listed in the service catalog below.

**Service Catalog**


<table>
<tr>
<th valign="top">

Process

</th>
<th valign="top">

Task

</th>
<th valign="top">

SAP

</th>
<th valign="top">

Customer

</th>
</tr>
<tr>
<td valign="top" rowspan="3">

Communication Management

</td>
<td valign="top">

Appoint an English-speaking contact person and communicate the name to SAP. This is required to ensure timely processing of configuration change requests affecting the customer system, interacting with SAP for efficient case processing, and other interaction between SAP and the customer.

</td>
<td valign="top">



</td>
<td valign="top">

x

</td>
</tr>
<tr>
<td valign="top">

Subscribe to the communication channels offered by SAP for receiving prompt information about any service disruptions, critical maintenance activities affecting the customer system, and change requests requiring action on the customer side.

</td>
<td valign="top">



</td>
<td valign="top">

x

</td>
</tr>
<tr>
<td valign="top">

Inform the customer about service disruptions and critical maintenance activities affecting the customer system.

</td>
<td valign="top">

x

</td>
<td valign="top">



</td>
</tr>
<tr>
<td valign="top" rowspan="2">

Asset Management

</td>
<td valign="top">

Management of the hardware and infrastructure resources in the region, from acquisition through disposal. This includes the request and approval process, procurement management, life-cycle management, and disposal management.

</td>
<td valign="top">

x

</td>
<td valign="top">



</td>
</tr>
<tr>
<td valign="top">

Protect IT assets such as systems, network, and data from threats that arise from unauthorized physical access or physical influence on those assets.

</td>
<td valign="top">

x

</td>
<td valign="top">



</td>
</tr>
<tr>
<td valign="top" rowspan="2">

Provisioning

</td>
<td valign="top">

Provisioning of resources and systems to customers in accordance with the ordered package and subscriptions. This includes the allocation and provisioning of technical \(physical and virtual\) resources, such as storage, network, compute units, systems, and database hosts, the deployment of the SAP application software and the proper initial configuration of quotas, service subscriptions, permissions, and trust configuration.

</td>
<td valign="top">

x

</td>
<td valign="top">



</td>
</tr>
<tr>
<td valign="top">

Provide quota according to the ordered package and subscriptions that can be used to enable resources and services \(for example, subscribing to a service\).

</td>
<td valign="top">



</td>
<td valign="top">

x

</td>
</tr>
<tr>
<td valign="top" rowspan="4">

Change Management

</td>
<td valign="top">

Apply regular product increments, as well as corrections to the infrastructure, systems, and services to avoid cases with minimal possible disruption of normal operations. Ensure that all platform changes \(such as updates of the Java runtime or operating system patches, but not of the customer applications\) are evaluated, authorized, prioritized, planned, tested, implemented, documented, and reviewed prior to implementation.

</td>
<td valign="top">

x

</td>
<td valign="top">



</td>
</tr>
<tr>
<td valign="top">

Perform updates of the infrastructure, systems, and services in a bi-weekly cycle if required. Respectively, for selected services \(such as SAP HANA and SAP ASE\), offer self-services for applying controlled updates of new versions. Emergency changes, for example, triggered by Case Management processes, have accelerated testing, approval, and implementation.

</td>
<td valign="top">

x

</td>
<td valign="top">



</td>
</tr>
<tr>
<td valign="top">

-   Ensure prompt delivery of security patches via the Security Patch Management process.

-   Provision new database systems and Java applications with the latest patched versions.

-   Apply the security patches on live customer systems \(Java application runtimes or databases\), in case the patches do not require downtime, or if the vulnerable system puts at risk SAP or other customers.

-   Inform the customers about the availability of security patches.




</td>
<td valign="top">

x

</td>
<td valign="top">



</td>
</tr>
<tr>
<td valign="top">

Adopt the latest patches or updates via the available self-services and by restarting applications when necessary. For example, when a security issue arises.

</td>
<td valign="top">



</td>
<td valign="top">

x

</td>
</tr>
<tr>
<td valign="top" rowspan="3">

Case Management

</td>
<td valign="top">

Process cases reported by the customer according to the Service Level Agreement. The case is recorded and prioritized in the case tracking system \(BCP\). Monitor the status and progress of the case throughout its whole lifecycle and give regular status updates to the customer.

</td>
<td valign="top">

x

</td>
<td valign="top">



</td>
</tr>
<tr>
<td valign="top">

In the event of cases, make reasonable effort to support end users and manage their cases, to explore self-help tools to find already documented solutions, and to liaise with SAP support in the event of new problems to ensure timely processing of cases affecting the resources in the customer account.

</td>
<td valign="top">



</td>
<td valign="top">

x

</td>
</tr>
<tr>
<td valign="top">

Confirm case resolution in the case tracking system \(BCP\).

</td>
<td valign="top">



</td>
<td valign="top">

x

</td>
</tr>
<tr>
<td valign="top" rowspan="2">

Service Requests

</td>
<td valign="top">

Process service requests reported by the customer according to the Service Level Agreement. The service request is recorded and prioritized in the service request tracking system \(BCP\). Monitor the status and progress of the service request throughout its whole lifecycle and give regular status updates to the customer.

</td>
<td valign="top">

x

</td>
<td valign="top">



</td>
</tr>
<tr>
<td valign="top">

Confirm service request completion in the service request tracking system \(BCP\).

</td>
<td valign="top">



</td>
<td valign="top">

x

</td>
</tr>
<tr>
<td valign="top" rowspan="5">

Backup & Restore

</td>
<td valign="top">

Perform a backup of the database systems hosted in the subaccount. A database log backup is done every 10 minutes and stored on the primary storage. Every 2 hours the logs are transferred from primary to secondary storage. Full data backup is done every day.

</td>
<td valign="top">

x

</td>
<td valign="top">



</td>
</tr>
<tr>
<td valign="top">

Restore previously backed-up data to recover to a consistent state. Verify the completeness of the restored data based on log files created during the recovery and smoke tests to verify the system’s consistency.

</td>
<td valign="top">

x

</td>
<td valign="top">



</td>
</tr>
<tr>
<td valign="top">

Give regular status updates to the customer throughout the entire restore procedure.

</td>
<td valign="top">

x

</td>
<td valign="top">



</td>
</tr>
<tr>
<td valign="top">

Collaborate with SAP to ensure timely processing of data restores if required.

</td>
<td valign="top">



</td>
<td valign="top">

x

</td>
</tr>
<tr>
<td valign="top">

Validate logical integrity and consistency of the restored data.

</td>
<td valign="top">



</td>
<td valign="top">

x

</td>
</tr>
<tr>
<td valign="top">

User Access Management

</td>
<td valign="top">

Manage users, permissions, and security configurations within the subaccount.

</td>
<td valign="top">



</td>
<td valign="top">

x

</td>
</tr>
<tr>
<td valign="top" rowspan="2">

System Monitoring

</td>
<td valign="top">

Ensure availability of the customer system according to the Service Level Agreements as agreed in the contractual agreement between SAP and the customer, by active monitoring, prompt issue detection, and case prevention.

</td>
<td valign="top">

x

</td>
<td valign="top">



</td>
</tr>
<tr>
<td valign="top">

Monitor the resource consumption \(memory, CPU, storage\) to detect issues in technical operations.

</td>
<td valign="top">

x

</td>
<td valign="top">



</td>
</tr>
<tr>
<td valign="top">

Malware Management

</td>
<td valign="top">

Ensure that the infrastructure and platform services are free of viruses, spam, spyware, and other malicious software. If malware is detected, an auto-notification is generated, which is assessed and resolved by the operator.

</td>
<td valign="top">

x

</td>
<td valign="top">



</td>
</tr>
<tr>
<td valign="top" rowspan="3">

Application Management

</td>
<td valign="top">

Design, develop, deploy, configure, maintain, and operate the application within the subaccount. This includes maintaining a staged environment for application delivery \(if required\), application resource management, and managing application availability and performance.

</td>
<td valign="top">



</td>
<td valign="top">

x

</td>
</tr>
<tr>
<td valign="top">

Provide infrastructure, tools, and application programming interfaces for the lifecycle management and operations of the application in the subaccount.

</td>
<td valign="top">

x

</td>
<td valign="top">



</td>
</tr>
<tr>
<td valign="top">

Regularly adopt the latest versions of the tools for lifecycle management and operations offered at the [SAP Development Tools site](https://tools.hana.ondemand.com/).

</td>
<td valign="top">



</td>
<td valign="top">

x

</td>
</tr>
<tr>
<td valign="top" rowspan="3">

Network Management

</td>
<td valign="top">

Manage the network isolation of the subaccounts provisioned to the customer.

</td>
<td valign="top">

x

</td>
<td valign="top">



</td>
</tr>
<tr>
<td valign="top">

Operate the network infrastructure transparently for customers, ensuring elasticity, high availability, and security.

</td>
<td valign="top">

x

</td>
<td valign="top">



</td>
</tr>
<tr>
<td valign="top">

Create and manage own Web domain for the application in the subaccount to ensure data isolation.

</td>
<td valign="top">



</td>
<td valign="top">

x

</td>
</tr>
<tr>
<td valign="top">

Penetration Testing

</td>
<td valign="top">

Inform SAP about any penetration testing that shall be performed for the customer account and ask for their approval. Testing is not allowed on any resources shared with other customers. The results, if any, from the test are to be treated strictly as the confidential information of SAP and the customer are not to be shared with any person or entity without explicit written authorization from SAP. Customers are required to share the results with SAP and work together with SAP operations to mitigate or remedy any security issues.

</td>
<td valign="top">



</td>
<td valign="top">

x

</td>
</tr>
<tr>
<td valign="top">

Decommissioning

</td>
<td valign="top">

Ensure the secure deletion of data and/or hardware disposal. This includes the disassembling of systems along with peripherals and their removal from the region. Before dismantling and handover for further use or return to the vendor, the data is wiped securely from the system.

</td>
<td valign="top">

x

</td>
<td valign="top">



</td>
</tr>
</table>

