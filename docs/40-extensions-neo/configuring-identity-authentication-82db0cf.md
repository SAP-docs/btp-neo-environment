<!-- loio82db0cff6fc542b4af38bdc0a6b5971a -->

# Configuring Identity Authentication

Use this procedure to configure the service provider \(SAP Cloud for Customer\) in the Identity Authentication tenant and to define the identity federation.



## Context

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**



## Procedure

1.  Get the service provider metadata XML file. To do so, you download the metadata XML file of your SAP Cloud for Customer system:

    1.  Log on to your SAP Cloud for Customer system as an administrator.

    2.  Select *ADMINITRATOR* \> *Common Tasks* and then choose *Configure Single Sign-On*.

    3.  On the *CONFIGURE SINGLE SIGN-ON* screen, navigate to *MY SYSTEM* \> *GENERAL* \> *Download Metadata*.

    4.  Choose the *SP Metadata* link, to download the SAP Cloud for Customer metadata XML file. Save it locally on your file system to import in later on in theIdentity Authentication.


2.  Create a custom application to use it as a SAML2.0 service provider. Access the tenant's administration console for Identity Authentication by using the console's URL.

    The URL has the <code>https://<i class="varname">&lt;tenant ID&gt;</i>.accounts.ondemand.com/admin</code> pattern.

    You can also get the URL from the Identity Authentication tenant registration e-mail.

    1.  Choose *Applications & Resources* \> *Applications* from the menu on the left.

    2.  Choose the *\+Add* button on the left hand panel, and enter the name of your SAP Cloud for Customer system.

        > ### Note:  
        > The name of the application is displayed on the login and registration pages.

    3.  Choose *Save*.


    The system creates an application and adds it to the list of applications.

3.  Configure the SAML 2.0 trust with SAP Cloud for Customer as a service provider. In the tenant's administration console for Identity Authentication, execute the following steps:

    1.  On the left-hand side, choose the newly created application, and then choose *Trust*.

    2.  Choose *SAML 2.0 Configuration*.

    3.  Upload the metadata XML file of your SAP Cloud for Customer system that you have downloaded in **Step 1**.

        On service provider metadata upload, the fields are populated with the parsed data from the XML file.

    4.  Save the configuration settings.


4.  Configure the identity federation on Identity Authentication. To do so, proceed as follows:

    1.  In the tenant's administration console for Identity Authentication, choose your SAP Cloud for Customer application, and navigate to *Trust* \> *Name ID Attribute*, and then select *Login Name*.

        This is the profile attribute that Identity Authentication sends to the application as a name ID. The application then uses this attribute to identify the user. You should select the attribute expected by your SAP Cloud for Customer system as a valid user.

        > ### Note:  
        > E-mail is not supported by the SAP Cloud for Customer system.

    2.  Save your selection.



