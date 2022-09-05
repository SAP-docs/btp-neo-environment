<!-- loio7613dee4711e1014839a8273b0e91070 -->

# Set Up the Console Client

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**



## Prerequisites

As the SAP BTP console client is part of the SAP BTP SDK for Neo environment, you must have downloaded and extracted the SAP BTP SDK for Neo environment. For more information, see [Install the SAP BTP SDK for Neo Environment](install-the-sap-btp-sdk-for-neo-environment-7613843.md).



<a name="loio7613dee4711e1014839a8273b0e91070__section_7D2269378D8046A996B6657F6A4F3F9E"/>

## Context

SAP BTP console client is part of the SAP BTP SDK for Neo environment. You can find it in the `tools` folder of your SDK installation. Before using the tool, you need to configure it to work with the platform.



<a name="loio7613dee4711e1014839a8273b0e91070__section_8DE5CE0C332A4C37BF794E0112EA77B3"/>

## Procedure

1.  Open the command prompt.
2.  Change the current directory to the `<SDK_installation_folder>\tools` location, which contains the *neo.bat* and *neo.sh* files. For example:

    ```
    
    cd C:\HCP\SDK
    cd tools
    
    ```

3.  In case you use a proxy server, specify the proxy settings by using environment variables. You can find sample proxy settings in the *readme.txt* file in the `\tools` folder of your SDK location.
    -   `Microsoft Windows` 

        > ### Note:  
        > -   For the new variables to be effective every time you open the console, define them using *Advanced System Settings* \> *Environment Variables* and restart the console.
        > -   For the new variables to be valid only for the currently open console, define them in the console itself.

        For example, if your proxy host is ***proxy*** and proxy port is ***8080***, specify the following environment variables:

        ```
        
        set HTTP_PROXY_HOST=proxy
        set HTTP_PROXY_PORT=8080
        set HTTPS_PROXY_HOST=proxy
        set HTTPS_PROXY_PORT=8080
        set HTTP_NON_PROXY_HOSTS="localhost"
        
        ```

        If you need basic proxy authentication, enter your user name and password:

        ```
        set HTTP_PROXY_USER=<user_name>
        set HTTP_PROXY_PASSWORD=<password>
        set HTTPS_PROXY_USER=<user_name>
        set HTTPS_PROXY_PASSWORD=<password>
        
        
        ```

    -   `Linux`, `Mac OS X`, or other `Unix` based OS:

        ```
        
        export http_proxy=http://proxy:8080
        export https_proxy=https://proxy:8080
        export no_proxy="localhost"
        
        ```

        If you need basic proxy authentication, enter your user name and password:

        ```
        export http_proxy=http://user:password@proxy:8080
        export https_proxy=https://user:password@proxy:8080
        
        ```



You can now start using the Console Client.

**Related Information**  


[Using the Console Client](../50-administration-and-ops-neo/using-the-console-client-8900b22.md "You execute a console client command by entering neo <command name> with the appropriate parameters. To list all parameters available for the respective command, execute neo help <command name>.")

[Console Client for the Neo Environment](../50-administration-and-ops-neo/console-client-for-the-neo-environment-7613230.md)

