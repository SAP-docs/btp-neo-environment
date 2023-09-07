<!-- loiobc623358916d47b48077b0e25b626a62 -->

# get-destination

This command downloads \(reads\) destination configuration properties files and destination certificate files. You can download them on subaccount, application or subscribed application level.



> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**



```
neo get-destination --account <subaccount_technical_name> --user <e-mail_or_user> --localpath <localpath_to_destination_file_or_JKS_file> --host <host>
```



## Parameters



To list all parameters available for this command, execute `neo help get-destination` in the command line.


<table>
<tr>
<th valign="top" colspan="2">

Required



</th>
</tr>
<tr>
<td valign="top">

`-a`, `--account` 



</td>
<td valign="top">

Your subaccount. The subaccount for which you provide username and password.

`Type`: string \(up to 30 characters; lowercase letters and numbers, starting with a letter\)



</td>
</tr>
<tr>
<td valign="top">

`-b`, `--application` 



</td>
<td valign="top">

The application for which you download a destination. Cases:

-   Use `--application <myapp>` if the application is running in your subaccount.
-   Use `--application <provider_subaccount>:<provider_app>` if the application is running in another subaccount.

`Type`: string \(up to 30 characters; lowercase letters and numbers, starting with a letter\)



</td>
</tr>
<tr>
<td valign="top">

`-h`, `--host` 



</td>
<td valign="top">

Enter a region host.

`Type`: URL, for acceptable values see [Regions](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/350356d1dc314d3199dca15bd2ab9b0e.html "You can deploy applications in different regions. Each region represents a geographical location (for example, Europe, US East) where applications, data, or services are hosted.") :arrow_upper_right:



</td>
</tr>
<tr>
<td valign="top">

`--localpath`



</td>
<td valign="top">

The path on your local file system where a destination or a JKS file will be downloaded. If not set, no files will be downloaded.

`Type`: string



</td>
</tr>
<tr>
<td valign="top">

`--name`



</td>
<td valign="top">

The name of the destination or JKS file to be downloaded. If not set, the names of all destination or JKS files for the service will be listed.

`Type`: string



</td>
</tr>
<tr>
<td valign="top">

`-p`, `--password` 



</td>
<td valign="top">

Password for the specified user. To protect your password, enter it only when prompted by the console client and not explicitly as a parameter in the properties file or the command line.

`Type`: string

> ### Note:  
> If you download a destination configuration file that contains a password field, the password value will not be visible. Instead, after `Password =...`, you will only see an empty space. You will need to learn the password in other ways.



</td>
</tr>
<tr>
<td valign="top">

`-u`, `--user` 



</td>
<td valign="top">

Your email, SAP ID or user name

`Type`: string



</td>
</tr>
</table>



## Examples

-   To read a destination on subaccount level, execute:

    ```
    neo get-destination --account mysubaccount --user p1234567890 --name weather --localpath C:\myfiles --host hanatrial.ondemand.com 
    ```

-   To read a destination on application level, execute:

    ```
    neo get-destination --account mysubaccount -user p1234567890 --application demo --name myconfiguration.jks --localpath C:\SDK\tools\samples\connectivity --host hanatrial.ondemand.com
    ```

-   To read a destination on subscribed application level, execute:

    ```
    neo get-destination --account mysubaccount --user p1234567890 --application othersubaccount:remotedemo --name weather --localpath C:\SDK\tools\samples\connectivity --host hanatrial.ondemand.com
    ```


**Related Information**  


[Download Destinations](https://help.sap.com/viewer/b865ed651e414196b39f8922db2122c7/Cloud/en-US/f02a359183c74429a9d82b23feb15243.html "") :arrow_upper_right:

[Exit Codes](exit-codes-7886796.md "")

