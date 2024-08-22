<!-- loio5b7049131e51491ead2d4589dd2be1dc -->

# Deleting a Certificate from a CA Bundle

Use this solution to remove a certificate from a CA bundle and replace it with a new one.



## Context

Issue: You are trying to delete a certificate from a CA bundle by running `remove-ca` with either the `--expired` parameter or the `--serial-number` parameter, but there is an error message and the operation does not complete successfully.

Solution: There is an alternative way to delete a certificate from a CA bundle. Here is how you can do it:



## Procedure

1.  Download the CA bundle content by running the `list-cas` command with the `-f` parameter to store this content locally.

    Example:

    ```
    neo list-cas -h hana.ondemand.com -u mymail@example.com -p ******** -a mysubaccount --bundle test -f testBundle.txt
    ```

    In this case, the "testBundle.txt" file contains all certificates, which are part of the "test" bundle.

2.  Update the content of the file you have just downloaded.

    Example:

    Open the "testBundle.txt" file and remove the certificate or certificates you no longer need. Then, save the "testBundle.txt" file.

3.  Add the file with the updated content to a new bundle by executing the `add-ca` command:

    Example:

    ```
    neo add-ca -h hana.ondemand.com -u mymail@example.com -p ******** -a mysubaccount --bundle test2 -l testBundle.txt
    ```

    This means that all trusted certificates from the "testBundle.txt" file are now added to the new "test2" bundle.

4.  Replace the old bundle with the new bundle by running the `set-ssl-host` command:

    Example:

    ```
    neo set-ssl-host -h hana.ondemand.com -u mymail@example.com -p ******** -a mysubaccount -n sslhost1 --ca-bundle test2:request
    ```

    The new "test2" bundle replaces the old "test" bundle. Therefore, the old "test" bundle is no longer needed.

5.  \(Optional\) You can remove the old bundle by running the `remove-ca` command:

    Example:

    ```
    neo remove-ca -h hana.ondemand.com -u mymail@example.com -p ******** -a mysubaccount --bundle test
    ```

    The old "test" bundle is deleted, because it is replaced by the new "test2" bundle in step 4.


**Related Information**  


[Experiencing CA Bundle Issues](experiencing-ca-bundle-issues-4c26325.md "Use the following troubleshooting steps for resolving issues with CA bundles.")

[Troubleshooting Guide for Custom Domains in the Neo Environment](troubleshooting-guide-for-custom-domains-in-the-neo-environment-216e0ed.md "Use this troubleshooting guide to quickly identify and resolve issues with custom domains in the SAP BTP, Neo environment.")

