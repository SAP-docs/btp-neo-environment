<!-- loio3225447dbcc8442794efab7c4b0d0abe -->

# Use a QR Code for Mobile Access

Use a QR code for easier copying of the OAuth authorization code on mobile devices.



## Context

When your account is configured for trust with a corporate identity provider \(IdP\), it is often impossible to connect to the IdP directly using a personal mobile device. The corporate IdP is often part of a protected corporate network, which does not allow personal devices to access it. To facilitate OAuth authentication on mobile devices, you can use the end user UI's QR code generation option. It provides as a scannable QR code the authorization code sent by the OAuth authorization server.



## Procedure

1.  In the Cockpit, choose the *Security* \> *OAuth* \> *Branding* section.

2.  Click the *End User UI* link. You are now opening the end user UI in a new browser window.

3.  Choose *Code*.

4.  Select the client from the list of registered clients for this user.

5.  Select the required scopes.

6.  Choose *Generate QR Code*.

7.  Use your mobile device to scan this QR code \(prerequisite: you have QR code scanning software installed\), and copy it to your device's clipboard.

8.  Paste the code from the clipboard to your mobile application \(prerequisite: your mobile application allows you to paste the authorization code from the clipboard and will send in this case the access token request directly to the OAuth authorization server\).

    ![](images/OAuth_QR_Code_4187982.png)


