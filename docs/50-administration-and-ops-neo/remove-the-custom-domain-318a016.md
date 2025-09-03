<!-- loio318a016c3a234370a60475625b947de0 -->

# Remove the Custom Domain

If you do not want to use the custom domain any longer, you can remove it using the console client commands. As a result, your application will be accessible only on its default hana.ondemand.com domain and you won't be charged for the custom domain anymore.



## Context

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/docs/btp/sap-business-technology-platform/sap-business-technology-platform?version=Cloud) .**



## Procedure

1.  Remove the mapping of the custom domain.

    1.  First, get a list of all custom domains and their corresponding mappings.

        Run:

        ```
        neo list-custom-domain-mappings --account mysubaccount --user mymail@example.com --host hana.ondemand.com
        ```

        See [list-custom-domain-mappings](list-custom-domain-mappings-7dfeeb2.md).

        In the output of the `list-custom-domain-mappings` command, you can find the custom domain or domains that you want to remove along with the corresponding SSL host for each domain.

    2.  Then, for each custom domain that you want to remove, run:

        ```
        neo remove-custom-domain --account mysubaccount --user mymail@example.com --host hana.ondemand.com
        --custom-domain www.example.com --ssl-host mysslhostname
        ```

        > ### Note:  
        > If you removed all custom domain mappings part of this SSL host, then don't forget to remove the DNS record that points to that SSL host, previously created with the [Configure DNS](configuring-custom-domains-77cf0e6.md#loio004406e1c9a8441fb05a25f5f87d45b7) step.


2.  Remove all trusted CA certificates from the SSL host of the custom domain that you want to remove, if any.

    > ### Note:  
    > To check whether you have any CA bundles assigned to the SSL host, run the `set-ssl-host` command without any optional parameters. For example:
    > 
    > ```
    > neo set-ssl-host --account mysubaccount --user mymail@example.com --host hana.ondemand.com -name mysslhostname
    > ```
    > 
    > If there are no CA bundles assigned to the SSL host, proceed to step 3.

    1.  Remove the client certificate configuration for the specified CA bundle and unassign that bundle from the SSL host:

        ```
        neo set-ssl-host --account mysubaccount --user mymail@example.com --host hana.ondemand.com -name mysslhostname --ca-bundle <bundle_name>:none
        ```

        For more information, see [set-ssl-host](set-ssl-host-2956975.md).

    2.  Delete the bundle and all trusted CA certificates in it:

        ```
        neo remove-ca --account mysubaccount --user mymail@example.com --host hana.ondemand.com --bundle <bundle_name>
        ```

        For more information, see [remove-ca](remove-ca-55b61e4.md).


3.  Unbind the certificate.

    ```
    neo unbind-domain-certificate --account mysubaccount --user mymail@example.com --host hana.ondemand.com --ssl-host mysslhostname  
    ```

4.  Delete the certificate.

    Note that you will need the certificate name defined when configuring the custom domain.

    ```
    neo delete-domain-certificate --account mysubaccount --user mymail@example.com --host hana.ondemand.com --name myfirstcert
    
    ```

5.  Delete the SSL host.

    ```
    neo delete-ssl-host --account mysubaccount --user mymail@example.com --host hana.ondemand.com --name mysslhostname
     
    ```


**Related Information**  


[remove-custom-domain](remove-custom-domain-de15ca8.md "Removes a custom domain as an access point of an application. Use this command if you no longer want an application to be accessible on the configured custom domain.")

[unbind-domain-certificate](unbind-domain-certificate-f8d24b6.md "Unbinds a certificate from an SSL host. The certificate will not be deleted from SAP BTP storage.")

[delete-domain-certificate](delete-domain-certificate-c3076cc.md "Deletes a certificate.")

[delete-ssl-host](delete-ssl-host-f7241b7.md "Deletes an SSL host.")

[list-ssl-hosts](list-ssl-hosts-e8fc50c.md "Lists SSL hosts for a given subaccount.")

