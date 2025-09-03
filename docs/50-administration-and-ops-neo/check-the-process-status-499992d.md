<!-- loio499992d9c31648b0afdae88c463ba9b4 -->

# Check the Process Status

The status of an individual process is based on values that reflect the process run state and its monitoring metrics.



## Context

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/docs/btp/sap-business-technology-platform/sap-business-technology-platform?version=Cloud) .**



## Procedure

1.  In the cockpit, choose *Applications* \> *Java Applications* in the navigation area.

2.  Select an application in the application list by clicking the link on its name.

    This takes you to the overview page for the selected application.

    The *Processes* panel shows the number of running processes and the overall state for the metrics as follows:

    *State*

    -   Started
    -   Started \(Disabled\)
    -   Starting
    -   Stopping
    -   Application Error
    -   Infrastructure Error

    *Metric*

    -   OK
    -   Warning \(also shown for intermediate states\)
    -   Critical
    -   Pending

3.  Choose *Monitoring* \> *Processes* in the navigation area to go to the process overview to view the status summary and further details:


    <table>
    <tr>
    <th valign="top">

    Panel
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    Status Summary
    
    </td>
    <td valign="top">
    
    Displays the current values of the two status categories and the runtime version. A short text summarizes any problems that have been detected.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    State
    
    </td>
    <td valign="top">
    
    Indicates whether the process has been started or is transitioning between the *Started* and *Stopped* states. The *Error* state indicates a fault, such as server unavailability, timeout, or VM failure.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Runtime
    
    </td>
    <td valign="top">
    
    Shows the runtime version on which the application process is running and its current status:

    -   OK: Still within the first three months since it was released
    -   No longer recommended: Has exceeded the initial three-month period
    -   Expired: 15 months since its release date


    
    </td>
    </tr>
    </table>
    

