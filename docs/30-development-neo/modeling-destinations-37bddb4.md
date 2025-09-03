<!-- loio37bddb411fa9496d9db9699371c99138 -->

# Modeling Destinations

You can connect your applications to another source by describing the source connection properties in a destination. Later on, you can access that destination from your application.

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/docs/btp/sap-business-technology-platform/sap-business-technology-platform?version=Cloud) .**

Depending on whether the destination source is located within the SAP BTP or not, the destinations are classified as internal or external. You can also provide a Solution for consumption to another SAP BTP subaccount and define a destination as deployable to all subscriber subaccounts.

The supported destination levels you can model within a Solution are:

**Supported Levels of Destinations**


<table>
<tr>
<th valign="top">

Level

</th>
<th valign="top">

Description

</th>
<th valign="top">

Support for Java Applications

</th>
<th valign="top">

Support for Tomcat Applications

</th>
<th valign="top">

Support for HTML5 Applications

</th>
</tr>
<tr>
<td valign="top">

Subaccount-Level Destination

</td>
<td valign="top">

After deployment, it is available for all applications within your subaccount

</td>
<td valign="top">

Yes

</td>
<td valign="top">

Yes

</td>
<td valign="top">

Yes

</td>
</tr>
<tr>
<td valign="top">

Application-Level Destination

</td>
<td valign="top">

After deployment, it is available only for designated applications

</td>
<td valign="top">

Yes

</td>
<td valign="top">

Yes

</td>
<td valign="top">

No

</td>
</tr>
</table>

**Related Information**  


[Modeling Subaccount-Level Destinations](modeling-subaccount-level-destinations-8aacd18.md "Subaccount-level destinations are not linked to a particular application, but instead can be used by all applications. For example, the subaccount-level destination can be used by an HTML5 application to connect to a source Java application.")

[Modeling Application-Level Destinations](modeling-application-level-destinations-1806ffa.md)

