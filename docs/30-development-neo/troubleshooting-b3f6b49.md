<!-- loiob3f6b49991e94e3ab4a4d8d17f9d110d -->

# Troubleshooting

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://launchpad.support.sap.com/#/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**

While transporting SAP BTP applications using the CTS+ tool, or while deploying solutions using the cockpit, you might encounter one of the following issues. This section provides troubleshooting information about correcting them.

**Troubleshooting**


<table>
<tr>
<th valign="top">

Message Text



</th>
<th valign="top">

Troubleshooting



</th>
</tr>
<tr>
<td valign="top">

***Technical error \[Invalid MTA archive \[<mtar archive\>\]. MTA deployment descriptor \(META-INF/mtad.yaml\) could not be parsed. Check the troubleshooting guide for guidelines on how to resolve descriptor errors. Technical details: <…\>***



</td>
<td valign="top">

This error could occur if the MTA archive is not consistent. There are several different reasons for this:

-   The MTA deployment descriptor `META-IND/mtad.yaml` cannot be parsed, because it is syntactically incorrect according to the YAML specification. For more information, see the publicly available YAML specification.

    Make sure that the descriptor is compliant with the specification. Validate the descriptor syntax, for example, by using an online YAML parser.

    > ### Note:  
    > Ensure that you do not submit any confidential information to the online YAML parser.

-   The MTA deployment descriptor might contain data that is not compatible with SAP BTP. Make sure the MTA deployment descriptor complies with the specification at [Multitarget Applications for the Neo Environment](multitarget-applications-for-the-neo-environment-e1bb7eb.md).

-   The archive might not be suitable for deployment to the SAP BTP. This might happen if, for example, you attempt to deploy an archive built for XSA to the SAP BTP. The technical details might contain information similar to the following:

    ***"Unsupported module type "<module type\>" for platform type "HCP-CLASSIC""***




</td>
</tr>
<tr>
<td valign="top">

***Technical error \[Invalid MTA archive \[<MTA name\>\]: Missing MTA manifest entry for module \[<module name\>\]\]***



</td>
<td valign="top">

The archive is inconsistent, for example, when a module referenced in the `META-INF/mtad.yaml` is not present in the MTA archive or is not referenced correctly. Make sure that the archive is compliant with the MTA specification available at [The Multitarget Application Model v.2](http://go.sap.com/documents/2016/06/e2f618e4-757c-0010-82c7-eda71af511fa.html) and the [The Multitarget Application Model v.3](https://www.sap.com/documents/2021/09/66d96898-fa7d-0010-bca6-c68f7e60039b.html).



</td>
</tr>
<tr>
<td valign="top">

***Technical error \[MTA extension descriptor\(s\) could not be parsed. Check the troubleshooting guide for guidelines on how to resolve descriptor errors. Technical details: <…\>***



</td>
<td valign="top">

This error could occur if one or more extension descriptors are not consistent. There are several different reasons for this:

-   One or more extension descriptors might not be syntactically compliant with the YAML specification. Validate the descriptor syntax, for example, by using an online YAML parser.

    > ### Note:  
    > Ensure that you do not submit any confidential information to the online YAML parser.

-   One or more extension descriptors might contain data that is not compatible with SAP BTP. Make sure all extension descriptors comply with the specification at [Multitarget Applications for the Neo Environment](multitarget-applications-for-the-neo-environment-e1bb7eb.md).



</td>
</tr>
<tr>
<td valign="top">

***Technical error \[MTA deployment descriptor \(META-INF/mtad.yaml\) from archive \[<mtar archive\>\] and some of extension descriptors \[<extension descriptor\>\] could not be processed . Check the troubleshooting guide for guidelines on how to resolve descriptor errors. Technical details: <…\>***



</td>
<td valign="top">

This error could occur if the MTA archive, or one or more extension descriptors are not consistent. There are several different reasons for this:

-   The MTA deployment descriptor or an extension descriptor might contain data that is not compatible with the SAP BTP. Make sure the MTA deployment descriptor and all extension descriptors comply with the specification at [Multitarget Applications for the Neo Environment](multitarget-applications-for-the-neo-environment-e1bb7eb.md).
-   The archive may not be suitable for deployment to SAP BTP. This might happen if, for example, you attempt to deploy an archive built for XSA to the SAP BTP. The technical details might contain information similar to the following:

    ***"Unsupported module type "<module type\>" for platform type "HCP-CLASSIC""***




</td>
</tr>
<tr>
<td valign="top">

***Process \[<process-name\>\] has failed with \[Your user is not authorized to perform the requested operation. Forbidden \(403\)\]. Contact SAP Support.***



</td>
<td valign="top" rowspan="2">

Ensure that you have required the necessary permissions or roles that are required to list or manage Multitarget Applications. For more information, see [Operating Solutions](operating-solutions-2abf7d4.md).



</td>
</tr>
<tr>
<td valign="top">

***Process \[CTS\_DEPLOY\] has failed with \[undefined \(403\)\]. Contact SAP Support.***



</td>
</tr>
</table>

