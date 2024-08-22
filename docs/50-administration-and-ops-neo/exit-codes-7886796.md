<!-- loio7886796eb9b9419fa6cecf1d215c38d8 -->

# Exit Codes

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of the following technology portfolios: application development; process automation; integration; data, analytics, and enterprise planning; artificial intelligence. The platform offers users the ability to turn data into business value, compose end-to-end business processes, connect entire IT landscapes, and personalize, build and extend SAP applications. This reduces the overall total cost of ownership maintaining SAP landscapes and third-party software across end-to-end business processes.") :arrow_upper_right:.**



## Overview

The exit code is a number that indicates the outcome of a command execution. It shows whether the command completes successfully or defines an error if something goes wrong during the execution.

When commands are executed as part of automated scripts, the exit codes provide feedback to the scripts, which allows the script to bypass known errors that can be met during execution. A script can also interact with the user in order to request additional information required for the script to complete.

All exit codes in SAP BTP are aligned to the Bash-Scripting Guide. For more information, see [Exit Codes With Special Meanings](http://tldp.org/LDP/abs/html/exitcodes.html#EXITCODESREF).



## Ranges

The set of exit codes is divided into ranges, based on the error type and the reason.


<table>
<tr>
<th valign="top">

Error Type

</th>
<th valign="top">

Start Number

</th>
<th valign="top">

End Number

</th>
<th valign="top">

Count

</th>
</tr>
<tr>
<td valign="top">

No error

</td>
<td valign="top">

0

</td>
<td valign="top">

0

</td>
<td valign="top">

1

</td>
</tr>
<tr>
<td valign="top">

Common errors

</td>
<td valign="top">

1

</td>
<td valign="top">

9

</td>
<td valign="top">

9

</td>
</tr>
<tr>
<td valign="top">

Missing parameters

</td>
<td valign="top">

10

</td>
<td valign="top">

39

</td>
<td valign="top">

30

</td>
</tr>
<tr>
<td valign="top">

Parameter validation errors

</td>
<td valign="top">

40

</td>
<td valign="top">

109

</td>
<td valign="top">

70

</td>
</tr>
<tr>
<td valign="top">

Authentication and Authorization Errors

</td>
<td valign="top">

110

</td>
<td valign="top">

126

</td>
<td valign="top">

17

</td>
</tr>
<tr>
<td valign="top">

Reserved space for system errors

</td>
<td valign="top">

127

</td>
<td valign="top">

165

</td>
<td valign="top">

39

</td>
</tr>
<tr>
<td valign="top">

Command-specific errors: frontend

</td>
<td valign="top">

166

</td>
<td valign="top">

209

</td>
<td valign="top">

44

</td>
</tr>
<tr>
<td valign="top">

Command-specific errors: backend

</td>
<td valign="top">

210

</td>
<td valign="top">

254

</td>
<td valign="top">

45

</td>
</tr>
<tr>
<td valign="top">

Reserved space for system errors

</td>
<td valign="top">

255

</td>
<td valign="top">

255

</td>
<td valign="top">

1

</td>
</tr>
</table>



## Exit Codes

Exit codes can be defined as *general* \(common for all commands\) and *command-specific* \(cover different cases via different commands\).


<table>
<tr>
<th valign="top">

Code

</th>
<th valign="top">

Meaning

</th>
<th valign="top">

Type/Reason

</th>
</tr>
<tr>
<td valign="top">

0

</td>
<td valign="top">

OK

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

1

</td>
<td valign="top">

General error

</td>
<td valign="top">

Error during execution of command

</td>
</tr>
<tr>
<td valign="top">

2

</td>
<td valign="top">

Command not found

</td>
<td valign="top">

Misspelled or missing command

</td>
</tr>
<tr>
<td valign="top">

3

</td>
<td valign="top">

Unsupported/Incompatible SDK version

</td>
<td valign="top">

SDK is not compatible with the runtime

</td>
</tr>
<tr>
<td valign="top">

4

</td>
<td valign="top">

Network error

</td>
<td valign="top">

Network problem or missing proxy configuration

</td>
</tr>
<tr>
<td valign="top">

5-9

</td>
<td valign="top">

Currently not used

</td>
<td valign="top">

Common errors

</td>
</tr>
<tr>
<td valign="top">

10

</td>
<td valign="top">

General missing parameter

</td>
<td valign="top">

Missing parameters

</td>
</tr>
<tr>
<td valign="top">

11

</td>
<td valign="top">

Missing host name

</td>
<td valign="top">

Missing parameters

</td>
</tr>
<tr>
<td valign="top">

12

</td>
<td valign="top">

Missing account name

</td>
<td valign="top">

Missing parameters

</td>
</tr>
<tr>
<td valign="top">

13

</td>
<td valign="top">

Missing application name

</td>
<td valign="top">

Missing parameters

</td>
</tr>
<tr>
<td valign="top">

14

</td>
<td valign="top">

Missing user name

</td>
<td valign="top">

Missing parameters

</td>
</tr>
<tr>
<td valign="top">

15-19

</td>
<td valign="top">

Currently not used

</td>
<td valign="top">

Missing parameters

</td>
</tr>
<tr>
<td valign="top">

20-39

</td>
<td valign="top">

Available for use by commands

</td>
<td valign="top">

Missing parameters

</td>
</tr>
<tr>
<td valign="top">

40

</td>
<td valign="top">

General parameter is invalid or empty

</td>
<td valign="top">

Validation errors

</td>
</tr>
<tr>
<td valign="top">

41

</td>
<td valign="top">

Host name parameter is invalid or empty

</td>
<td valign="top">

Validation errors

</td>
</tr>
<tr>
<td valign="top">

42

</td>
<td valign="top">

Account name parameter is invalid or empty

</td>
<td valign="top">

Validation errors

</td>
</tr>
<tr>
<td valign="top">

43

</td>
<td valign="top">

Application name parameter is invalid or empty

</td>
<td valign="top">

Validation errors

</td>
</tr>
<tr>
<td valign="top">

44-49

</td>
<td valign="top">

Currently not used

</td>
<td valign="top">

Validation errors

</td>
</tr>
<tr>
<td valign="top">

50-109

</td>
<td valign="top">

Available for use by commands

</td>
<td valign="top">

Validation errors

</td>
</tr>
<tr>
<td valign="top">

110

</td>
<td valign="top">

Wrong user or password

</td>
<td valign="top">

Authentication and authorization errors

</td>
</tr>
<tr>
<td valign="top">

111

</td>
<td valign="top">

General authentication and authorization error

</td>
<td valign="top">

Authentication and authorization errors

</td>
</tr>
<tr>
<td valign="top">

112-114

</td>
<td valign="top">

Currently not used

</td>
<td valign="top">

Authentication and authorization errors

</td>
</tr>
<tr>
<td valign="top">

115-126

</td>
<td valign="top">

Available for use by commands

</td>
<td valign="top">

Authentication and authorization errors

</td>
</tr>
<tr>
<td valign="top">

127-165

</td>
<td valign="top">

Special exit codes

</td>
<td valign="top">

System-dependent errors

</td>
</tr>
<tr>
<td valign="top">

166

</td>
<td valign="top">

General frontend error

</td>
<td valign="top">

Frontend

</td>
</tr>
<tr>
<td valign="top">

167 - 209

</td>
<td valign="top">

Available for use by commands

</td>
<td valign="top">

Frontend

</td>
</tr>
<tr>
<td valign="top">

210

</td>
<td valign="top">

General backend error

</td>
<td valign="top">

Backend

</td>
</tr>
<tr>
<td valign="top">

211 - 254

</td>
<td valign="top">

Available for use by commands

</td>
<td valign="top">

Backend

</td>
</tr>
<tr>
<td valign="top">

255

</td>
<td valign="top">

Special exit codes

</td>
<td valign="top">

System-dependent errors

</td>
</tr>
</table>

**Related Information**  


[Console Client for the Neo Environment](https://help.sap.com/viewer/ea72206b834e4ace9cd834feed6c0e09/Cloud/en-US/76132306711e1014839a8273b0e91070.html)

