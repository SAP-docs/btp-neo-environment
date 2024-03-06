<!-- loio11da7c3a91f24206a68f70b5d6cb3d88 -->

# Update an Expired Certificate

When the certificate for the custom domain expires or it's about to expire, you can either upload and bind a new certificate based on a new CSR, or upload and bind a new certificate based on an already existing CSR.



## Context

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**

It's possible to update an expired certificate by uploading a signed certificate that isn't based on a CSR generated via the `generate-csr` command. However, this procedure requires you to upload a private key from a remote location, which poses a security risk. Also, there's no way to download the uploaded private key. For more information, see [upload-domain-certificate](upload-domain-certificate-bb54abf.md).

Therefore, SAP recommends that you use only certificates that are based on CSRs previously generated via the `generate-csr` command.

<a name="loio7b3d0eda8f4149ad83f46d3472687ee8"/>

<!-- loio7b3d0eda8f4149ad83f46d3472687ee8 -->

## Using a New CSR



## Context

Upload and bind a new certificate to the SSL host to replace the expired certificate by generating a new CSR. If you had configured the certificate using the console client commands, follow the steps:



<a name="loio7b3d0eda8f4149ad83f46d3472687ee8__steps_v5r_21h_j2b"/>

## Procedure

1.  Generate a new CSR by executing the `neo generate-csr` command with the appropriate parameters:

    ```
    neo generate-csr --account mysubaccount --user mymail@example.com --host hana.ondemand.com
    --name mynewcert --certificate-distinguished-name "C=BG,O=MyCompany,CN=example.com"
    ```

    For more information, see [Upload a Certificate](configuring-custom-domains-77cf0e6.md#loio55120d899d314e23ab8e33b4b388cea6).

2.  In the command line output, you get the generated new CSR. Copy and send the text to your trusted CA to sign your certificate.

3.  When you receive a signed SSL certificate from the CA, upload it by executing:

    ```
    neo upload-domain-certificate --account mysubaccount --user mymail@example.com --host hana.ondemand.com --name mynewcert --location ./certificate.pub
    ```

4.  Execute `neo set-ssl-host` with the `--certificate` parameter.

    ```
    neo set-ssl-host --account mysubaccount --user mymail@example.com --host hana.ondemand.com --name mysslhostname --certificate mynewcert
    ```

    The `set-ssl-host` command allows you to unbind the expired certificate and bind the new one to the SSL host in one step. For more information, see [set-ssl-host](set-ssl-host-2956975.md).

5.  To verify that you have configured correctly the new certificate, execute `neo list-domain-certificates`.

6.  After you have made sure that the new certificate is configured correctly, delete the old certificate.

    Run the `delete-domain-certificate` command:

    ```
    neo delete-domain-certificate --account mysubaccount --user mymail@example.com --host hana.ondemand.com --name myoldtcert
    ```

    See [delete-domain-certificate](delete-domain-certificate-c3076cc.md).


<a name="loiof16731619a134670ac99915b2049d8d5"/>

<!-- loiof16731619a134670ac99915b2049d8d5 -->

## Using the CSR of the Bound Certificate



## Context

Some certificate authorities \(CA\) offer to sign an SSL certificate based on the CSR of the already bound certificate. If you choose this option, you don't need to generate a new CSR.

> ### Note:  
> When you update your old certificate this way, you overwrite it with the new certificate.



## Procedure

1.  Run the `display-csr` command to get the CSR of the certificate currently bound to your SSL host:

    ```
    neo display-csr --account mysubaccount --user mymail@example.com --host hana.ondemand.com --name mycurrentcert
    ```

    Then, send the CSR to your CA for signing.

2.  When you receive the signed SSL certificate from your CA, upload it by executing:

    ```
    neo upload-domain-certificate --account mysubaccount --user mymail@example.com --host hana.ondemand.com --name mycurrentcert --location ./certificate.pub –-force
    ```

    The `--force` parameter allows you to overwrite the old certificate and bind the new certificate in one step. For more information, see [upload-domain-certificate](upload-domain-certificate-bb54abf.md).

    If you don't use the `--force` parameter, you won't be able to bind the certificate to the SSL host.

3.  To verify that the validity of the certificate is updated, execute `neo list-domain-certificates`.


**Related Information**  


[Configuring Custom Domains](configuring-custom-domains-77cf0e6.md#loio77cf0e6cd32e496c9cc8eeac4bedde94 "To make sure that your domain is trusted and all application data is protected, you need to first set up secure SSL communication. The next step will then be to make your application accessible via the custom domain and route traffic to it.")

[set-ssl-host](set-ssl-host-2956975.md "Configures and updates an SSL host. Allows you to replace an SSL certificate with a different one, manage TLS protocol versions, and configure a bundle of trusted CAs.")

[upload-domain-certificate](upload-domain-certificate-bb54abf.md "Uploads a signed custom domain certificate to SAP BTP. You can upload either a certificate based on a previously generated CSR via the generate-csr command, or another valid certificate with its corresponding private key.")

[bind-domain-certificate](bind-domain-certificate-8722bcb.md "Binds a certificate to an SSL host. The certificate must already be uploaded.")

[unbind-domain-certificate](unbind-domain-certificate-f8d24b6.md "Unbinds a certificate from an SSL host. The certificate will not be deleted from SAP BTP storage.")

[list-domain-certificates](list-domain-certificates-dfb8438.md "Use this command to list certificates available for a custom domain.")

