<!-- loio7c6df2db6332419ea7a862191525377c -->

# Account Administration Using the SAP BTP Command Line Interface \(btp CLI\) \[Feature Set B\]

Use the SAP BTP command line interface \(btp CLI\) for account management tasks, such as creating or updating subaccounts and directories, and managing entitlements. It is an alternative to the SAP BTP cockpit for all users who like to work in a terminal or want to automate operations using scripts.

The btp CLI offers convenient features for interactive use as well as for scripting: For the interactice user, there's login via SSO, command autocompletion, as well as several interactive commands with prompts. But all commands can also be run with parameters, so the btp CLI can just as well be used for scripting. In addition, there is the `--format JSON` option to receive the results as JSON instead of text, and it exposes exit codes for the result status. You can then use the capabilities of the shell, e.g. jq, to work with the results.

> ### Note:  
> The content in this section is only relevant for cloud management tools feature set B. For more information, see [Working with Cloud Management Tools Feature Set B in the Neo Environment](../10-concepts-neo/working-with-cloud-management-tools-feature-set-b-in-the-neo-environment-8c963e8.md) and [Cloud Management Tools - Feature Set Overview](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/caf4e4e23aef4666ad8f125af393dfb2.html).



<a name="loio7c6df2db6332419ea7a862191525377c__section_nc4_bpf_15b"/>

## Documentation

In this documentation, you learn how to download, install, update, and use the btp CLI. Additionally, see the following:

-   [btp CLI Command Reference](https://help.sap.com/docs/BTP/btp-cli/intro.html)

-   [Get Started with the SAP BTP Command Line Interface \(btp CLI\)](https://developers.sap.com/tutorials/cp-sapcp-getstarted.html)

-   [Automate Account Operations with the Command Line Interface](https://developers.sap.com/tutorials/cp-cli-automate-operations.html)

-   [Setting Up a Global Account via the Command Line [Feature Set B]](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/accd5b2389b04f4daf8a79b606435927.html "Your global account is the entry point for managing the resources, landscape, and entitlements for your departments and projects in a self-service manner in SAP BTP. You can use the command-line tool btp CLI to set it up.") :arrow_upper_right:

-   Access command help from the terminal with `btp help`




<a name="loio7c6df2db6332419ea7a862191525377c__section_lk5_xjg_qjb"/>

## How the btp CLI Works

 ![](images/Overview_of_CLI_for_SAP_BTP_3a71aa7.png) 

You download the btp CLI client to your local desktop and access it through the shell of your operating system. The client then accesses all required platform services through its backend, the CLI server, where the command definitions are stored. The CLI server delegates authentication and authorization to the authorization server, and forwards trust to the platform services, which then take care of authorization at the execution of each command.

**Related Information**  


[btp CLI Command Reference](https://help.sap.com/docs/BTP/btp-cli/intro.html)

