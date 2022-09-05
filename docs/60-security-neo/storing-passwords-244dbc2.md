<!-- loio244dbc262b5c4d37a42cfd7405e4719e -->

# Storing Passwords



## Context

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**

Using the [Password Storage API](https://api.sap.com/api/SCP_PasswordStorage/resource), you can securely persist passwords and key phrases such as passwords for keystore files. Once persisted in the password storage, they:

-   Can be accessed from different application computing units;
-   Survive application restarts and updates;
-   Are a subject of automatic backup;
-   Stay persisted unless you explicitly delete them via the API, or you undeploy your application.

Before transportation and persistence, passwords are encrypted with an encryption key which is specific for the application that owns the password. They are stored according to subscription, and accessible only when the owning application is working on behalf of the corresponding subscription.

> ### Note:  
> Each password is identified by an alias. To check the rules and constraints about passwords aliases, permitted characters and length, see the [security javadoc](https://help.hana.ondemand.com/javadoc/index.html).

 <a name="concept_x5n_gpw_gn"/>

<!-- concept\_x5n\_gpw\_gn -->

## Adding Resource Reference

To use the password storage API, you need to add a resource reference to `PasswordStorage` in the `web.xml` file of your application, which is located in the `\WebContent\WEB-INF` folder as shown below:

```
<resource-ref>
  <res-ref-name>PasswordStorage</res-ref-name>
  <res-type>com.sap.cloud.security.password.PasswordStorage</res-type>
</resource-ref>
```

 <a name="concept_kvt_qpw_gn"/>

<!-- concept\_kvt\_qpw\_gn -->

## Looking Up the JNDI

An initial JNDI context can be obtained by creating a `javax.naming.InitialContext` object. You can then consume the resource by looking up the naming environment through the `InitialContext` class as follows:

```
InitialContext ctx = new InitialContext();
PasswordStorage passwordStorage = (PasswordStorage) ctx.lookup("java:comp/env/PasswordStorage");
```

Note that according to the Java EE Specification, the prefix **java:comp/env** should be added to the JNDI resource name \(as specified in the `web.xml` file\) to form the lookup name.

 <a name="concept_cyc_dqw_gn"/>

<!-- concept\_cyc\_dqw\_gn -->

## Using the Password Storage API

Below is a code example of how to use the API to set, get or delete passwords. These methods provide the option of assigning an alias to the password.

```
import javax.naming.InitialContext;
import javax.naming.NamingException;
 
import com.sap.cloud.security.password.PasswordStorage;
import com.sap.cloud.security.password.PasswordStorageException;
.......
 
   private PasswordStorage getPasswordStorage() throws NamingException {
    InitialContext ctx = new InitialContext();
    PasswordStorage passwordStorage = (PasswordStorage) ctx.lookup("java:comp/env/PasswordStorage");
    return passwordStorage;
  }
 
  private void setPassword(String alias, char[] password) throws PasswordStorageException, NamingException {
    PasswordStorage passwordStorage = getPasswordStorage();
    passwordStorage.setPassword(alias, password);
  }
 
  private char[] getPassword(String alias) throws PasswordStorageException, NamingException {
    PasswordStorage passwordStorage = getPasswordStorage();
    return passwordStorage.getPassword(alias);
  }
 
  private void deletePassword(String alias) throws PasswordStorageException, NamingException {
    PasswordStorage passwordStorage = getPasswordStorage();
    return passwordStorage.deletePassword(alias);
  }
```

> ### Note:  
> It is recommended to cache the obtained value, as reading of passwords is an expensive operation and involves several internal remote calls to central storage and audit infrastructure. As passwords are different for the different tenant the cache should be tenant aware. PasswordsStorage instance obtained via lookup can be cached and used by multiple threads.

 <a name="concept_u3b_xxd_hn"/>

<!-- concept\_u3b\_xxd\_hn -->

## Local Testing

When you run applications on SAP BTP local runtime, you can use a local implementation of the password storage API, but keep in mind that the passwords are not encrypted and stored in a local file. Therefore, for local testing, use only test passwords.

**Related Information**  


[Security Development](security-development-6fafbaa.md "This section describes how you can implement security in your applications.")

