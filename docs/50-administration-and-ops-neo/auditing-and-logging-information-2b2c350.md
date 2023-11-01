<!-- loio2b2c350cafe54fa587aac6b3c82c11f3 -->

# Auditing and Logging Information

Here you can find a list of the audit log events that are logged by SAP Custom Domain service in the SAP BTP, Neo environment.



<a name="loio2b2c350cafe54fa587aac6b3c82c11f3__section_nvn_nzn_wqb"/>

## How to Read the Audit Log Messages

The object names in the "Event grouping" column and the actions provided in the "How to identify related log events" column provide key information needed to understand the meaning of the custom domain audit log messages. Here's an example for an audit log message:

> ### Example:  
> The data **before create** from **object with name "certificate"** and identifier \{...\} by user <SAP ID\>."

In this example, the message says that a user with <SAP ID\> has initiated the generation of a CSR. If the action is **create finished**, it means that the CSR generation has been completed successfully, while the **create failed** action indicates that the operation has failed.

> ### Note:  
> It's important to pay attention to the object name, because in certain cases the names of the actions coincide. In such cases, the object name will help you distinguish one audit log from another. For example, the "Generate CSR" and "Create SSL host" audit log events have the same actions, but their object names differ.
> 
> There is one case where both the object names and the actions coincide - the "Add custom domain mapping" and "Remove custom domain mapping" audit log events. The value of the `platformUrl` property is what makes the difference here.

The following table contains the object names and actions related to the Custom Domain service audit logs:


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
<td valign="top" rowspan="4">

Events related to SSL hosts

Object name: **sslhost**

</td>
<td valign="top">

Create SSL host

</td>
<td valign="top">

**before create** - Creation of SSL host by <user\>

**create finished** - Creation of SSL host completed

**create failed** - Creation of SSL host failed

</td>
</tr>
<tr>
<td valign="top">

Delete SSL host

</td>
<td valign="top">

**before delete** - Deletion of SSL host by <user\>

**delete finished** - Deletion of SSL host completed

**delete failed** - Deletion of SSL host failed

</td>
</tr>
<tr>
<td valign="top">

Bind certificate

</td>
<td valign="top">

**before bind-certificate** - Bind of uploaded domain certificate to SSL host by <user\>

**bind-certificate finished** - Bind of uploaded domain certificate to SSL host completed

**bind-certificate failed** - Bind of uploaded domain certificate to SSL host failed

</td>
</tr>
<tr>
<td valign="top">

Unbind certificate

</td>
<td valign="top">

**before unbind-certificate** - Unbind of uploaded domain certificate to SSL host by <user\>

**unbind-certificate finished** - Unbind of uploaded domain certificate to SSL host completed

**unbind-certificate failed** - Unbind of uploaded domain certificate to SSL host failed

</td>
</tr>
<tr>
<td valign="top" rowspan="2">

Events related to custom domain mappings

Object name: **sslhost**

</td>
<td valign="top">

Add custom domain mapping

"platformUrl"="example.hana.ondemand.com"

</td>
<td valign="top">

**before update-mapping** - Addition of custom domain mapping by <user\>

**update-mapping finished** - Addition of custom domain mapping completed

**update-mapping failed** - Addition of custom domain mapping failed

</td>
</tr>
<tr>
<td valign="top">

Remove custom domain mapping

"platformUrl"="null"

</td>
<td valign="top">

**before update-mapping** - Removal of custom domain mapping by <user\>

**update-mapping finished** - Removal of custom domain mapping completed

**update-mapping failed** - Removal of custom domain mapping failed

</td>
</tr>
<tr>
<td valign="top" rowspan="2">

Events related to client certificate authentication

Object name: **sslhost**

</td>
<td valign="top">

Configure client certificate authentication

</td>
<td valign="top">

**before configure-client-cert-auth** - Configuration of client certificate authentication by <user\>

**configure-client-cert-auth finished** - Configuration of client certificate authentication completed

**configure-client-cert-auth failed** - Configuration of client certificate authentication failed

</td>
</tr>
<tr>
<td valign="top">

Delete client certificate authentication

</td>
<td valign="top">

**before delete-client-cert-cfg** - Deletion of configured client certificate authentication by <user\>

**delete-client-cert-cfg finished** - Deletion of configured client certificate authentication completed

**delete-client-cert-cfg failed** - Deletion of configured client certificate authentication failed

</td>
</tr>
<tr>
<td valign="top" rowspan="2">

Events related to IP filtering

Object name: **ip-filtering**

</td>
<td valign="top">

Configure IP filtering

</td>
<td valign="top">

**before configure-ip-filtering** - Configuration of IP filtering by <user\>

**configure-ip-filtering finished** - Configuration of IP filtering completed

**configure-ip-filtering failed** - Configuration of IP filtering failed

</td>
</tr>
<tr>
<td valign="top">

Delete IP filtering

</td>
<td valign="top">

**before delete-ip-filtering** - Deletion of configured IP filtering by <user\>

**delete-ip-filtering finished** - Deletion of configured IP filtering completed

**delete-ip-filtering failed** - Deletion of configured IP filtering failed

</td>
</tr>
<tr>
<td valign="top" rowspan="7">

Events related to certificates

Object name: **certificate**

</td>
<td valign="top">

Generate CSR

</td>
<td valign="top">

**before create** - Generation of CSR by <user\>

**create finished** - Generation of CSR completed

**create failed** - Generation of CSR failed

</td>
</tr>
<tr>
<td valign="top">

Upload certificate

</td>
<td valign="top">

**before upload** - Upload of domain certificate by <user\>

**upload finished** - Upload of domain certificate completed

**upload failed** - Upload of domain certificate failed

</td>
</tr>
<tr>
<td valign="top">

Update certificate

Available when you're using the `force` parameter \("forceFlag":"true"\).

</td>
<td valign="top">

**before delete** - Update of domain certificate by <user\>

**delete finished** - Update of domain certificate completed

**before upload** - Update of domain certificate failed

**upload finished** - Update of domain certificate failed

</td>
</tr>
<tr>
<td valign="top">

Update certificate

Available when the `force` parameter is missing \("forceFlag":"null"\), you're not using it \("forceFlag":"false"\), or you're using it \("forceFlag":"true"\), but an error has occurred while uploading or deleting the certificate.

</td>
<td valign="top">

**before update** - Update of domain certificate by <user\>

**update finished** - Update of domain certificate completed

**update failed** - Update of domain certificate failed

</td>
</tr>
<tr>
<td valign="top">

Delete certificate

</td>
<td valign="top">

**before delete** - Deletion of domain certificate by <user\>

**delete finished** - Deletion of domain certificate completed

**delete failed** - Deletion of domain certificate failed

</td>
</tr>
<tr>
<td valign="top">

Upload trusted CA certificate

</td>
<td valign="top">

**before upload-ca** - Upload of trusted CA certificate by <user\>

**upload-ca finished** - Upload of trusted CA certificate completed

**upload-ca failed** - Upload of trusted CA certificate failed

</td>
</tr>
<tr>
<td valign="top">

Delete trusted CA certificate

</td>
<td valign="top">

**before delete-ca** - Deletion of trusted CA certificate by <user\>

**delete-ca finished** - Deletion of trusted CA certificate completed

**delete-ca failed** - Deletion of trusted CA certificate failed

</td>
</tr>
<tr>
<td valign="top" rowspan="3">

Events related to reverse proxy configurations

Object name: **reverse-proxy**

</td>
<td valign="top">

Add proxy host mapping

</td>
<td valign="top">

**before add-proxy-mapping** - Addition of reverse proxy host mapping by <user\>

**add-proxy-mapping finished** - Addition of reverse proxy host mapping completed

**add-proxy-mapping failed** - Addition of reverse proxy host mapping failed

</td>
</tr>
<tr>
<td valign="top">

Update proxy host mapping

</td>
<td valign="top">

**before update-proxy-mapping** - Update of reverse proxy host mapping by <user\>

**update-proxy-mapping finished** - Update of reverse proxy host mapping completed

**update-proxy-mapping failed** - Update of reverse proxy host mapping failed

</td>
</tr>
<tr>
<td valign="top">

Delete proxy host mapping

</td>
<td valign="top">

**before delete-proxy-mapping** - Deletion of reverse proxy host mapping by <user\>

**delete-proxy-mapping finished** - Deletion of reverse proxy host mapping completed

**delete-proxy-mapping failed** - Deletion of reverse proxy host mapping failed

</td>
</tr>
</table>

**Related Information**  


[Audit Logging in the Cloud Foundry Environment](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/f92c86ab11f6474ea5579d839051c334.html)

[Audit Logging in the Neo Environment](https://help.sap.com/viewer/ea72206b834e4ace9cd834feed6c0e09/Cloud/en-US/02c39712c1064c96b37c1ea5bc9420dc.html)

