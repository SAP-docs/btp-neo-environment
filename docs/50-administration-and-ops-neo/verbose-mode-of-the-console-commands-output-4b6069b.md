<!-- loio4b6069b765fd4b299fbdd1415901d3da -->

# Verbose Mode of the Console Commands Output

> ### Remember:  
> SAP Business Technology Platform, Neo environment will sunset on **December 31, 2028**, subject to terms of customer or partner contracts.
> 
> For more information, see SAP Note [3351844](https://launchpad.support.sap.com/#/notes/3351844).

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**



The console commands consist of:

-   Local code - executed inside a local JVM, which is started when the command is started.
-   Remote code - executed at back end \(generally, the REST API that was called by the local code\), which is started in a separate JVM on the cloud.

> ### Note:  
> The trace level for remote code cannot be changed.

For local code execution, a LOG4J library is used. It is easy to be configured and, by default, there is a configuration file located inside the commands class path, that is `.../tools/lib/cmd`.

For each command execution, two appenders are defined - one for the session and one for the console. They both define different files for all messages that are logged by the SAP infrastructure and by `apache.http`. By default, the console commands output is written in a number of log files. However, you are allowed to change the `log4j.properties` file, and define additional appenders or change the existing ones. If you want, for example, the full output to be printed in the console \(verbose mode\), or you want to see details from the execution of specific libraries \(partially verbose mode\), you need to adjust the LOG4J configuration file.

For more information on how to configure the LOG4J, see [https://logging.apache.org/](https://logging.apache.org/).

To adjust the level of a specific logger, you have to add `log4j.logger.<package> = <level>` in the code of the `log4j.properties` file.

For more information about the different levels, see [https://logging.apache.org/log4j/1.2/apidocs/org/apache/log4j/Level.html](https://logging.apache.org/log4j/1.2/apidocs/org/apache/log4j/Level.html)

In the file defined for the session, only loggers with level `ERROR` are logged. If you want, for example, to log debug information about the `apache.http` library, you have to change `log4j.category.org.apache.http=ERROR, session` to `log4j.category.org.apache.http=DEBUG, session`.



## Example

This example demonstrates how you can change the output of command execution so that it is printed in the console instead of collecting the information within log files. To do this, open your SDK folder and go to directory `/tools/lib/cmd`. Then, open the `log4j.properties` file and replace its content with the code below.

> ### Tip:  
> We recommend that you save the original content of the `log4j.properties` file. To switch back to the default settings, just revert the changes you did in the `log4j.properties` file.

```ini
##########
# Log levels
##########
 
log4j.rootLogger=INFO, console
 
log4j.additivity.rootLogger=false
 
log4j.category.com.sap = INFO, console
log4j.additivity.com.sap = false
log4j.category.org.apache.http = INFO, console
log4j.additivity.org.apache.http = false
log4j.category.org.apache.http.wire = INFO, console
log4j.additivity.org.apache.http.wire = false
 
##########
# System out console appender
##########
 
log4j.appender.console.Threshold=ALL
 
log4j.appender.console=org.apache.log4j.ConsoleAppender
log4j.appender.console.Target=System.out
 
log4j.appender.console.layout=org.apache.log4j.PatternLayout
log4j.appender.console.layout.ConversionPattern=%d %-5p [%t] %C: %m%n
 
log4j.appender.console.filter.1=org.apache.log4j.varia.StringMatchFilter
log4j.appender.console.filter.1.StringToMatch=>> Authorization: Basic
log4j.appender.console.filter.1.AcceptOnMatch=false
```

**Related Information**  


[Machine-Readable Command Output](https://help.sap.com/viewer/ea72206b834e4ace9cd834feed6c0e09/Cloud/en-US/b35e1e92ceb647daac49098b828dac92.html)

[Implementing Logging for Java Applications](https://help.sap.com/viewer/f88a032109f0429caea276fc6e3a95f9/Cloud/en-US/e6e8ccd3bb571014b6afdc54744eef4d.html "Configure logging and specify log level messages. Learn about the log rotation, the log retention, and the logging levels.") :arrow_upper_right:

