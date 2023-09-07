<!-- loiofe47e02fd9514ab889c37250ed771c0c -->

# Test Security Locally

When you add user authentication to your application, you can test it first on the local server before uploading it to SAP BTP.

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://me.sap.com/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**



> ### Note:  
> On the local server, authentication is handled locally, that is, not by the SAP ID service. When you try to access a protected resource on the local server, you will see a local login page \(not SAP ID service's or another identity provider's login page\). User access is then either granted or denied based on a local JSON [\(JavaScript Object Notation](http://www.json.org/)\) file \(*<local\_server\_dir\>/config\_master/com.sap.security.um.provider.neo.local/neousers.json*\), which defines the local set of user accounts, along with their roles and attributes. This is just for testing purposes. When you deploy to the cloud, user authentication is still handled by the SAP ID service.



<a name="loiofe47e02fd9514ab889c37250ed771c0c__section_75EAEAD90999455AB2937E120B583BA8"/>

## Test Locally with the Console Client

To test security locally, you need to find and edit manually the JSON file configuring local test users. It is located at *<local\_server\_dir\>/config\_master/com.sap.security.um.provider.neo.local/neousers.json*.

The following example shows a sample configuration of a JSON file with two users, along with their attributes and roles: first user with id `john` and password `johndoe`, and second user `jane` with password `janedoe`.

```json
{
  "Users": [
    {
      "UID": "john",
      "Password": "{SSHA}Ub53I5XdyH/Nh3gr3pUQ6vPyjYPPRVKF",
      "Roles": [
        "Everyone"
      ],
      "Attributes": [
        {
          "attributeName": "firstname",
          "attributeValue": "John"
        },
        {
          "attributeName": "lastname",
          "attributeValue": "Doe"
        },
        {
          "attributeName": "email",
          "attributeValue": "john.doe@sap.com"
        }
      ]
    },
    {
      "UID": "jane",
      "Password": "{SSHA}/obq802EmKc+rc4/fjU/XzbvBiaHtNIH",
      "Roles": [
        "Employee",
               "Manager"
      ],
      "Attributes": [
        {
          "attributeName": "firstname",
          "attributeValue": "Jane"
        },
        {
          "attributeName": "lastname",
          "attributeValue": "Doe"
        },
        {
          "attributeName": "email",
          "attributeValue": "jane.doe@sap.com"
        }
      ]
    }
  ]
}

```

> ### Note:  
> `SSHA` is a password storage scheme. When developing locally, you can use the `slappasswd` utility – an `OpenLDAP` password utility for Linux, Mac OS X, or other Unix-based OS – to generate such hashes:
> 
> `slappasswd -h {SSHA} -s <password>`



## Troubleshooting

When stopping your local server, you might see the following error logs:

```
#ERROR#org.apache.catalina.core.ContainerBase##anonymous#System Bundle Shutdown###ContainerBase.removeChild: stop: 
org.apache.catalina.LifecycleException: Failed to stop component 
[StandardEngine[Catalina].StandardHost[localhost].StandardContext[/idelogin]]
```

This error causes *no* harm and you don't need to take any measures.



## Next Steps

-   After testing, you can proceed with deploying the application to SAP BTP. For more information, see [Deploying and Updating Java Applications](../30-development-neo/deploying-and-updating-java-applications-e5dfbc6.md).

-   After deploying on the cloud, you may need to perform configuration steps using the cockpit. For more information, see [Security Configuration](security-configuration-baadd42.md).


