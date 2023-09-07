<!-- loio76134b64711e1014839a8273b0e91070 -->

# EclipseLink Weaving

EclipseLink provides weaving as a means of enhancing JPA entities and classes for performance optimization. At present, SAP BTP supports static weaving only. Static weaving occurs at compile time and is available in both the Java Web and Java EE 6 Web Profile environments.

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**



Dynamic weaving is currently not supported on SAP BTP.



<a name="loio76134b64711e1014839a8273b0e91070__section_D5D10883B6EE4EC5BC79A337F474844E"/>

## Prerequisites

-   For static weaving to work, the entity classes must be listed in the `persistence.xml` file.

-   EclipseLink Library:

    To use the EclipseLink weaving options in your web applications, add the EclipseLink library to the classpath:

    -   SDK for Java Web

        The EclipseLink library has already been added to the `WebContent/WEB-INF/lib` folder, since it is required for the JPA persistence scenario.

    -   SDK for Java EE 6 Web Profile

        The EclipseLink library is already part of the SDK for Java EE 6 Web Profile, allowing you to run JPA scenarios without any additional steps. To use the weaving options, however, you add the EclipseLink library to the classpath, as described below.





<a name="loio76134b64711e1014839a8273b0e91070__section_FA28F38145334C41B7E94A0B5ED9DDE5"/>

## SDK for Java EE 6 Web Profile: Adding the EclipseLink Library to the Classpath

1.  In the Eclipse IDE in the *Project Explorer* view, select the web application and from the context menu choose *Properties*.
2.  In the tree, select *JPA*.
3.  In the *Platform* section, select the correct EclipseLink version, which should match the version available in the SDK.
4.  In the *JPA implementation* section, select the type `User Library`.
5.  To the right of the user library list box, choose *Download library*.
6.  Select the correct version of the EclipseLink library \(currently `EclipseLink 2.5.2`\) and choose *Next*.
7.  Accept the EclipseLink license and choose *Finish*.
8.  The new user library now appears; make sure it is selected.
9.  Unselect *Include libraries with this application* and choose *OK*.



<a name="loio76134b64711e1014839a8273b0e91070__section_2F0255F47B51405B920E619BBA8C918E"/>

## Enabling Static Weaving in Eclipse

1.  In the Eclipse IDE in the *Project Explorer* view, select the web application and from the context menu choose *Properties*.
2.  In the tree, select *JPA* \> *EclipseLink*.
3.  In the *Static weaving* section, select *Weave classes on build*.
4.  Leave the default values for the source classes, target classes, and persistence XML root; however you may need to adapt them if you have a non-standard web application project layout. Choose *OK*.

    > ### Note:  
    > If you change the target class settings, make sure you deploy these classes.


Your web application project is rebuilt so that the JPA entity class files contain weaving information. This also occurs on each \(incremental\) project build. The woven entity classes will are whenever you publish the web application to the cloud.



<a name="loio76134b64711e1014839a8273b0e91070__section_4E306C3AF85A4B979CD6820B2DF49C0B"/>

## More Information

For information about using an ant task or the command line to perform static weaving, see the [EclipseLink User Guide](http://wiki.eclipse.org/EclipseLink/UserGuide/JPA/Advanced_JPA_Development/Performance/Weaving/Static_Weaving).

