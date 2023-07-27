<!-- loiof907bd460d46436f9ead17ea954fa9c6 -->

# Configure and Check the SSO Configuration

You can check that the SSO is properly configured by launching SAP Web IDE.



## Context

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://launchpad.support.sap.com/#/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**



## Procedure

1.  Configure the SSO. See [Configuring Single Sign-On Between SAP S/4HANA Cloud and SAP BTP, Neo Environment](configuring-single-sign-on-between-sap-s-4hana-cloud-and-sap-btp-neo-environment-a41018f.md).

2.  Check if you have set up the SSO correctly.

    1.  In the SAP BTP cockpit, go to *Services* and search for `Web IDE`.

    2.  Choose the *SAP Web IDE Full-Stack* tile.

    3.  Choose the *Configure Service* link.

    4.  Set up the *DiDeveloper* role. See [Assign Users Permission for SAP Web IDE](https://help.sap.com/viewer/825270ffffe74d9f988a0f0066ad59f0/CF/en-US/102a024b1e344c54a0df7d835163b039.html).

    5.  Open the link in the *Application URL* field to launch the SAP Web IDE.





<a name="loiof907bd460d46436f9ead17ea954fa9c6__result_xb2_11y_kbb"/>

## Results

You will see the login screen of the Identity Authentication. You need to use another browser, or an incognito session of user.

