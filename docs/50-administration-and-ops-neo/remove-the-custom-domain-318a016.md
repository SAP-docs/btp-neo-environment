<!-- loio318a016c3a234370a60475625b947de0 -->

# Remove the Custom Domain

If you do not want to use the custom domain any longer, you can remove it using the console client commands. As a result, your application will be accessible only on its default hana.ondemand.com domain.



## Context

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://launchpad.support.sap.com/#/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**



## Procedure

1.  In the console client command line, execute `neo remove-custom-domain`.

    Note that you will need the SSL host name defined when configuring the custom domain. You can view it by executing `list-ssl-hosts`.

    ```
    neo remove-custom-domain --account mysubaccount --user mymail@example.com --host hana.ondemand.com
    --custom-domain www.example.com --ssl-host mysslhostname
    
    ```

2.  Unbind the certificate.

    ```
    neo unbind-domain-certificate --account mysubaccount --user mymail@example.com --host hana.ondemand.com --ssl-host mysslhostname  
    ```

3.  Delete the certificate.

    Note that you will need the certificate name defined when configuring the custom domain.

    ```
    neo delete-domain-certificate --account mysubaccount --user mymail@example.com --host hana.ondemand.com --name myfirstcert
    
    ```

4.  Delete the SSL host.

    ```
    neo delete-ssl-host --account mysubaccount --user mymail@example.com --host hana.ondemand.com --name mysslhostname
     
    ```


**Related Information**  


[remove-custom-domain](remove-custom-domain-de15ca8.md "Removes a custom domain as an access point of an application. Use this command if you no longer want an application to be accessible on the configured custom domain.")

[unbind-domain-certificate](unbind-domain-certificate-f8d24b6.md "Unbinds a certificate from an SSL host. The certificate will not be deleted from SAP BTP storage.")

[delete-domain-certificate](delete-domain-certificate-c3076cc.md "Deletes a certificate.")

[delete-ssl-host](delete-ssl-host-f7241b7.md "Deletes an SSL host.")

[list-ssl-hosts](list-ssl-hosts-e8fc50c.md "Lists SSL hosts for a given subaccount.")

