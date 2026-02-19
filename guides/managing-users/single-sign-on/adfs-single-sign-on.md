## Overview

You can integrate your Active Directory Federation Services (AD FS) instance to help manage seamless single sign-on for the members of your organisation.

The following articles outline the process for configuring AD FS on your Windows server, and how to setup Contensis to use this new configuration. They also cover testing the integration between the two systems.

These articles assume you have access and permission to your AD FS server along with system administrator access to Contensis.

### Requirements

-   An active directory instance where all users have an email address attribute.
-   A server running Microsoft Server 2012 R2, 2012 or 2008 with AD FS installed. This is covered in the following [MSDN article](https://msdn.microsoft.com/en-us/library/gg188612.aspx): *Deploy and configure AD FS*.
-   An instance of Contensis installed which can access your AD FS login page.
-   Your Contensis installation must be accessible on https and use a valid SSL certificate.

## Assigning emails to federated CMS users

The following describes the order of precedence when assigning an email to a user after federated login, such as via AD FS or Azure AD.

### AD FS

The value of the email claim is assigned.

### Azure AD

#### WsFederation\_Azure\_PrioritiseUPNForEmailAddress = 0

1.  Use MicrosoftGraph.User.Mail value, if present.
2.  Use first of MicrosoftGraph.User.OtherMails addresses, if present.
3.  Use the UPN, if it is already in an email format.
4.  Use the username constructed from UPN, if present.

The constructed username will be in the form of an email address.

#### WsFederation\_Azure\_PrioritiseUPNForEmailAddress = 1

1.  Use the UPN, if it is already in an email format.
2.  Use 'email' claim, if present.
3.  Use MicrosoftGraph.User.Mail value, if present.
4.  Use first of MicrosoftGraph.User.OtherMails addresses, if present.
5.  Use the username constructed from UPN, if present.

The constructed username will be in the form of an email address.

With the appropriate trusts and claims setup on your [AD FS server](#configure-your-ad-fs-server), the next step is to login to Contensis and turn on AD FS integration.

1.  Login to Contensis using an administrative account.
2.  Navigate to the *Management Console* and select **Global Settings**.
3.  Set the *WsFederation\_MetadataEndpoint* setting to your AD FS URL with /FederationMetadata/2007-06/FederationMetadata.xml appended.  
    e.g. https://adfs.customername.com/FederationMetadata/2007-06/FederationMetadata.xml.

**Note**: This must be accessible from your Contensis server.

4.  Set the *WsFederation\_Type* setting to 1.
5.  Once you have completed the above steps. Please [raise a help desk ticket](https://www.contensis.com/help-and-docs/help-desk) as our support team will need to restart the application.

This article outlines the process of configuring your AD FS services on your Windows server to add the necessary trusts and claims for Contensis to integrate with your organisations single sign-on service.

### Add the relying party trusts

1.  Open the AD FS Management console, click **Add Relying Party Trust** in the Actions pane and press **Start** on the wizard introduction page.

![](/image-library/resources-images/user-guides-images/adfs-01.x5f4e8734.png?q=80&f=webp)

2.  Select **Enter data about the relying party manually**.

![](/image-library/resources-images/user-guides-images/adfs-02.xf4f45398.png?q=80&f=webp)

3.  Enter a *Display name*, e.g. Contensis and press **Next**.

![](/image-library/resources-images/user-guides-images/adfs-03.x1530ec01.png?q=80&f=webp)

4.  Select **AD FS Profile**.

![](/image-library/resources-images/user-guides-images/adfs-04.x887ad93a.png?q=80&f=webp)

5.  Skip the *Configure Certificate* step by pressing **Next** (it’s not supported by Contensis).

![](/image-library/resources-images/user-guides-images/adfs-05.xc3e4b323.png?q=80&f=webp)

6.  Select **Enable support for the WS-Federation Passive protocol** and enter your CMS address with the addition of */authenticate/* on the end and press **Next**.  
    e.g. https://cms-customername.cloud.contensis.com/authenticate/

**Please make sure you have the trailing end slash as without it the AD FS integration will not work**

**Note**: Contensis must be available on https, non-https will not work.

![](/image-library/resources-images/user-guides-images/adfs-06-new.xd2561b41.png?q=80&f=webp)

7.  Double check the CMS address is correct in the Relying party trust identifiers and then click **Next**.

![](/image-library/resources-images/user-guides-images/adfs-07-new.x2d908453.png?q=80&f=webp)

8.  Leave the default option of *I do not want to configure multi-factor authentication settings for this relying party trust at this time* selected.If you wish to configure multi-factor authentication select the second option. Multi-factor authentication is outside the scope of this article.

![](/image-library/resources-images/user-guides-images/adfs-09.x848fb1a5.png?q=80&f=webp)

9.  Select **Permit all users to access this relying party** and press **Next** if you want to allow all active directory users to login to Contensis. Alternatively select *Deny all users access this relying party* if you want to allow specific users later.

![](/image-library/resources-images/user-guides-images/adfs-10.xa540d0a4.png?q=80&f=webp)

10.  You don’t need to change anything in the *Ready to Add Trust* step. Press **Next**.

![](/image-library/resources-images/user-guides-images/adfs-11.x73eedca5.png?q=80&f=webp)

11.  Select the *Open the Edit Claim rules dialog for this relying party trust when the wizard closes* checkbox and press **Close**.

![](/image-library/resources-images/user-guides-images/adfs-12.xaa48a39b.png?q=80&f=webp)

### Configure claim rules

1.  The *Edit Claim Rules* window should open automatically after adding the relying party trust. Press **Add Rule…** to create a new rule.

![](/image-library/resources-images/user-guides-images/adfs-13.x691f5ef8.png?q=80&f=webp)

2.  Select **Send LDAP Attributes as Claims** from the *Claim rule template list*.

![](/image-library/resources-images/user-guides-images/adfs-14.xad6dd137.png?q=80&f=webp)

1.  Enter a Claim rule name e.g. Contensis claims
2.  Select Active Directory as the Attribute store
3.  As a minimum map the following LDAP attributes outlined in the table and press **Next**.

LDAP attribute

Outgoing claim type

User-Principal-Name

UPN

E-Mail-Addresses

E-Mail Address

SAM-Account-Name

Name

SAM-Account-Name

Name ID

![](/image-library/resources-images/user-guides-images/adfs-15.x842bbd97.png?q=80&f=webp)

If you want to populate the user’s first name and surname, you can also map the following LDAP attributes.

LDAP attribute

Outgoing claim type

Given-Name

Given-Name

Surname

Surname

You can also configure Contensis to automatically create groups which users are members of when the user first logs in. To enable this you need to map the following LDAP attribute.

LDAP attribute

Outgoing claim type

Is-Member-Of-DL

Group

6.  You’ll now see the claim listed. Press Add Rule… to add another claim

![](/image-library/resources-images/user-guides-images/adfs-16.x9ce204f0.png?q=80&f=webp)

You can continue to run the AD synchronisation feature alongside an AD FS integration. If you are running the sync then users and groups will be created within Contensis as normal and any AD FS users will be updated and moved into their relevant groups.

If you are running the AD Synchronisation and you have the global setting DirectoryServices\_DeleteInvalidUsersAndGroups set to true then AD FS users will be deleted if they aren’t a member of the groups being synchronised.

It is recommended that all users allowed to log in via AD FS are included in the groups which are being synchronised via the AD synchronisation feature.

## Test single sign-on in Contensis

1.  Once you have [configured](#configure-your-ad-fs-server) your AD FS server and set up [AD FS in Contensis](#configure-contensis-to-use-ad-fs), you should see a new **Sign in with AD FS** button on the Contensis login screen.

![](/image-library/resources-images/user-guides-images/adfs-17.x0c6c5af8.png?q=80&f=webp)

2.  Press **Sign in with AD FS** to be redirected to your AD FS logon screen.

![](/image-library/resources-images/user-guides-images/adfs-18.x4db03723.png?q=80&f=webp)

3.  Enter your username and password and press **Sign in**. You will be logged into Contensis.

If this is the first time a user has logged in, a user will be created in Contensis with a username which matches their AD username. If a Contensis user already exists with the same user name, then the user will be converted to an AD FS user. No permissions or group assignments will be lost.

All users created via an AD FS login are added to a system group called *AD Users*, this enables you to give the *AD Users* some default permissions.

If you are having AD FS login problems then here are some things you might want to check are configured correctly and a debug step you could try.

### CMS URL

1.  In the *Management Console* navigate to **Global Settings**.
2.  Look up the ContensisGuiURL setting and check if the *Setting Value* has https:// defined at the start of it (non-https will not work).

### AD FS server configuration

Has the AD FS server been [configured correctly](#configure-your-ad-fs-server) Check this common cause of login problems very carefully - are all the necessary trusts and claims for Contensis present and configured correctly?

### CMS settings

1.  In the *Management Console* navigate to **Global Settings**:  
    The **ADFS\_Enabled** *global setting* should be set to 1.  
    The **ADFS\_MetadataEndpoint** *global setting* should have the link to the metadata endpoint on your AD FS server. This will be in the following format:  
    https://adfs.contensis.com/FederationMetadata/2007-06/FederationMetadata.xml
2.  Double check that you can access this from the CMS server. To do this you can logon to the server and run the following command in PowerShell:

Invoke-WebRequest https://adfs.contensis.com/FederationMetadata/2007-06/FederationMetadata.xml - UseBasicParsing

If the metadata endpoint is configured correctly you should get a *StatusCode* of 200 and the *Content* will start with <EntityDescriptor....

### Machine.config machinekey validation

1.  Open the machine.config file on your CMS server. It can be found in c:\\Windows\\Microsoft.NET\\Framework64\\v4.0.30319\\Config
2.  Search for the following <machineKey>, you will see something like:

<machineKey validationKey="E1D4A7ACE716CC17B9BE3F1794AB117E7CB771B878253727" decryptionKey="E8969B07BF46F3FF659E008495F1EA5163EBDC0E50B6024E" validation="SHA1"/>

Make sure that the validation property is set to SHA1 and not anything else. If it is set to something else, change it and then restart IIS.

### Debug using verbose logging

Follow the steps below to setup tracing on IdentityServer and then attempt to login using ADFS or logout. Any issues should be seen in the logs.

#### Set up tracing on IdentityServer

1.  Add the xml above to the web.config file for the CMS instance, change the Contensis\_DebugInfoLevel to *Debug* in the web.config.
2.  Ensure that the CMS has access to the directory specified in the initializeData setting.
3.  Save web.config.