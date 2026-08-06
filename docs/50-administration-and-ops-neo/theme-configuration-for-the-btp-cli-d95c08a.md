<!-- loiod95c08ad1e694317bcae3470a77a6a7d -->

# Theme Configuration for the btp CLI

Customize the visual theme of the SAP BTP Command Line Interface \(btp CLI\).



## Context

> ### Caution:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/docs/btp/sap-business-technology-platform/sap-business-technology-platform?version=Cloud) .**

> ### Tip:  
> Additional IP outbound addresses will soon be used in all regions in the Neo environment. For more information, see [Additional IP Addresses Added to SAP BTP, Neo Runtime Regions](https://help.sap.com/whats-new/cf0cb2cb149647329b5d02aa96303f56?version=Cloud&Component=Region&Valid_as_Of=2026-11-02:2026-11-02). To subscribe to such notifications, see SAP Note [3513325](https://me.sap.com/notes/3513325).

You can control the visual appearance of the SAP BTP Command Line Interface \(btp CLI\) output by using the theme configuration parameter.



## Procedure

1.  **Available Themes**

    The following values are supported:

    -   **default** \(default\): applies the SAP-themed visual style to the CLI output.
    -   **none**: applies the standard CLI appearance without additional theming.

2.  **Set the Theme**

    To configure the theme, use:

    ```
    btp set config --theme=<value>
    ```

    Examples:

    -   `btp set config --theme=default`
    -   `btp set config --theme=none`

3.  **Reset the Theme Configuration**

    To reset the theme setting to its default value, run:

    ```
    btp reset config –theme
    ```

4.  **NO\_COLOR Environment Variable**

    If the NO\_COLOR environment variable is set to true, any configured theme is ignored and the CLI output is displayed without theming.

    When `NO_COLOR=true` is set, it overrides the `--theme` configuration.


**Related Information**  


[Change Configuration Settings](change-configuration-settings-dba4eb6.md "Change the configuration settings to customize the behavior of the btp CLI.")

