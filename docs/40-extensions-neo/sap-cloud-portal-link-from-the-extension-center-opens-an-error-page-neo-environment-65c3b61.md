<!-- loio65c3b61d48e148a7ae246bd6257f3588 -->

# SAP Cloud Portal Link From the Extension Center Opens an Error Page \(Neo Environment\)

SAP Cloud Portal link from the Extension Center opens an error page.



<a name="loio65c3b61d48e148a7ae246bd6257f3588__section_ujc_lp2_2cc"/>

## Issue/Symptom

I want to open the SAP Cloud Portal link from the Extension Center for my registered SAP SuccessFactors system. When I choose the SAP Cloud Portal link, it opens a page that contains the following: Site not found.



<a name="loio65c3b61d48e148a7ae246bd6257f3588__section_j1l_np2_2cc"/>

## Solution

**Have you defined IP restrictions for your SAP SuccessFactors company?**

-   **Yes, I have defined IP restrictions for my SAP SuccessFactors company**
    -   **Issue/Symptom**

        I want to open the SAP Cloud Portal link from the Extension Center for my registered SAP SuccessFactors system. When I choose the SAP Cloud Portal link, it opens a page that contains the following: Site not found.

    -   **Reason**

        You have defined IP restrictions for your SAP SuccessFactors company.

        These restrictions prevent the Portal Service from calling your SAP SuccessFactors system from SAP BTP. You will need to allow the IP ranges of the SAP BTP landscape of your subaccount in your SAP SuccessFactors company.

        These are the places in SAP SuccessFactors where you can allow IP ranges:

        -   Admin Center \> IP Restriction Management

        -   Admin Center \> Password & Login Policy Settings \> Set API login exceptions... section

        -   Provisioning \> your SAP SuccessFactors company \> Company Settings \> Restrict access to IP range


    -   **Solution**

        You need to allow the IP ranges of the SAP BTP, Neo environment where your subaccount resides so that the SAP Cloud Portal service can call your SAP SuccessFactors company.

        For more information about the IP addresses in CIDR notation, see[Regions and Hosts Available for the Neo Environment](https://help.sap.com/docs/BTP/ea72206b834e4ace9cd834feed6c0e09/d722f7cea9ec408b85db4c3dcba07b52.html).

        In CIDR notation, IP addresses are written as a prefix, and a suffix is attached to indicate how many bits are in the entire address. The suffix is set apart from the prefix with a slash mark. For example, in the CIDR notation 192.0.1.0/24, the prefix is 192.0.1.0

        You need to calculate the first and the last IP address that is included in the IP range in CIDR notation. These values set the IP range when allowing the IP addresses. You can do that with an online IP calculator.

        For example, 157.133.70.0/24 translates to the IP range 157.133.70.0 - 157.133.70.255


-   **I Haven't Defined IP Restrictions for My SAP SuccessFactors Company**
    -   **Issue/Symptom**

        I want to open the SAP Cloud Portal link from the Extension Center for my registered SAP SuccessFactors system. When I choose the SAP Cloud Portal link, it opens a page that contains the following: Site not found.

    -   **Reason**

        Your user is not part of the Extensions Administrators group.

    -   **Solution**

        1.  In the **Admin Center**, search for **Manage Permission Groups**.
        2.  Search for Extensions Administrators and choose **Extensions Adminsitrators** from the list.
        3.  In the **People Pool** dropdown menu, select a category, for example **Username.**
        4.  In the **Search** field, enter your username. Select the checkbox of your username and choose **Done**.
        5.  Choose **Update**in the **Active Group Membership** box to see how many users match the criteria. Click the number to see the detail list.

        If you want to add another condition for defining the people pool, choose **Add another category** and choose a category and item. If you use two or more categories, this functions as an **AND** operation, that is, only users are selected who meet all selection criteria.

        Complex group definitions may require you to use multiple people pools. If you use two or more people pools, these people pools functions as an **OR** operation, that is, all users are selected who fulfill the selection criteria of at least one pool.

        See [Creating Dynamic Permission Groups](https://help.sap.com/docs/SAP_SUCCESSFACTORS_PLATFORM/b569eee64d3f4159b2b5272ba7d6b127/6adf50f40a86406a917a54ce7fd2131b.html).



