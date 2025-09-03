<!-- loiob6cd0ceae2b040fc96df3773eb8b156b -->

# Session Reuse

You can configure the "session reuse" boolean property to mitigate third-party cookie deprecation if your HTML5 application is affected by it.

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/docs/btp/sap-business-technology-platform/sap-business-technology-platform?version=Cloud) .**

This option is relevant only when applications are embedded in an iFrame screen element. When you set "session reuse" to true \(the default value is false\), authentication for the applications occurs in a new tab instead of within the iFrame itself. For more details on how this affects the authentication process, please visit [Mitigating Third-Party Cookie Deprecation](https://help.sap.com/docs/btp/sap-btp-neo-environment/mitigating-third-party-cookie-deprecation).



<a name="loiob6cd0ceae2b040fc96df3773eb8b156b__section_ryx_xkn_jfc"/>

## Configuration and Example

To configure the Session Reuse property, add a JSON string with the following format to the neo-app.json file:

```
```
"sessionReuse": true | false
``
```

An example configuration that mitigates third-party cookie deprecation looks like this:

> ### Sample Code:  
> ```
> ```
> "sessionReuse": true
> ```
> ```

