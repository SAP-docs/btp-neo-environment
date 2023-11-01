<!-- loio9b9f742a1b904a9f9e271ba21c788561 -->

# put-destination

This command uploads destination configuration properties files and JKS files. You can upload them on subaccount, application or subscribed application level.



> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**



```
neo put-destination --account <subaccount_technical_name> --user <e-mail_or_user> --localpath <destination_file_or_JKS_file_localpath> --host <host>
```



## Parameters



To list all parameters available for this command, execute `neo help put-destination` in the command line.


<table>
<tr>
<th valign="top" colspan="2">

Required

</th>
</tr>
<tr>
<td valign="top">

`-a`,

`--account`

</td>
<td valign="top">

Your subaccount. The subaccount for which you provide username and password.

`Type`: string \(up to 30 characters; lowercase letters and numbers, starting with a letter\)

</td>
</tr>
<tr>
<td valign="top">

`-b`,

`--application`

</td>
<td valign="top">

The application for which you upload a destination. Cases:

-   Use `--application <myapp>` if the application is running in your subaccount.
-   Use `--application <provider_subaccount>:<provider_app>` if the application is running in another subaccount.

`Type`: string \(up to 30 characters; lowercase letters and numbers, starting with a letter\)

</td>
</tr>
<tr>
<td valign="top">

`-h`,

`--host`

</td>
<td valign="top">

Enter a region host.

`Type`: URL. For acceptable values see [Regions](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/350356d1dc314d3199dca15bd2ab9b0e.html "You can deploy applications in different regions. Each region represents a geographical location (for example, Europe, US East) where applications, data, or services are hosted.") :arrow_upper_right:.

</td>
</tr>
<tr>
<td valign="top">

`--localpath` 

</td>
<td valign="top">

The path to a destination or a JKS file on your local file system.

`Type`: string

</td>
</tr>
<tr>
<td valign="top">

`-p`,

`--password`

</td>
<td valign="top">

Password for the specified user. To protect your password, enter it only when prompted by the console client and not explicitly as a parameter in the properties file or the command line.

`Type`: string

> ### Note:  
> When uploading a destination configuration file that contains a password field, the password value remains available in the file. However, if you later download this file, using the `get-destination` command, the password value will no more be visible. Instead, after `Password =...`, you will only see an empty space.



</td>
</tr>
<tr>
<td valign="top">

`-u`,

`--user`

</td>
<td valign="top">

Your email, SAP ID or user name

`Type`: string

</td>
</tr>
</table>



## Examples

-   To upload a destination on subaccount level, execute:

    ```
    neo put-destination --account mysubaccount --user p1234567890 --localpath C:\myfiles\myconfiguration.jks --host hanatrial.ondemand.com
    ```

-   To upload a destination on application level, execute:

    ```
    neo put-destination --account mysubaccount --user p1234567890 --application demo --localpath C:\SDK\tools\samples\connectivity\weather --host hanatrial.ondemand.com
    ```

-   To upload a destination on subscribed application level, execute:

    ```
    put-destination -h <host> -a <subaccount> -u <user> -b <provider_subaccount>:<application> --localpath <path to destination file>
    
    ```


**Related Information**  


[Upload Destinations](https://help.sap.com/viewer/b865ed651e414196b39f8922db2122c7/Cloud/en-US/7bd8fcd7e74c467c811144505e0280fb.html "") :arrow_upper_right:

[Exit Codes](exit-codes-7886796.md "")

