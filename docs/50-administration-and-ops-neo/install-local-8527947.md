<!-- loio85279476e13c4f178087952d8fc0980d -->

# install-local

This command installs a server runtime in a local folder, by default `<SDK installation folder>/server`.



> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/docs/btp/sap-business-technology-platform/sap-business-technology-platform?version=Cloud) .**



```
neo install-local
```



## Parameters


<table>
<tr>
<th valign="top" colspan="2">

Optional

</th>
</tr>
<tr>
<td valign="top">

`--ajp-port`

</td>
<td valign="top">

AJP port opened by server

`Default`: *8009*

</td>
</tr>
<tr>
<td valign="top">

`--http-non-proxy-hosts`

</td>
<td valign="top">

JVM system property `http.nonProxyHosts`

</td>
</tr>
<tr>
<td valign="top">

`--http-port`

</td>
<td valign="top">

HTTP port opened by server

`Default`: *8080*

</td>
</tr>
<tr>
<td valign="top">

`--http-proxy-host`

</td>
<td valign="top">

JVM system property `http.ProxyHost`

</td>
</tr>
<tr>
<td valign="top">

`--http-proxy-port`

</td>
<td valign="top">

JVM system property `http.ProxyPort`

</td>
</tr>
<tr>
<td valign="top">

`--https-port`

</td>
<td valign="top">

HTTPS port opened by server

`Default`: *8443*

</td>
</tr>
<tr>
<td valign="top">

`--https-proxy-host`

</td>
<td valign="top">

JVM system property `https.ProxyHost`

</td>
</tr>
<tr>
<td valign="top">

`--https-proxy-port`

</td>
<td valign="top">

JVM system property `https.ProxyPort`

</td>
</tr>
<tr>
<td valign="top">

`--jmx-port`

</td>
<td valign="top">

JMX port opened by server \(JVM system property `com.sun.management.jmxremote.port`\)

`Default`: *1717*

</td>
</tr>
<tr>
<td valign="top">

`-l`, `--location`

</td>
<td valign="top">

Local server installation directory

</td>
</tr>
</table>

**Related Information**  


[Deploy Locally with the Console Client](../30-development-neo/deploy-locally-with-the-console-client-937c833.md "The console client allows you to install a server runtime in a local folder and use it to deploy your application.")

