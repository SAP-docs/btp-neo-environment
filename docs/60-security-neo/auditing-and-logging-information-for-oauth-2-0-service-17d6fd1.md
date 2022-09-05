<!-- loio17d6fd1de6cb447da9ba19c99541e566 -->

# Auditing and Logging Information for OAuth 2.0 Service

Here you can find a list of the security events that are logged by OAuth 2.0 Service.

<a name="loio17d6fd1de6cb447da9ba19c99541e566__table_dqf_pkf_p4b"/>Security events written in audit logs


<table>
<tr>
<th valign="top">

Event grouping



</th>
<th valign="top">

What events are logged



</th>
<th valign="top">

How to identify related log events



</th>
</tr>
<tr>
<td valign="top" rowspan="2">

Authorization code



</td>
<td valign="top">

Issue OAuth authorization code



</td>
<td valign="top">

"action":"create" & "key":"Creating authorization code: <first 5 symbols of the code\>"

Distincted by tenantId:"<tenant id\>"



</td>
</tr>
<tr>
<td valign="top">

Delete OAuth authorization code



</td>
<td valign="top">

"action":"delete" & "key":"Deleting authorization code: <first 5 symbols of the code\>"

Distincted by tenantId:"<tenant id\>"



</td>
</tr>
<tr>
<td valign="top" rowspan="5">

Access token



</td>
<td valign="top">

Issue access token for client credentials flow



</td>
<td valign="top">

"action":"create" & "key":" Creating access token: <first 5 symbols of the token\>"

"action":"create" & "key":"Creating platform access token: <first 5 symbols of the token\>" - when using platform client

Distincted by tenantId:"<tenant id\>"



</td>
</tr>
<tr>
<td valign="top">

Issue access token from authorization code



</td>
<td valign="top">

"action":"create" & "key":"Creating access token: <first 5 symbols of the token\>"

Distincted by tenantId:"<tenant id\>"



</td>
</tr>
<tr>
<td valign="top">

Issue access token from refresh token



</td>
<td valign="top">

"action":"create" & "key":"Creating access token: <first 5 symbols of the token\>" & "key":"Creating refresh token: <first 5 symbols of the token\>"

Distincted by tenantId:"<tenant id\>"



</td>
</tr>
<tr>
<td valign="top">

Issue acccess token from SAML bearer assertion



</td>
<td valign="top">

"action":"create" & "objectID":"Creating access token: <first 5 symbols of the token\>"

Distincted by tenantId:"<tenant id\>"

Further refining of search: "operation":"Create access token from SAML bearer"



</td>
</tr>
<tr>
<td valign="top">

Delete access token



</td>
<td valign="top">

"action":"delete" & "key":"Deleting cloud access token: <first 5 symbols of the token\>"

Distincted by tenantId:"<tenant id\>"



</td>
</tr>
<tr>
<td valign="top">

Refresh token



</td>
<td valign="top">

Create refresh token



</td>
<td valign="top">

"action":"create" & "key":""Creating refresh token: " <first 5 symbols of the token\>"

Distincted by tenantId:"<tenant id\>"



</td>
</tr>
<tr>
<td valign="top" rowspan="3">

OAuth client



</td>
<td valign="top">

Create OAuth client



</td>
<td valign="top">

"action":"create" & "key":"Creating application client: <client id\>"

Distincted by tenantId:"<tenant id\>"



</td>
</tr>
<tr>
<td valign="top">

Update OAuth client



</td>
<td valign="top">

"action":"update" & "key":"Updating application client: <client id\>"

Distincted by tenantId:"<tenant id\>"



</td>
</tr>
<tr>
<td valign="top">

Delete OAuth client



</td>
<td valign="top">

"action":"delete" & "key":"Deleting application client: <client id\>"

Distincted by tenantId:"<tenant id\>"



</td>
</tr>
<tr>
<td valign="top" rowspan="7">

Platform client



</td>
<td valign="top">

Create OAuth platform client



</td>
<td valign="top">

"action":"create" & "key":"Creating platform client: <client id\>"

Distincted by "account":"<account\>"



</td>
</tr>
<tr>
<td valign="top">

Delete OAuth platform client



</td>
<td valign="top">

"action":"delete" & "key":"Deleting platform client: <client id\>"

Distincted by "account":"<account\>"



</td>
</tr>
<tr>
<td valign="top">

Create multi-tenant OAuth platform client



</td>
<td valign="top">

"action":"create" & "objectID":"Creating platform client: <client id\>"

Distincted by "account":"<account\>"

Further refining of search: "operation":"Create Multitenant Platform API client"



</td>
</tr>
<tr>
<td valign="top">

Create admin OAuth platform client



</td>
<td valign="top">

"action":"create" & "key":"Creating platform client: <client id\>"

Distincted by:

-   "account":"<ips\_global\_account\>"

-   "account":"<ias\_resource\_server\>




</td>
</tr>
<tr>
<td valign="top">

Delete admin OAuth platform client



</td>
<td valign="top">

"action":"delete" & "key":"Deleting platform client: <client id\>"

Distincted by:

-   "account":"<ips\_global\_account\>"

-   "account":"<ias\_resource\_server\>




</td>
</tr>
<tr>
<td valign="top">

Create external OAuth platform client



</td>
<td valign="top">

"action":"create" & "objectID":"Creating platform client: <client id\>"

Distincted by:

-   "account":"<ips\_global\_account\>"

-   "account":"<ias\_resource\_server\>


Further refining of search: "operation":"Delete External Platform API client"



</td>
</tr>
<tr>
<td valign="top">

Delete external OAutth platform client



</td>
<td valign="top">

"action":"delete" & "objectID":"Deleting platform client: <client id\>"

Distincted by:

-   "account":"<ips\_global\_account\>"

-   "account":"<ias\_resource\_server\>


Further refining of search: "operation":"Delete External Platform API client"



</td>
</tr>
</table>



The following information is described in the table columns:

-   *Event grouping* - Events that are logged with a similar format or are related to the same entities.

-   *What events are logged* - Description of the security or data protection and privacy related event that is logged.

-   *How to identify related log events* - Search criteria or key words, that are specific for a log event that is created along with the logged event.

-   *Additional information* - Any related information that can be helpful.


**Related Information**  


[Audit Logging in the Cloud Foundry Environment](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/f92c86ab11f6474ea5579d839051c334.html)

[Audit Logging in the Neo Environment](https://help.sap.com/viewer/ea72206b834e4ace9cd834feed6c0e09/Cloud/en-US/02c39712c1064c96b37c1ea5bc9420dc.html)

