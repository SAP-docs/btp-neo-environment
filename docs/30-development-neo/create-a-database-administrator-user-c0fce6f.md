<!-- loioc0fce6f0322246daaf1e29a25414f15e -->

# Create a Database Administrator User

As an subaccount administrator, you can use the database user feature provided in the cockpit to create your own database user for your SAP HANA database.



<a name="loioc0fce6f0322246daaf1e29a25414f15e__d446e18"/>

## Context

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**

SAP BTP creates four users that it requires to manage the database: SYSTEM, BKPMON, CERTADM, and PSADBA. These users are reserved for use by SAP BTP.

> ### Caution:  
> Do not delete or deactivate these users or change their passwords.



<a name="loioc0fce6f0322246daaf1e29a25414f15e__d446e35"/>

## Procedure

1.  In the SAP BTP cockpit, navigate to a subaccount. For more information, see [Navigate in the Cockpit](../50-administration-and-ops-neo/navigate-in-the-cockpit-fdeff7e.md).

2.  Choose *SAP HANA / SAP ASE* \> *Databases and Schemas* in the navigation area.

    You see all databases that are available in the subaccount, along with their details, including the database type, version, memory size, state, and the number of associated databases.

3.  Select the relevant SAP HANA XS database.

4.  In the *Development Tools* section, click *Database User*.

    A message confirms that you do not yet have a database user.

5.  Choose *Create User*.

    Your user and initial password are displayed. Change the initial password when you first log on to an SAP HANA system, for example the SAP HANA Web-based Development Workbench.

    > ### Note:  
    > -   Your database user is assigned a set of permissions for administering the SAP HANA database system, which includes *HCP\_PUBLIC*, and *HCP\_SYSTEM*. The *HCP\_SYSTEM* role contains, for example, privileges that allow you to create database users and grant additional roles to your own and other database users.
    > 
    > -   You also require specific roles to use the SAP HANA Web-based tools. For security reasons, only the role that provides access to the SAP HANA Web-based Development Workbench is assigned as default.

6.  To log on to the SAP HANA Web-based Development Workbench and change your initial password now \(recommended\), copy your initial password and then close the dialog box.

    You do not have to change your initial password immediately. You can open the dialog box again later to display both your database user and initial password. Since this poses a potential security risk, however, you are strongly advised to change your password as soon as possible.

7.  In the *Development Tools* section, click *SAP HANA Web-based Development Workbench*.

8.  On the SAP HANA logon screen, enter your database user and initial password.

9.  Change your password when prompted.

    > ### Caution:  
    > You are responsible for choosing a strong password and keeping it secure. If your user is blocked or if you've forgotten the password of your user, another database administration user with `USER_ADMIN` privileges can unlock your user.




## Next Steps

-   > ### Tip:  
    > There may be some roles that you cannot assign to your own database user. In this case, we recommend that you create a second database user \(for example, *ROLE\_GRANTOR*\) and assign it the *HCP\_SYSTEM* role. Then log onto the SAP HANA system with that user and grant your database user the roles you require.

-   In the SAP HANA system, you can now create database users for the members of your subaccount and assign them the required developer roles.

-   To be able to use other HANA tools like HANA Cockpit or HANA XS Administration tool, you must assign yourself access to these before you can start using them. See [Assign Roles Required for the SAP HANA XS Administration Tool](assign-roles-required-for-the-sap-hana-xs-administration-tool-c006db5.md#loioc006db57b3654c5fbcd9f6136b556c3d)


**Related Information**  


[Roles Required for Web-based Tools](assign-roles-required-for-the-sap-hana-xs-administration-tool-c006db5.md#loiod7c4ca5dac4f4dbbb47901eebe9ea0d1 "To use the SAP HANA Web-based tools, you require specific roles.")

[Managing SAP HANA Users](http://help.sap.com/saphelp_hanaplatform/helpdata/en/ed/7af17e5ae14de694d9bee5f35098f4/content.htm?frameset=/en/c0/555f0bbb5710148faabb0a6e35c457/frameset.htm)

[Setting Up Roles and Authorizations](http://help.sap.com/saphelp_hanaplatform/helpdata/en/8f/f545995b594245b2508a380457fbc8/content.htm?frameset=/en/9a/b0b327addd411ab6eadeba205a889e/frameset.htm)

[Creating an SAP HANA Tenant Database and an SAP HANA XS Classic Application](https://help.sap.com/viewer/d4790b2de2f4429db6f3dff54e4d7b3a/Cloud/en-US/a4b1a6abc13f45d58c9a156b81487d8a.html "Create and bind an SAP HANA tenant database to an SAP HANA XS classic application using the SAP BTP cockpit, the SAP HANA cockpit and the SAP HANA Web-Based Development Workbench.") :arrow_upper_right:

