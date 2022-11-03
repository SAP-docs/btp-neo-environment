<!-- loio4023e1504ebc4a00a5108b8f716fe9a3 -->

# Troubleshooting and Support

Troubleshooting and support information for the btp CLI.



<a name="loio4023e1504ebc4a00a5108b8f716fe9a3__section_dv5_kb1_ckb"/>

## Make sure that you are using a recent version of the btp CLI client

We recommend checking for updates of the client on a regular basis. Most new functionality is added via the CLI server, so no update from your side is required. But if new functionality is added to the client, the only way to get it is by downloading and installing a newer version.

Run the command `btp` or `btp --info` to find out which version of the client you are using. Then check on our [download page](https://tools.hana.ondemand.com/#cloud-cpcli) for the current version and install the latest client.

Use `btp --help` to display an overview of all commands. If new commands are available but cannot be used with your client version, these commands are marked with a notice to update your client. If you run such a command, you get an error message pointing you to the client version that you need.



<a name="loio4023e1504ebc4a00a5108b8f716fe9a3__section_b25_g3c_xlb"/>

## I cannot log on

To log on, run `btp login`. During interactive logon, confirm the server URL that is proposed by the CLI and provide the subdomain of your global account. The btp CLI is part of our cloud management tools feature set B. This means that you can only access a global account that uses this feature set B. For example, all trial accounts are on feature set B. For more information, see [Cloud Management Tools — Feature Set Overview](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/caf4e4e23aef4666ad8f125af393dfb2.html "Cloud management tools represent the group of technologies designed for managing SAP BTP.") :arrow_upper_right:.



<a name="loio4023e1504ebc4a00a5108b8f716fe9a3__section_tpf_hyh_xlb"/>

## I'd like to setup a global account with the command line

If you don't know how to get started, you might want to have a look at the appropriate workflow: [Setting Up a Trial Account via the Command Line [Feature Set B]](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/a21360fa19714751a7c49c796d39ac3d.html "If your trial account is running on the cloud management tools feature set B, you can use the command-line interfaces to set it up. For all tasks on global account and subaccount level, you use the SAP BTP command line interface (btp CLI). Once you’ve created a Cloud Foundry environment instance (a Cloud Foundry org), you use the Cloud Foundry CLI (cf CLI). This procedure works without the SAP BTP cockpit (except that you need the global account subdomain to log in, which you may have to look up in the cockpit).") :arrow_upper_right: or [Setting Up a Global Account via the Command Line [Feature Set B]](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/accd5b2389b04f4daf8a79b606435927.html "Your global account is the entry point for managing the resources, landscape, and entitlements for your departments and projects in a self-service manner in SAP BTP. You can use the command-line tool btp CLI to set it up.") :arrow_upper_right:.



<a name="loio4023e1504ebc4a00a5108b8f716fe9a3__section_csr_4s1_ckb"/>

## I'd like to see a more detailed output \(verbose mode\)

If you get an error message that is not helpful enough, or if you want to find out more about what exactly happened after you ran a command, use the `btp --verbose` option with your command and run it again. The btp CLI will try to execute the command again, but also print information about each step of the command execution. This might help you understand what exactly went wrong and provide hints for you to solve the issue. If you need to create a support request, providing this information helps us analyze the error and provide a solution more quickly.

Here is an example of the `btp list security/role-collection` command call without the option:

> ### Sample Code:  
> ```
> btp list security/role-collection
> name                         	description
> Global Account Administrator 	Administrative access to the global account
> Global Account Viewer        	Read-only access to the global account
> 
> OK
> 
> ```

If you use `btp --verbose list security/role-collection`, the output is much more lengthy. It contains information such as client version and the current context, the correlation ID, and request and response details.

> ### Sample Code:  
> ```
> btp --verbose list security/role-collection
> 2019/12/18 10:35:21.309235 main.go:34: Support trace activated.
> 2019/12/18 10:35:21.309284 main.go:35: Client version 1.x.x running with command line: --verbose list security/role-collection
> 2019/12/18 10:35:21.309349 clifiles.go:65: Config file path was set to /Users/my-user/Library/Caches/.btp/config.json
> 2019/12/18 10:35:21.309386 login.go:138: Reading configuration from &{/Users/my-user/Library/Caches/.btp config.json commands.json}
> 2019/12/18 10:35:21.309578 main.go:60: CLI server URL:            http://localhost:8080
> 2019/12/18 10:35:21.309591 main.go:60: Global account subdomain:  my-ga-subdomain
> 2019/12/18 10:35:21.309594 main.go:60: Subaccount:                not set
> 2019/12/18 10:35:21.309597 main.go:60: Configuration file:        /Users/my-user/Library/Caches/.btp/config.json
> 2019/12/18 10:35:21.309603 login.go:138: Reading configuration from &{/Users/my-user/Library/Caches/.btp config.json commands.json}
> 2019/12/18 10:35:21.309663 main.go:68: Successfully loaded login config.
> 2019/12/18 10:35:21.311758 protocol.go:41: Loading command metadata from http://localhost:8080/commandMetadata/v-1
> 2019/12/18 10:35:21.311860 protocol.go:248: Adding correlation ID 1234abcde-ab12-12ab-34cd-123456abcdef to request http://localhost:8080/commandMetadata/v-1
> 2019/12/18 10:35:21.319441 protocol.go:53: Received response 200 from request http://localhost:8080/commandMetadata/v-1
> 2019/12/18 10:35:21.322441 protocol.go:161: Executing command list security/role-collection with parameters map[subaccount:{0 }]
> 2019/12/18 10:35:21.322622 protocol.go:205: Sending request:
> {POST http://localhost:8080/command/v-1/security/role-collection?list HTTP/1.1 1 1 map[Content-Type:[application/json;charset=UTF-8] X-Cpcli-Subdomain:[my-ga-subdomain]] {{"paramValues":{"subaccount":null}}} 0x12c6380 35 [] false localhost:8080 map[] map[] <nil> map[]   <nil> <nil> <nil> 0xc0000ae070}
> to http://localhost:8080/command/v-1/security/role-collection?list
> 2019/12/18 10:35:21.322642 protocol.go:248: Adding correlation ID 1234abcde-ab12-12ab-34cd-123456abcdef to request http://localhost:8080/command/v-1/security/role-collection?list
> 2019/12/18 10:35:24.683689 protocol.go:214: Received response 200 from request http://localhost:8080/command/v-1/security/role-collection?list
> 2019/12/18 10:35:24.690916 main.go:196: Getting response mapping for command result code 200
> 2019/12/18 10:35:24.690943 main.go:198: Response mapping: {[200] ok {table  [name description]}}
> name                         description
> Global Account Administrator Administrative access to the global account
> Global Account Viewer        Read-only access to the global account
> 
> OK
> 
> ```



<a name="loio4023e1504ebc4a00a5108b8f716fe9a3__section_q5m_151_ckb"/>

## I need support

Use component `BC-CP-TOOLS-CLI` to contact support.

If a correlation ID is printed with your error message, please provide it with your support ticket. The correlation ID is created for each command execution, and is passed with all of its steps. It allows the identification of all log messages related to a command execution.

See [Getting Support](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/5dd739823b824b539eee47b7860a00be.html "Use SAP Community, get guided answers, or explore SAP Support Portal.") :arrow_upper_right:.

