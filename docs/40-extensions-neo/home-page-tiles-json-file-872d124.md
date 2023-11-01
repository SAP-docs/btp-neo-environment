<!-- loio872d124e75094aa5a782fb5703d88eb3 -->

# Home Page Tiles JSON File

The Home Page tiles JSON descriptor, for example, `tiles.json`, contains the definition of the Home Page tiles for the extension application.



> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**

> ### Note:  
> The support of the Home Page tiles in SAP SuccessFactors has been discontinued. See [Home Page Tiles](https://help.sap.com/docs/SAP_SUCCESSFACTORS_PLATFORM/59f821da545a4bdb94f1eb8fa22e4b36/00c8674252d1461691bec004be68f425.html).
> 
> We recommend that you use the latest home page. See [Migrating to the Latest Home Page](https://help.sap.com/docs/SAP_SUCCESSFACTORS_PLATFORM/59f821da545a4bdb94f1eb8fa22e4b36/8d2921382f9544dc8d14cb249ec6a289.html).



## Properties




<table>
<tr>
<th valign="top" colspan="2">

Home Page Tile Properties

</th>
</tr>
<tr>
<td valign="top">

`name` 

</td>
<td valign="top">

The name of the tile used to identify it. This name is used in the Home Page administration tools and it is not visible to end-users, but only to HR administrators.

</td>
</tr>
<tr>
<td valign="top">

`metadata` 

</td>
<td valign="top">

Defines the localized tile title and description.

</td>
</tr>
<tr>
<td valign="top">

-   `title`




</td>
<td valign="top">

A metadata property.

This is the title of the custom tile as it appears to end-users on the Home Page.

The value *en\_US* is mandatory. Otherwise, the value for other locales is not provided, and end-users will see a blank tile.

</td>
</tr>
<tr>
<td valign="top">

-   `subTitle`




</td>
<td valign="top">

A metadata property.

This is a subtitle that appears on custom tiles under the tile title. Subtitles are optional. If you do not want to use a subtitle, you can leave the field blank.

</td>
</tr>
<tr>
<td valign="top">

-   `locale`




</td>
<td valign="top">

A metadata property.

Using this propety, you can localize the title, and the subtitle.

</td>
</tr>
<tr>
<td valign="top">

`type` 

</td>
<td valign="top">

Determines how the tile appears to end-users. Currently, only static type is supported.

The value *static* is mandatory.

</td>
</tr>
<tr>
<td valign="top">

`configuration` 

</td>
<td valign="top">

Contains the *icon* property.

</td>
</tr>
<tr>
<td valign="top">

-   `icon`




</td>
<td valign="top">

A configuration property.

Contains the ID of the icon that you want to use for the custom tile. You can take its ID from SAP SuccessFactors system. Go to *Admin Center* \> *Manage Home Page* \> *Add Custom Tile* and then follow the wizard until you choose the icon in the *Tile* tab. Then, take its ID and place it in the `tiles.json`. For example, "sap-icon://add-product".

</td>
</tr>
<tr>
<td valign="top">

`navigation` 

</td>
<td valign="top">

The tile navigation determines how the tile responds when a user clicks or selects it. You can choose from the following options:

-   type: html-popover

    configuration: Contains two properties, "contentSize" and "content".

    "contentSize" defines the width of the popover window and has one of the following values: "responsive", "small", "medium", and "large".

    "content" defines the HTML content of the popover window and has a String value. You cannot localize the content of this type \(unlike the SAP SuccessFactors custom popover tiles\).

-   type: iframe-popover

    configuration: Contains two properties, "contentSize" and "URL".

    "contentSize" defines the size of the popover window and has one of the following values: "responsive", "small", "medium", and "large".

    "URL" defines the relative to the application root of the iframe source and has a String value.

-   type: url

    configuration: Contains the "url" property.

    "url" defines the URL link which will be opened and has a String value. For example, "index.html".

    The "url" is relative to the application root.

-   type: no\_target




</td>
</tr>
</table>

For more details about the Home Page tiles properties, see [Custom Tile Configuration Settings](https://help.sap.com/viewer/59f821da545a4bdb94f1eb8fa22e4b36/LATEST/en-US/ba363fa85356409d9e90847857064e29.html).



> ### Note:  
> The `tiles.json` descriptor file must use UTF-8 encoding and its size must not exceed 100 KB.



## Example

Example of a Home Page tile JSON descriptor.

```json
[{
	"tileVersion": "NEW_HOME_PAGE",
	"tiles": [{
			"name": "New Test Application",
			"section": "news",
			"metadata": [{
				"title": "My new home page tile",
				"subTitle": "This is new home page tile",
				"locale": "en_US"
			}],
			"type": "static",
			"configuration": {
				"icon": "sap-icon://add-product"
			},
			"navigation": {
				"type": "url",
				"configuration": {
					"openInNewWindow": false,
					"url": "index.html"
				}
			}
		}]	
}]
```

