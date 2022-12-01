<!-- loioe4d818da43af43e1983df8e9e5caadb2 -->

# Audit Log Retrieval API Usage for the Neo Environment

The audit log retrieval API allows you to retrieve the audit logs for your SAP BTP Neo environment account. It follows the OData 4.0 standard, providing the audit log results as OData with collection of JSON entities.

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**



<a name="loioe4d818da43af43e1983df8e9e5caadb2__section_ow1_2rl_ctb"/>

## Prerequisites

Create an OAuth client for platform API and get an access token as described in [Using Platform APIs](../30-development-neo/using-platform-apis-392af9d.md).

Use the following scopes:

-   Read Audit Logs – allow usage of the Audit Log Retrieval API to retrieve audit logs;

-   Manage Audit Logs – allow usage of the Audit Log Retention API to read retention and set custom retention.




<a name="loioe4d818da43af43e1983df8e9e5caadb2__section_ij5_sfq_hdb"/>

## Example: Get audit logs for the last 30 days

To achieve this you need to execute a similar GET request:

```
https://api.<region host>/auditlog/v1/accounts/<account>/AuditLogRecords?$count=true
```

> ### Note:  
> The account provided as part of the URL should be the randomly generated technical name of the subaccount not the Display Name.

To authenticate, in the header provide the taken OAuth token similar to: "***Authorization: Bearer 41fce723412c6c18961f7e95d911ad37***"

The returned results are split on pages with size – the server page size, which by default is set to 1000 records per server page. If the number of results is higher than the default server page size, in the response *@odata.nextLink* would be provided with the URL, to retrieve the next results' chunk.



<a name="loioe4d818da43af43e1983df8e9e5caadb2__section_zwv_sfq_hdb"/>

## Example: Get audit log filtering by time \(UTC+0\), user, category and application

To do this you need to execute a similar GET request:

```
https://api.<region host>/auditlog/v1/accounts/<account>/AuditLogRecords?$filter=(Time le '2017-12-30T17.13.22' or Time eq '2017-12-30T17.13.22') and User eq '<user>' and Category eq '<category>' and Application eq '<application_name>'
```

> ### Note:  
> In the above example you can use all of the OData v4.0 supported logical operators for filtering described in the following documentation, see [Query Options](http://docs.oasis-open.org/odata/odata/v4.0/cs02/part2-url-conventions/odata-v4.0-cs02-part2-url-conventions.html#_Toc372793303).

> ### Note:  
> You can only filter by time \(UTC+0\), user, category and application. You can combine multiple filters in one request.

> ### Note:  
> When filtering by time the format should be: *yyyy-mm-ddThh.MM.ss*

To authenticate, in the header provide the taken OAuth token similar to: "***Authorization: Bearer 41fce723412c6c18961f7e95d911ad37***"

The returned results are split on pages with size – the default server page size. If the number of results is higher than the default server page size, in the response *@odata.nextLink* would be provided with the URL, to retrieve the next results' chunk.

The predefined audit log message categories are:

-   Data protection and privacy related

    -   *audit.data-access* read-access logging records for access to sensitive personal data;

    -   *audit.data-modification* data modification logging records for sensitive personal data.


    Security related

    -   *audit.security-events* logging of general security events like login, logout, and other.;

    -   *audit.configuration* logging of security critical configuration changes.



For more infromation, see [Change Logging and Read-Access Logging](change-logging-and-read-access-logging-93fac8d.md).



<a name="loioe4d818da43af43e1983df8e9e5caadb2__section_l1g_mfq_hdb"/>

## Example: Get audit logs using client-side pagination

To get results based on pages with size 50, first check the total results number, execute a similar GET request:

```
https://api.<region host>/auditlog/v1/accounts/<account>/AuditLogRecords?$count=true
```

To split the pages on a desired size, 50 results per page in this example, execute a similar GET request:

```
https://api.<region host>/auditlog/v1/accounts/<account>/AuditLogRecords?$top=50&$skip=0
```

To get a second page, execute a similar GET request:

```
https://api.<region host>/auditlog/v1/accounts/<account>/AuditLogRecords?$top=50&$skip=50
```

To get a third page, execute a similar GET request:

```
https://api.<region host>/auditlog/v1/accounts/<account>/AuditLogRecords?$top=50&$skip=100
```

Continue the same requesting pattern, until the number of the results returned by count, in the first example of this section, is reached.

To authenticate, in the header provide the taken OAuth token similar to: "***Authorization: Bearer 41fce723412c6c18961f7e95d911ad37***"

> ### Note:  
> If you use client-side pagination and request a client-side page bigger that the server-side default page, the audit log retrieval API will split the requested page in several chunks that would be returned. As a result you will receive a response containing an @odata.nextLink field, where the next data chunk could be retrieved \(for more information, see the *Results*section below\). Go to the next client-side page value only after you have iterated all the chunks the server breaks the result to, which means that there is no @odata.nextLink field as part of the response provided.



<a name="loioe4d818da43af43e1983df8e9e5caadb2__section_mlc_2jq_hdb"/>

## Results

Executing a GET request towards the audit log retrieval API, results in response similar to the one below. The information for the AuditLogRecords can be checked in the metadata OData part. In the “*value*” part you receive the audit log messages in the format shown in the response example. The results returned on page are limited to the server page size. To get the next result page, navigate to the URL provided in *@odata.nextLink*.

> ### Sample Code:  
> ```
> {
>                     "@odata.context": "$metadata#AuditLogRecords",
>                     "value": [
>                     {
>                     "Uuid": "3b8a8b-16247c70836-8",
>                     "Category": "audit.data-access",
>                     "User": "<user>",
>                     "Tenant": "<tenant>",
>                     "Account": "<account>",
>                     "Application": "<application>",
>                     "Time": "2018-03-21T09.00.40.572+0000",
>                     "Message": "Read data access message. \"%void\"The accessed data belongs to {\"type\":\"account\",\"role\":\"account\",\"id\":{\"id :\":\"auditlog\"}} and  read  from object with name \"Auditlog Retrieval API\" and identifier {\"type\":\"Legacy.Object\",\"id\":{\"key\":\"Auditlog Retrieval API\"}} by user null",
>                     "InstanceId": null,
>                     "FormatVersion": "2.2"
>                     }, 
>                     …
>                     {
>                     "Uuid": "33a87d-1621e7debb2-1be",
>                     "Category": "audit.security-events",
>                     "User": "<user>",
>                     "Tenant": "<tenant>",
>                     "Account": "<account>",
>                     "Application": "<application>",
>                     "Time": "2018-03-21T09.00.40.782+0000",
>                     "Message": "Security event message. Security event: "This is my message with custom parameters: &param1, &param2\",\"param1\":\"value of param1\",\"param2\":\"value of param2\"",
>                     "InstanceId": null,
>                     "FormatVersion": "2.2"
>                     },    ],
>                     "@odata.nextLink": "http://localhost:8001/auditlog/v1/accounts/auditlog/AuditLogRecords?$top=5000&$skip=0&$skiptoken=1000"
>                     }
>                     
>                     
>                     //Second Page:
>                     {
>                     "@odata.context": "$metadata#AuditLogRecords",
>                     "value": [
>                     {
>                     "Uuid": "2a70bd-1621a471259-3653",
>                     "Category": "audit.configuration",
>                     "User": "<user>",
>                     "Tenant": "<tenant>",
>                     "Account": "<account>",
>                     "Application": "<application>",
>                     "Time": "2018-03-20T15.59.14.878+0000",
>                     "Message": "Configuration change message. Attribute attributes update from value \"[old value]\" to value \"[new value]\". ",
>                     "InstanceId": null,
>                     "FormatVersion": "2.2"
>                     },
>                     …
>                     {
>                     "Uuid": "33a87d-1621e7debb2-1bf",
>                     "Category": "audit.data-modification",
>                     "User": "<user>",
>                     "Tenant": "<tenant>",
>                     "Account": "<account>",
>                     "Application": "<application>",
>                     "Time": "2018-03-20T15.59.14.898+0000",
>                     "Message": "Data modification message. Attribute attribute1 update from value \"some old value\" to value \"some new value\". Attribute attribute3 update from value \"old Value\" to value \"new Value\". The data  update  from object with name \"object1 display name\" and identifier {\"type\":\"Legacy.Object\",\"id\":{\"key\":\"object1_ID\"}} by user null",
>                     "InstanceId": null,
>                     "FormatVersion": "2.2"
>                     },
>                     ],
>                     "@odata.nextLink": "http://localhost:8001/auditlog/v1/accounts/auditlog/AuditLogRecords?$top=5000&$skip=0&$skiptoken=2000"
>                     }
>                 
> ```

The retrieved audit logs are in JSON format. The semantics of the JSON fields are as follows:


<table>
<tr>
<th valign="top">

JSON field



</th>
<th valign="top">

Semantic description



</th>
</tr>
<tr>
<td valign="top">

UUID



</td>
<td valign="top">

Unique identifier of the audit log message



</td>
</tr>
<tr>
<td valign="top">

Category



</td>
<td valign="top">

Category of the audit log message. It could be one of the predefined audit log types \(audit.security-events , audit.configuration , audit.data-access or audit.data-modification\) or a subcategory provided when invoking the “log” method with “subcategory” parameter \( e.g. audit.data-modification.test , audit.data-access.my-sub-category etc.\)



</td>
</tr>
<tr>
<td valign="top">

User



</td>
<td valign="top">

The user that has executed the auditable event. The result of the user field could be:

-   ***“<userA\>”*** - the user is determined implicitly by audit logging;

-   ***“<userA\> on behalf of <userB\>”*** – the user A is implicitly determined by audit logging and the user B is set by the component writing audit logs and verified by audit logging;

-   ***“on behalf of <userB\>”*** - the user B is set by the component writing audit logs and verified by audit logging;

-   ***“”*** \(empty string\) – no user is determined or verified by audit logging.


> ### Note:  
> Users that are set by the component writing audit logs and not further verified as a validity by audit logging are visible **only** in the “*Message*” field in the “*Custom defined attributes*” part in field “*caller\_user*”.



</td>
</tr>
<tr>
<td valign="top">

Tenant



</td>
<td valign="top">

Tenant ID owner of the auditable event.



</td>
</tr>
<tr>
<td valign="top">

Account



</td>
<td valign="top">

Account ID owner of the auditable event.



</td>
</tr>
<tr>
<td valign="top">

Application



</td>
<td valign="top">

Application that has generated the audit log event.



</td>
</tr>
<tr>
<td valign="top">

Time



</td>
<td valign="top">

Timestamp \(UTC+0\) when the auditable event is generated.



</td>
</tr>
<tr>
<td valign="top">

Message



</td>
<td valign="top">

Audit log message text.



</td>
</tr>
<tr>
<td valign="top">

InstanceId



</td>
<td valign="top">

Instance ID where the event has occurred if applicable.



</td>
</tr>
<tr>
<td valign="top">

FormatVersion



</td>
<td valign="top">

Audit log message format.



</td>
</tr>
</table>

**Related Information**  


[Audit Log Retrieval API for the Neo Environment](https://api.sap.com/api/AuditLogRetrievalAPI/resource)

[API Documentation](../30-development-neo/api-documentation-4570e92.md "API documentation for the Neo environment.")

