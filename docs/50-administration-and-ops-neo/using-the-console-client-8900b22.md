<!-- loio8900b22376f84c609ee9baf5bf67130a -->

# Using the Console Client

You execute a console client command by entering *neo <command name\>* with the appropriate parameters. To list all parameters available for the respective command, execute *neo help <command name\>*.

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/docs/btp/sap-business-technology-platform/sap-business-technology-platform?version=Cloud) .**



-   [Opening the Console Client](using-the-console-client-8900b22.md#loio8900b22376f84c609ee9baf5bf67130a__opening_the_console_client)
-   [Properties File](using-the-console-client-8900b22.md#loio8900b22376f84c609ee9baf5bf67130a__properties_file)
-   [Command Line](using-the-console-client-8900b22.md#loio8900b22376f84c609ee9baf5bf67130a__command_line)
-   [Parameter Priority](using-the-console-client-8900b22.md#loio8900b22376f84c609ee9baf5bf67130a__parameter_priority)
-   [Parameter Values](using-the-console-client-8900b22.md#loio8900b22376f84c609ee9baf5bf67130a__parameter_values)
-   [Proxy Settings](using-the-console-client-8900b22.md#loio8900b22376f84c609ee9baf5bf67130a__proxy_settings)
-   [Output Mode](using-the-console-client-8900b22.md#loio8900b22376f84c609ee9baf5bf67130a__output_mode)

You can define the parameters of the different commands either directly in *the command line*, or, in *a properties file*:

```
neo <command name> <mandatory parameters> [optional parameters]
```

```
neo <command name> <properties file location>
```



<a name="loio8900b22376f84c609ee9baf5bf67130a__opening_the_console_client"/>

## Opening the Console Client

The console client is part of the SDK for SAP BTP,Neo environment. You can find it in the tools folder of your SDK installation.

To start it, open the command prompt and change the current directory to the <SDK\_installation\_folder\>\\tools location, which contains the neo.bat and neo.sh files.



<a name="loio8900b22376f84c609ee9baf5bf67130a__command_line"/>

## Command Line

You can deploy the same application as in the example above by executing the following command directly in the command line:

```
neo deploy --account <subaccount technical name> --application <application name> --source samples/deploy_war/example.war --user <user name or email>
```



<a name="loio8900b22376f84c609ee9baf5bf67130a__properties_file"/>

## Properties File

Within the*tools* folder, a file `example_war.properties` can be found in the `samples/deploy_war folder`. In the file, enter your own user and subaccount name:

```

################################################
    # General settings - relevant for all commands #
    ################################################

    # Your subaccount technical name
    account=<your subaccount>

    # Application name
    application=<your application name>

    # User for login to hana.ondemand.com.
    user=<email or user name>

    # Host of the admin server. Optional. Defaults to hana.ondemand.com.
    host=hana.ondemand.com

    #################################################################
    # Deployment descriptor settings - relevant only for deployment #
    #################################################################

    # List of file system paths to *.war files and folders containing them
    source=samples/deploy_war/example.war
  

```

Then execute the deployment with the following line:

```
neo deploy samples/deploy_war/example_war.properties
```

Note that you can have more than one properties file. For example, you can have a different properties file for each application or user in your subaccount.



<a name="loio8900b22376f84c609ee9baf5bf67130a__parameter_priority"/>

## Parameter Priority

Argument values specified in the command line override the values specified in the properties file. For example, if you have specified `account=a` in the properties file and then enter `account=b` in the command line, the operation will take effect in `account b`.



<a name="loio8900b22376f84c609ee9baf5bf67130a__parameter_values"/>

## Parameter Values

Since the client is executed in a console environment, not all characters can be used in arguments. There are special characters that should be quoted and escaped.

Consult your console/shell user guide on how to use special characters as command line arguments.

For example, to use argument with value `abc&()[]{}^=;!'+,`~123` on Windows 7, you should quote the value and escape the`!` character. Therefore you should use `"abc&()[]{}^=;^!'+,`~123"`.

*User*

You can use your e-mail, SAP ID or user name.

*Password*

Do not specify your password in the properties file or as a command line argument. Enter a password only when prompted by the console client.

For example, use:

```
neo deploy samples/deploy_war/example_war.properties
```

instead of

```
neo deploy --password <mypassword > samples/deploy_war/example_war.properties
```

> ### Restriction:  
> Your password cannot start with the "`@`" character.

> ### Note:  
> You can't log on with SAP Universal ID. Log on with the password associated with your account \(S-user or P-user\) in the default identity provider, SAP ID service.
> 
> If you've forgotten this password and this user is associated with your SAP Universal ID user, reset your password.
> 
> For more information, see SAP Note [3085908](https://me.sap.com/notes/3085908).



<a name="loio8900b22376f84c609ee9baf5bf67130a__proxy_settings"/>

## Proxy Settings

If you work in a proxy environment, before you execute commands, you need to configure the proxy.

For more information, see [Set Up the Console Client](https://help.sap.com/viewer/ea72206b834e4ace9cd834feed6c0e09/Cloud/en-US/7613dee4711e1014839a8273b0e91070.html).



<a name="loio8900b22376f84c609ee9baf5bf67130a__output_mode"/>

## Output Mode

You can configure the console to print detailed output during command execution.

For more information, see [Verbose Mode of the Console Commands Output](https://help.sap.com/viewer/ea72206b834e4ace9cd834feed6c0e09/Cloud/en-US/4b6069b765fd4b299fbdd1415901d3da.html).

**Related Information**  


[Console Client Commands](https://help.sap.com/viewer/ea72206b834e4ace9cd834feed6c0e09/Cloud/en-US/56e309f496cc446ba441d862db94cb18.html)

