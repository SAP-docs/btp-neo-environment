<!-- loiocd54325ba712483489ab93eb1864af57 -->

# start-local

This command starts a local server instance.



> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of the following technology portfolios: application development; process automation; integration; data, analytics, and enterprise planning; artificial intelligence. The platform offers users the ability to turn data into business value, compose end-to-end business processes, connect entire IT landscapes, and personalize, build and extend SAP applications. This reduces the overall total cost of ownership maintaining SAP landscapes and third-party software across end-to-end business processes.") :arrow_upper_right:.**



```
neo start-local
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

`-l`, `--location`

</td>
<td valign="top">

Local server installation directory

</td>
</tr>
<tr>
<td valign="top">

`--shutdown-port`

</td>
<td valign="top">

Shutdown port opened by server

`Default`: *8003*

</td>
</tr>
<tr>
<td valign="top">

`--wait-url`

</td>
<td valign="top">

Waits for a 2xx response from the specified URL before exiting

</td>
</tr>
<tr>
<td valign="top">

`--wait-url-timeout`

</td>
<td valign="top">

Seconds to wait for a 2xx response from the wait-url before exiting

`Default`: *180*

</td>
</tr>
</table>

**Related Information**  


[Deploy Locally with the Console Client](../30-development-neo/deploy-locally-with-the-console-client-937c833.md "The console client allows you to install a server runtime in a local folder and use it to deploy your application.")

