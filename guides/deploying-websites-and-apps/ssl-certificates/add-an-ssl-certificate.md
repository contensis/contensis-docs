To add an SSL certificate to your project, you’ll need to be a System Administrator or a member of a SSL Certificate Administrators group.

1.  Navigate to the *SSL certificates* listing screen by pressing **Settings** in the sidebar and selecting **SSL certificates** from the menu.
2.  Select **New certificate** from the toolbar. The *Add a certificate* window will open.
3.  A certificate is usually issued as a single or collection of `PEM` files, or as individual `.key`, `.crt` files. In practice, each certificate is listed in a file, using seperate blocks.

JavaScript

```
-----BEGIN PRIVATE KEY-----    

 //PRIVATE KEY
    
-----END PRIVATE KEY-----

-----BEGIN CERTIFICATE-----

 // CERTIFICATE
    
-----END CERTIFICATE-----

-----BEGIN CERTIFICATE-----
    
 // INTERMEDIATE(s)
    
-----END CERTIFICATE-----
```

4.  Copy each section in the file including in `——BEGIN xxxxxx———` and `———END XXXXX———` tags into the the Add a certificate window.
5.  Once completed, press **Verify certificate.**
6.  If verification is successful you can press **Install certificate**. A confirmation message will be displayed and your new certificate will be displayed in the listing.
7.  You'll need to enable the certificate once installed.

## Enable the certificate

To make the certificate active you'll need to enable it from the actions menu.

1.  Locate the certificate in the list.
2.  Open the actions menu for the certificate by pressing on the triple dot button.
3.  Select **Enable certificate** from the menu. A confirmation message will be displayed of the change of status.

## Disable an existing certificate

To disable a certificate you'll need to use the actions menu in the listing.

1.  Locate the certificate in the list.
2.  Open the actions menu for the certificate by pressing on the triple dot button.
3.  Select **Disable certificate** from the menu. A confirmation message will be displayed of the change of status.