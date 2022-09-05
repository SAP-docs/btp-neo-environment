<!-- loio16f9fab6ae2d40fda106cc7b469d484b -->

# create-vm

Creates a new virtual machine and starts it.



> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**



```
neo create-vm --account <subaccount_technical_name> --user <e-mail_or_user> --host <host> --name <vm_name> --size <vm_size>
```



## Parameters




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

Subaccount technical name

`Type`: string \(up to 30 characters; lowercase letters and numbers, starting with a letter\)



</td>
</tr>
<tr>
<td valign="top">

`-h`, `--host`



</td>
<td valign="top">

Enter a region host.

`Type`: URL. For acceptable values, see [Regions](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/350356d1dc314d3199dca15bd2ab9b0e.html "You can deploy applications in different regions. Each region represents a geographical location (for example, Europe, US East) where applications, data, or services are hosted.") :arrow_upper_right:.



</td>
</tr>
<tr>
<td valign="top">

 `-n`, `--name` 



</td>
<td valign="top">

Name of the virtual machine

`Type`: string \(up to 30 characters; lowercase letters and numbers, starting with a letter\)



</td>
</tr>
<tr>
<td valign="top">

`-p`, `--password`



</td>
<td valign="top">

To protect your password, enter it only when prompted by the console client and not explicitly as a parameter in the properties file or the command line.

`Type`: string



</td>
</tr>
<tr>
<td valign="top">

`-u`, `--user`



</td>
<td valign="top">

Use your email, SAP ID, or user name.

`Type`: string



</td>
</tr>
<tr>
<td valign="top">

`-z`, `--size` 



</td>
<td valign="top">

The size of the newly created virtual machine.

`Acceptable values`: x-small, small, medium, large, x-large



</td>
</tr>
</table>


<table>
<tr>
<th valign="top" colspan="2">

Optional



</th>
</tr>
<tr>
<td valign="top">

`--preserve-volume`



</td>
<td valign="top">

Choose to preserve the volume on virtual machine termination.

`Type:` switch. It takes no value.

`Default`: off



</td>
</tr>
<tr>
<td valign="top">

`--private-key-passphrase`



</td>
<td valign="top">

Private key passphrase

The passphrase is used to encrypt the private key in the generated key pair. You will need it when you connect to the virtual machine using an SSH client.

> ### Note:  
> The passphrase should contain at least five characters in total: lowercase letters \(a-z\), uppercase letters \(A-Z\), numbers \(0-9\), and special characters. For production scenarios, make sure to protect your key pair with a passphrase that consists of at least fifteen characters.

If you do not provide `-pkp` as a parameter in the command line, you will be prompted to enter a passphrase.

If you do not enter a passphrase, the command will be executed but the private key will not be encrypted.



</td>
</tr>
<tr>
<td valign="top">

 `--private-key-passphrase-confirmation` 



</td>
<td valign="top">

Private key passphrase confirmation

If you do not provide `-pkpc` as a parameter in the command line, you will be prompted to confirm your passphrase.



</td>
</tr>
<tr>
<td valign="top">

`-l`, `--ssh-key-location`



</td>
<td valign="top">

The path to a public key of certificate that will be uploaded and used to log in on the newly created virtual machine.

`Type:` string



</td>
</tr>
<tr>
<td valign="top">

 `-k`, `--ssh-key-name` 



</td>
<td valign="top">

The name of the already existing public key to be used to login on the newly created virtual machine.

`Type:` string. It can contain only alphanumeric characters \(0-9, a-z, A-Z\), underscore \(\_\), and hyphen \(-\). The allowed name length is between 1 and 128 characters.



</td>
</tr>
<tr>
<td valign="top">

 `-v`, `--volume-id` 



</td>
<td valign="top">

Unique identifier of the volume from which the virtual machine will be created.

`Type:` string

`Condition`: Use when you want to create a new virtual machine from a volume.



</td>
</tr>
<tr>
<td valign="top">

 `-s`, `--volume-snapshot-id` 



</td>
<td valign="top">

Unique identifier of the volume snapshot.

`Type:` string

`Condition`: Use when you want to create a new virtual machine from a volume snapshot.



</td>
</tr>
<tr>
<td valign="top">

 `-y`, `--synchronous` 



</td>
<td valign="top">

Waits until the creation is complete.

`Type:` switch. It takes no value.

`Default`: off



</td>
</tr>
</table>



## Example

```
neo create-vm --account mysubaccount --user mymail@example.com --host hana.ondemand.com --name myvm --size x-small
```

**Related Information**  


[Manage Virtual Machines](https://help.sap.com/viewer/c746ff81651e4b8fb6efc11146091016/Cloud/en-US/c0d2dd37428944d3b673ffdd74f3a975.html "You can create and start a virtual machine using either the SAP BTP cockpit or the console client. Then, you establish a secure communication channel to it over Secure Shell (SSH) protocol. You open an SSH tunnel and get all the communication details needed for you to log in to the virtual machine and install and maintain your software.") :arrow_upper_right:

[Manage Volume Snapshots](https://help.sap.com/viewer/c746ff81651e4b8fb6efc11146091016/Cloud/en-US/93dd4760f72f42f6a668c903030272a4.html "You can take a snapshot of an existing virtual machine volume in your subaccount and use it to create a new virtual machine with the same file system thus saving any manual installation.") :arrow_upper_right:

