<!-- loio38144cd12fcc44249e7b2c4584f46045 -->

# Using the Keystore Service for Client Side HTTPS Connections



<a name="loio38144cd12fcc44249e7b2c4584f46045__prereq_N10011_N1000E_N10001"/>

## Prerequisites

> ### Tip:  
> **This documentation refers to SAP Business Technology Platform, Neo environment. If you are looking for documentation about other environments, see [SAP Business Technology Platform](https://help.sap.com/viewer/65de2977205c403bbc107264b8eccf4b/Cloud/en-US/6a2c1ab5a31b4ed9a2ce17a5329e1dd8.html "SAP Business Technology Platform (SAP BTP) is an integrated offering comprised of four technology portfolios: database and data management, application development and integration, analytics, and intelligent technologies. The platform offers users the ability to turn data into business value, compose end-to-end business processes, and build and extend SAP applications quickly.") :arrow_upper_right:.**

-   You have imported the Hello World sample in the Neo SDK. For more information, see [Using Samples](../30-development-neo/using-samples-937ce0d.md).
-   You have an HTTPS server hosting a resource which you would like to access in your application.
-   You have prepared the required key material as *.jks* files in the local file system.

    > ### Note:  
    > File `client.jks` contains a client identity key pair trusted by the HTTPS server, and `cacerts.jks` contains all issuer certificates for the HTTPS server. The files are created with the *keytool* from the standard JDK distribution. For more information, see [Key and Certificate Management Tool](http://docs.oracle.com/javase/6/docs/technotes/tools/windows/keytool.html).




<a name="loio38144cd12fcc44249e7b2c4584f46045__context_N1004E_N1000E_N10001"/>

## Context

This procedure describes how to extend the HelloWorld Web application to use Keystore Service. It includes making an SSL connection to an external HTTPS server by using the JDK and Apache HTTP Client.

You test and run the application on your local server and on SAP BTP.

 <a name="task_cxv_x4d_vp"/>

<!-- task\_cxv\_x4d\_vp -->

## Using javax.net.ssl Framework



<a name="task_cxv_x4d_vp__steps_fjf_kpd_vp"/>

## Procedure

1.  Declare a Keystore Service Resource Reference.

    To enable the look-up of the Keystore Service through JNDI, you need to add a resource reference entry to the `web.xml` descriptor.

    1.  In the application archive, open the `HelloWorld/WebContent/WEB-INF/web.xml` file, and insert the following content:

        ```
        <resource-ref>
        	<res-ref-name>KeyStoreService</res-ref-name>
        	<res-type>com.sap.cloud.crypto.keystore.api.KeyStoreService</res-type>
        </resource-ref>
        ```

    2.  Save the file.


2.  Create a new Servlet.

    1.  In a Servlet class, use Keystore service. For example, use the following source code:

        ```
        package com.sap.cloud.sample.keystoreservice;
        
        import java.io.BufferedReader;
        import java.io.BufferedWriter;
        import java.io.IOException;
        import java.io.InputStreamReader;
        import java.io.OutputStreamWriter;
        import java.io.PrintWriter;
        import java.security.KeyStore;
        
        import javax.naming.Context;
        import javax.naming.InitialContext;
        import javax.naming.NamingException;
        import javax.net.ssl.KeyManager;
        import javax.net.ssl.KeyManagerFactory;
        import javax.net.ssl.SSLContext;
        import javax.net.ssl.SSLSocket;
        import javax.net.ssl.SSLSocketFactory;
        import javax.net.ssl.TrustManager;
        import javax.net.ssl.TrustManagerFactory;
        import javax.servlet.ServletException;
        import javax.servlet.http.HttpServlet;
        import javax.servlet.http.HttpServletRequest;
        import javax.servlet.http.HttpServletResponse;
        
        import com.sap.cloud.crypto.keystore.api.KeyStoreService;
        
        
        public class SSLExampleServlet extends HttpServlet {
           private static final long serialVersionUID = 1L;
        
           /**
            * @see HttpServlet#doGet(HttpServletRequest request, HttpServletResponse response)
            */
           protected void doGet(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
        
             // get Keystore Service
             KeyStoreService keystoreService;
             try {
               Context context = new InitialContext();
               keystoreService = (KeyStoreService) context.lookup("java:comp/env/KeyStoreService");
             } catch (NamingException e) {
               response.getWriter().println("Error:<br><pre>");
               e.printStackTrace(response.getWriter());
               response.getWriter().println("</pre>");
               throw new ServletException(e);
             }
        
             String host = request.getParameter("host");
             if (host == null || (host = host.trim()).isEmpty()) {
               response.getWriter().println("Host is not specified");
               return;
             }
             String port = request.getParameter("port");
             if (port == null || (port = port.trim()).isEmpty()) {
               port = "443";
             }
             String path = request.getParameter("path");
             if (path == null || (path = path.trim()).isEmpty()) {
               path = "/";
             }
             String clientKeystoreName = "client";
            
             String clientKeystorePassword = request.getParameter("client.keystore.password");
             if (clientKeystorePassword == null || (clientKeystorePassword = clientKeystorePassword.trim()).isEmpty()) {
               response.getWriter().println("Password for client keystore is not specified");
               return;
             }
             String trustedCAKeystoreName = "cacerts";
        
            // get a named keystores with password for integrity check
             KeyStore clientKeystore;
             try {
               clientKeystore = keystoreService.getKeyStore(clientKeystoreName, clientKeystorePassword.toCharArray());
             } catch (Exception e) {
               response.getWriter().println("Client keystore is not available: " + e);
               return;
             } 
        
             // get a named keystore without integrity check
             KeyStore trustedCAKeystore;
             try {
               trustedCAKeystore = keystoreService.getKeyStore(trustedCAKeystoreName, null);
             } catch (Exception e) {
               response.getWriter().println("Trusted CAs keystore is not available" + e);
               return;
             }  
           
          callHTTPSServer(response, host, port, path, clientKeystorePassword, clientKeystore, trustedCAKeystore);
        }
        
         private void callHTTPSServer(HttpServletResponse response, 
                                      String host, 
                                      String port, 
                                      String path, 
                                      String clientKeystorePassword, 
                                      KeyStore clientKeystore, 
                                      KeyStore trustedCAKeystore) throws IOException {
           try {
             KeyManagerFactory kmf = KeyManagerFactory.getInstance(KeyManagerFactory.getDefaultAlgorithm());
             kmf.init(clientKeystore, clientKeystorePassword.toCharArray());
        
             KeyManager[] keyManagers = kmf.getKeyManagers();
             TrustManagerFactory tmf = TrustManagerFactory.getInstance(TrustManagerFactory.getDefaultAlgorithm());
             tmf.init(trustedCAKeystore);
        
             TrustManager[] trustManagers = tmf.getTrustManagers();
             SSLContext sslContext = SSLContext.getInstance("TLS");
             sslContext.init(keyManagers, trustManagers, null);
        
             SSLSocketFactory factory = sslContext.getSocketFactory();
        
             SSLSocket socket = (SSLSocket)factory.createSocket(host, Integer.parseInt(port));
             socket.startHandshake();
        
             PrintWriter out = new PrintWriter(new BufferedWriter(new OutputStreamWriter(socket.getOutputStream())));
             out.println("GET " + path + " HTTP/1.0");
             out.println();
             out.flush();
        
             if (out.checkError()) {
               response.getWriter().println("Error durring request sending");
             }
        
             BufferedReader in = new BufferedReader(new InputStreamReader(socket.getInputStream()));
             String inputLine;
             while ((inputLine = in.readLine()) != null) {
               response.getWriter().println(inputLine);
             }
        
             in.close();
             out.close();
             socket.close();
           } catch (Exception e) {
             response.getWriter().println("Error:<br><pre>");
             e.printStackTrace(response.getWriter());
             response.getWriter().println("</pre>");
           } finally {
             response.getWriter();
           }
         } 
        }
        ```

    2.  Save the Java code and make sure that the project compiles without errors.


3.  Deploy and Test the Web Application

    -   Local Server Configuration of the Keystore
    -   Cloud Configuration of the Keystore


 <a name="task_nsl_y4d_vp"/>

<!-- task\_nsl\_y4d\_vp -->

## Using Apache HTTP Client



<a name="task_nsl_y4d_vp__steps_nyd_5pd_vp"/>

## Procedure

1.  Add the required *.jar* files of the Apache HTTP Client \(version 4.2 or higher\) to the build path of your project.

2.  Add the following imports:

    ```
    import org.apache.http.HttpEntity;
    import org.apache.http.HttpResponse;
    import org.apache.http.client.methods.HttpGet;
    import org.apache.http.conn.scheme.Scheme;
    import org.apache.http.conn.scheme.SchemeSocketFactory;
    import org.apache.http.conn.ssl.SSLSocketFactory;
    import org.apache.http.impl.client.DefaultHttpClient;
    import org.apache.http.util.EntityUtils;
    ```

3.  Replace `callHTTPSServer()` method with the one using Apache HTTP client.

    ```
    private void callHTTPSServer(HttpServletResponse response, 
                                 String host, 
                                 String port, 
                                 String path, 
                                 String clientKeystorePassword, 
                                 KeyStore clientKeystore, 
                                 KeyStore trustedCAKeystore) throws IOException, ServletException {
      try {    
        SchemeSocketFactory socketFactory = new SSLSocketFactory(clientKeystore, clientKeystorePassword, trustedCAKeystore);
        Scheme sch = new Scheme("https", Integer.parseInt(port), socketFactory);
        DefaultHttpClient httpclient = new DefaultHttpClient();
        httpclient.getConnectionManager().getSchemeRegistry().register(sch);
    
        HttpGet httpget = new HttpGet("https://" + host + path);
    
        HttpResponse resp = httpclient.execute(httpget);
        HttpEntity entity = resp.getEntity();
    
        BufferedReader in = new BufferedReader(new InputStreamReader(entity.getContent()));
        String inputLine;
        while ((inputLine = in.readLine()) != null) {
          response.getWriter().println(inputLine);
        }
        EntityUtils.consume(entity);
      } catch (Exception e) {
        response.getWriter().println("error: " + e);
        throw new ServletException(e);
      } finally {
        response.getWriter().flush();
      }
    }
    ```


**Related Information**  


[Configure Keystore on Local Server](configure-keystore-on-local-server-a0fa997.md)

[Configure Keystore on Cloud](configure-keystore-on-cloud-b3ffae7.md)

