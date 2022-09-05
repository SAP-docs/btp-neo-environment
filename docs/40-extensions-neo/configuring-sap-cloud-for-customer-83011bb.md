<!-- loio83011bba2d0a4173872cb1a9549b8215 -->

# Configuring SAP Cloud for Customer

Configure the Single Sign-On \(SSO\) to Identity Authentication in the SAP Cloud for Customer system.



## Context

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**



## Procedure

1.  Get the identity provider metadata XML file. To do so:

    1.  Use the following URL to access the metadata for the Identity Authentication tenant:

        <code>https://<i class="varname">&lt;tenant ID&gt;</i>.accounts.ondemand.com/saml2/metadata</code>.

    2.  Save the content of the page locally on your file system as an XML file.


2.  Log on to your SAP Cloud for Customer system as an administrator.

3.  Choose *ADMINISTRATOR* \> *Common Tasks* and then choose *Configure Single Sign-On*.

4.  On the *CONFIGURE SINGLE SIGN-ON* screen, choose the *IDENTITY PROVIDER* tab.

5.  Choose *New Identity Provider*.

6.  Browse and open the metadata XML file that you have downloaded in **Step 1**. By importing the metadata, the system automatically uploads the required signature certificate and encryption certificate.

    The new identity provider is activated and displayed in the *Trusted Identity Provider* list.

7.  Once you have configured your identity provider, activate SSO in your SAP Cloud for Customer system. To do so, choose *Activate Single Sign-On*, and then choose *OK*.

8.  To save your settings, choose *Save* in the upper left-hand corner.


