<!-- loioc7c36e6d97764822bd86be07bfe84090 -->

# close-db-tunnel

This command closes one or all database tunnel sessions that have been opened in a background process using the `open-db-tunnel --background` command.



> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/docs/btp/sap-business-technology-platform/sap-business-technology-platform?version=Cloud) .**



```
neo close-db-tunnel --session-id <session_ID>
```

A tunnel opened in a background process is automatically closed when the last session using the tunnel is closed. The background process terminates after the last tunnel has been closed.



## Parameters


<table>
<tr>
<th valign="top" colspan="2">

Required

</th>
</tr>
<tr>
<td valign="top">

`--all`

</td>
<td valign="top">

Closes all tunnel sessions that have been opened in the background

</td>
</tr>
<tr>
<td valign="top">

`--session-id`

</td>
<td valign="top">

Tunnel session to be closed. Cannot be used together with the parameter `--all`.

</td>
</tr>
</table>



## Example

```
neo close-db-tunnel --session-id f4b00f06-df0a-4018-b725-392a93b49bd4
```

**Related Information**  


[open-db-tunnel](open-db-tunnel-9e3f90f.md "This command opens a database tunnel to the database system associated with the specified schema or database.")

[Automating the Use of Database Tunnels](https://help.sap.com/viewer/3fa880aa54b74110ae99ad01503fcd60/Cloud/en-US/49626c9474584bbfa4a936975b851326.html "For continuous delivery and automated tests, the open-db-tunnel command supports a background mode, which allows a database tunnel to be opened by automated scripts or as part of a Maven build.") :arrow_upper_right:

