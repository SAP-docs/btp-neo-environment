<!-- loio9e3fc153918545e59c3ae609f7d6ea35 -->

# Create an Extension Site

You create an extension site to integrate the extension application in SAP SuccessFactors.



## Prerequisites

-   You have administrator's permissions for SAP SuccessFactors. See [Defining the People Pool for Managing Extensions](defining-the-people-pool-for-managing-extensions-ccd49f2.md).

-   For Java extension applications, make sure that the application's client-side is developed as a SAPUI5 component.

    HTML5 extension applications are supported by default.




## Context

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**



## Procedure

1.  Depending on the SAP SuccessFactors release, go to:

    1.  In SAP SuccessFactors *Admin Center*, open the *Extension Center*.

    2.  On the *Extensions on SAP BTP* tab page, navigate to the *Neo Environment* screen area, and choose the *link* in the *SAP Cloud Portal URL* column for your integrated system.


2.  In the extension site creation wizard:

    1.  Enter a name.

    2.  In the *Template Source* dropdown list, choose *SAP SuccessFactors Extensions*.

    3.  Select one of the templates based on your preferred layout.

    4.  Choose *Create*.


    Your new extension site opens in edit mode.

3.  4. Add your extension application to the extension site. This extension application has to be an HTML5 application.

    1.  From the *Site Designer* side panel, open *Content Management*, and choose *Apps*.

    2.  Choose *\+* at the bottom left side, and choose *New*.

    3.  From the *App Resource* field, search for your extension application, and choose *OK*.


    The application is added to the *Apps* list.

4.  5. Add the extension application to the site menu.

    1.  In the *Site Designer* side navigation panel, choose *Menu Editor*.

    2.  Choose *\+* and select *Add Item*.

    3.  In the *Add Menu Item* dialog, select *App* as your *Item Type*.

    4.  Search for your application and add it as a full-page application in your site.

    5.  Choose *Save*.


    If you preview your extension site now, you'll see that the application is part of the site menu and is displayed as a full page application in your site.

5.  Publish the extension site to make it available to all users.

    1.  Choose *Extension Directory*.

    2.  Hover over the card of your site, and click the arrow at the bottom right corner.

    3.  Choose *Publish*.


6.  Access the extension site at runtime.

    1.  Hover over the published card of your site.

    2.  Choose the runtime URL that is displayed on the card.





## Results

You have created an extension site for your extension application, and your extension application appears in it.

> ### Note:  
> The SAP Cloud Portal service documentation uses the generic term *Site* and not *Extension Site*. Both are referring to the same entity. For more information about SAP Cloud Portal service, see [SAP Cloud Portal Service for the Neo Environment](https://help.sap.com/viewer/8422cb487c2146999a2a7dab9cc85cf7/Cloud/en-US)

