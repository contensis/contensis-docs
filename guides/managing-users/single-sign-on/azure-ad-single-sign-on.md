## Overview

You can integrate your Azure Active Directory (Azure AD) instance to help manage seamless single sign-on for the members of your organisation.

The following articles outline the process for configuring Azure AD, and how to setup Contensis to use this new configuration. They also cover testing the integration between the two systems.

These articles assume you have access and permission to your Azure portal along with system administrator access to Contensis.

### Overview

***Note:*** *this article applies to app registrations created after October 2021(see [this link](https://docs.microsoft.com/en-us/azure/active-directory/develop/reference-breaking-changes#appid-uri-in-single-tenant-applications-will-require-use-of-default-scheme-or-verified-domains) for further details on Azure AD changes).*

To be able to register Contensis CMS with Azure, you will first need to complete the following actions on Azure:

1.  **Register a new application for each CMS instance**  
    Register new applications for each Contensis CMS instance that will be integrated with Azure. For example, if you have a live and development instance you will need to register two applications, one for the live CMS url and one for the development CMS url.
2.  **Update the application manifest**  
    Allows group integration and adds the application id url.
3.  **Update permissions**  
    Allows user integration.
4.  **Obtain relevant federation data for the CMS**  
    Obtaining credentials and discovery document data that is required to allow the Zengenti identity provider to federate with your registered Azure application.

### Registering a new application

Go to the [Azure portal](https://portal.azure.com/#home) and click ‘*Azure Active Directory*’ from the options in the left panel.

![](/image-library/resources-images/user-guides-images/01.x2f42a038.png?q=80&f=webp)

You will now be taken to the ‘*Azure Active Directory Overview*’ screen.

Click ‘*App Registrations*’ from the ‘*Manage*’ section.

![](/image-library/resources-images/user-guides-images/02.x6f10c295.png?q=80&f=webp)

You now have the option to add a new registration.

Click ‘*\+ New registration*’ in the toolbar.

![](/image-library/resources-images/user-guides-images/03.xccd990ef.png?q=80&f=webp)

You’ll be presented with a form allowing you to enter initial application registration information.

**Name**  
This is the display name for the registration in your Azure portal, and can be anything of your choosing.

**Supported Account Types**  
This defines the types of accounts the application grants permissions to.

**Redirect URI  
**This is not optional and is a requirement for the Zengenti identity provider. It should be entered in the following format:

https://<your cms domain>/authenticate/

After completion, the form should look similar to the following:

![](/image-library/resources-images/user-guides-images/04.x74cfee27.png?q=80&f=webp)

Click ‘*Register*’. The application is now registered.

### Update authentication options

The application needs to be updated to include additional authentication options.

Click ‘*Authentication*’ from the application overview and ensure *'Access tokens'* and *'ID tokens'* are selected in the **Implicit grant and hybrid flows** section:

![](/image-library/resources-images/user-guides-images/azuread-authentication.x9b125e33.png?q=80&f=webp)

### Update the application manifest

To allow the Zengenti identity provider to be able to identify itself, and process a user’s group membership, the application manifest must now be amended.

Click ‘*Manifest*’ from the application overview:

![](/image-library/resources-images/user-guides-images/05.x462e4ccd.png?q=80&f=webp)

Update the ‘*groupMembershipClaims*’ value to ‘*SecurityGroup*’.

Click ‘*Save*’.

![](/image-library/resources-images/user-guides-images/azuread-manifest.x8a5a2536.png?q=80&f=webp)

A message will display confirming that the manifest has been updated successfully.

![](/image-library/resources-images/user-guides-images/07.x62debb22.png?q=80&f=webp)

Click ‘*API permissions*’ and then click ‘*\+ Add a permission*’.

![](/image-library/resources-images/user-guides-images/08.xeb9b0b3b.png?q=80&f=webp)

Click ‘*Microsoft Graph*’ from the top.

![](/image-library/resources-images/user-guides-images/09.x08a83c08.png?q=80&f=webp)

Now add the following permissions:

1.  **Delegated permissions**
    
    -   Directory.Read.All
    -   User.Read
    -   openid
    -   profile
    
2.  **Application permissions**
    
    -   Directory.Read.All
    -   User.Read.All
    

To add these, click on the relevant permission type and copy/paste the permission as listed above into the search field, then check the permission as shown below:

![](/image-library/resources-images/user-guides-images/10.x81b4a55e.png?q=80&f=webp)

![](/image-library/resources-images/user-guides-images/11.xbdd80e01.png?q=80&f=webp)

![](/image-library/resources-images/user-guides-images/12.xb1e4c961.png?q=80&f=webp)

![](/image-library/resources-images/user-guides-images/13.x44d4b0d5.png?q=80&f=webp)

When the three permission options have been selected, click ‘*Add permissions*’.

This will take you back to the API permissions page, where a warning relating to changed permissions will be visible.

To allow the permissions to be available for the Zengenti identity provider, you must grant admin access. Click ‘*Grant admin consent*’ at the bottom of the page.

![](/image-library/resources-images/user-guides-images/14.x9aba73d5.png?q=80&f=webp)

A further warning will then display - click ‘*Yes*’.

![](/image-library/resources-images/user-guides-images/15.x96dfc6b4.png?q=80&f=webp)

A success message will display, together with details of the permissions granted.

![](/image-library/resources-images/user-guides-images/16.xd03b1ffd.png?q=80&f=webp)

### Setting up admin consent requests (optional)

If the user that will log in into Contensis CMS for the very first time after registration does not have Azure AD global admin permissions you need an additional step to enable admin consent requests.

Go to “Azure Active Directory” > "Enterprise applications*"* and on the left menu, there is a *'User settings'* entry that has an **Admin consent requests** section. This section needs to be enabled as follows and should have a user, group or role selected that will receive notifications for admin consent via email. The admin consent needs to be granted once per lifetime of the application.

![](/image-library/resources-images/user-guides-images/azuread-adminconsent.x31540427.PNG?q=80&f=webp)

#### Obtain relevant federation data for the CMS

The Zengenti identity provider requires the following information to federate with your Azure instance:

-   Metadata endpoint
-   Application id
-   Tenant id
-   Tenant name
-   Application key

#### Metadata endpoint

Go to “Azure Active Directory” > App Registrations

e.g. Home > Zengenti Ltd > App Registrations

Click ‘*Endpoints*’ in the top bar.

![](/image-library/resources-images/user-guides-images/17.x7b75f894.png?q=80&f=webp)

You will see a list of available application endpoints.

Copy the link for ‘*OpenID Connect metadata document*’

![](/image-library/resources-images/user-guides-images/capture.xf6b0e851.PNG?q=80&f=webp)

#### Application id

Click ‘*Overview*’ in the application options pane and then copy the ‘*Application (client) ID*’ which will be required when configuring Contensis to use your Azure AD instance.

![](/image-library/resources-images/user-guides-images/19.xbc6f1adb.png?q=80&f=webp)

#### Tenant id

In the ‘*Overview*’ screen, copy the '*Directory (tenant) ID*’ which will be required when configuring Contensis to use your Azure AD instance.

![](/image-library/resources-images/user-guides-images/19.xbc6f1adb.png?q=80&f=webp)

#### Tenant name

Select ‘*Azure Active Directory*’ from the panel on the left, and then ‘*Custom Domain Names*’. You can then copy the ‘Name’ listed as the ‘Primary’ - this is your tenant name and will be required when configuring Contensis to use your Azure AD instance.

![](/image-library/resources-images/user-guides-images/20.x117c57a4.png?q=80&f=webp)

#### Application key

In the application overview panel, click ‘*Certificates & secrets*’ and then click ‘*\+ New client secret*’.

![](/image-library/resources-images/user-guides-images/21.x71b2b94f.png?q=80&f=webp)

You will see a form for naming and choosing the lifespan of a key. Complete as appropriate for your requirements, then click ‘*Add*’.

![](/image-library/resources-images/user-guides-images/22.x2d0d4cdf.png?q=80&f=webp)

You will now need to copy the key as directed before navigating away from this screen. Click the ‘*Copy to clipboard*’ icon.

**Once you leave this screen or carry out any other action, you will no longer be able to retrieve this key value.**

![](/image-library/resources-images/user-guides-images/23.x68e7f644.png?q=80&f=webp)

You have now completed the registration of Contensis with Azure and are now ready to [configure Contensis to use Azure AD](https://www.contensis.com/help-and-docs/user-guides/user-management/single-sign-on/azure-ad-single-sign-on/configure-contensis-to-use-azure-ad).

### Overview

***Note:*** *this article applies to app registrations created before October 2021 or that have the Contensis CMS domain (e.g. cloud.contensis.com) verified in the Azure portal (see [this link](https://docs.microsoft.com/en-us/azure/active-directory/develop/reference-breaking-changes#appid-uri-in-single-tenant-applications-will-require-use-of-default-scheme-or-verified-domains) for further details).*

To be able to register Contensis CMS with Azure, you will first need to complete the following actions on Azure:

1.  **Register a new application for each CMS instance**  
    Register new applications for each Contensis CMS instance that will be integrated with Azure. For example, if you have a live and development instance you will need to register two applications, one for the live CMS url and one for the development CMS url.
2.  **Update the application manifest**  
    Allows group integration and adds the application id url.
3.  **Update permissions**  
    Allows user integration.
4.  **Obtain relevant federation data for the CMS**  
    Obtaining credentials and discovery document data that is required to allow the Zengenti identity provider to federate with your registered Azure application.

### Registering a new application

Go to the [Azure portal](https://portal.azure.com/#home) and click ‘*Azure Active Directory*’ from the options in the left panel.

![](/image-library/resources-images/user-guides-images/01.x2f42a038.png?q=80&f=webp)

You will now be taken to the ‘*Azure Active Directory Overview*’ screen.

Click ‘*App Registrations*’ from the ‘*Manage*’ section.

![](/image-library/resources-images/user-guides-images/02.x6f10c295.png?q=80&f=webp)

You now have the option to add a new registration.

Click ‘*\+ New registration*’ in the toolbar.

![](/image-library/resources-images/user-guides-images/03.xccd990ef.png?q=80&f=webp)

You’ll be presented with a form allowing you to enter initial application registration information.

**Name**  
This is the display name for the registration in your Azure portal, and can be anything of your choosing.

**Supported Account Types**  
This defines the types of accounts the application grants permissions to.

**Redirect URI  
**This is not optional and is a requirement for the Zengenti identity provider. It should be entered in the following format:

https://<your cms domain>/authenticate

After completion, the form should look similar to the following:

![](/image-library/resources-images/user-guides-images/04.x74cfee27.png?q=80&f=webp)

Click ‘*Register*’. The application is now registered.

### Update the application manifest

To allow the Zengenti identity provider to be able to identify itself, and process a user’s group membership, the application manifest must now be amended.

Click ‘*Manifest*’ from the application overview:

![](/image-library/resources-images/user-guides-images/05.x462e4ccd.png?q=80&f=webp)

Update the ‘*groupMembershipClaims*’ value to ‘*SecurityGroup*’ , then add the application id url in the form of ‘*https://<your domain>/authenticate*’, as shown below.

Click ‘*Save*’.

![](/image-library/resources-images/user-guides-images/06.x153c17ac.png?q=80&f=webp)

A message will display confirming that the manifest has been updated successfully.

![](/image-library/resources-images/user-guides-images/07.x62debb22.png?q=80&f=webp)

Click ‘*API permissions*’ and then click ‘*\+ Add a permission*’.

![](/image-library/resources-images/user-guides-images/08.xeb9b0b3b.png?q=80&f=webp)

Click ‘*Microsoft Graph*’ from the top.

![](/image-library/resources-images/user-guides-images/09.x08a83c08.png?q=80&f=webp)

Now add the following permissions:

1.  **Delegated permissions**
    
    -   Directory.Read.All
    -   User.Read
    
2.  **Application permissions**
    
    -   Directory.Read.All
    

To add these, click on the relevant permission type and copy/paste the permission as listed above into the search field, then check the permission as shown below:

![](/image-library/resources-images/user-guides-images/10.x81b4a55e.png?q=80&f=webp)

![](/image-library/resources-images/user-guides-images/11.xbdd80e01.png?q=80&f=webp)

![](/image-library/resources-images/user-guides-images/12.xb1e4c961.png?q=80&f=webp)

![](/image-library/resources-images/user-guides-images/13.x44d4b0d5.png?q=80&f=webp)

When the three permission options have been selected, click ‘*Add permissions*’.

This will take you back to the API permissions page, where a warning relating to changed permissions will be visible.

To allow the permissions to be available for the Zengenti identity provider, you must grant admin access. Click ‘*Grant admin consent*’ at the bottom of the page.

![](/image-library/resources-images/user-guides-images/14.x9aba73d5.png?q=80&f=webp)

A further warning will then display - click ‘*Yes*’.

![](/image-library/resources-images/user-guides-images/15.x96dfc6b4.png?q=80&f=webp)

A success message will display, together with details of the permissions granted.

![](/image-library/resources-images/user-guides-images/16.xd03b1ffd.png?q=80&f=webp)

### Obtain relevant federation data for the CMS

The Zengenti identity provider requires the following information to federate with your Azure instance:

-   Metadata endpoint
-   Application id
-   Tenant id
-   Tenant name
-   Application key

#### Metadata endpoint

Go to “Azure Active Directory” > App Registrations

e.g. Home > Zengenti Ltd > App Registrations

Click ‘*Endpoints*’ in the top bar.

![](/image-library/resources-images/user-guides-images/17.x7b75f894.png?q=80&f=webp)

You will see a list of available application endpoints.

Copy the link for ‘*Federation metadata document*’

![](/image-library/resources-images/user-guides-images/18.x2a0ce83e.png?q=80&f=webp)

#### Application id

Click ‘*Overview*’ in the application options pane and then copy the ‘*Application (client) ID*’ which will be required when configuring Contensis to use your Azure AD instance.

![](/image-library/resources-images/user-guides-images/19.xbc6f1adb.png?q=80&f=webp)

#### Tenant id

In the ‘*Overview*’ screen, copy the '*Directory (tenant) ID*’ which will be required when configuring Contensis to use your Azure AD instance.

![](/image-library/resources-images/user-guides-images/19.xbc6f1adb.png?q=80&f=webp)

#### Tenant name

Select ‘*Azure Active Directory*’ from the panel on the left, and then ‘*Custom Domain Names*’. You can then copy the ‘Name’ listed as the ‘Primary’ - this is your tenant name and will be required when configuring Contensis to use your Azure AD instance.

![](/image-library/resources-images/user-guides-images/20.x117c57a4.png?q=80&f=webp)

#### Application key

In the application overview panel, click ‘*Certificates & secrets*’ and then click ‘*\+ New client secret*’.

![](/image-library/resources-images/user-guides-images/21.x71b2b94f.png?q=80&f=webp)

You will see a form for naming and choosing the lifespan of a key. Complete as appropriate for your requirements, then click ‘*Add*’.

![](/image-library/resources-images/user-guides-images/22.x2d0d4cdf.png?q=80&f=webp)

You will now need to copy the key as directed before navigating away from this screen. Click the ‘*Copy to clipboard*’ icon.

**Once you leave this screen or carry out any other action, you will no longer be able to retrieve this key value.**

![](/image-library/resources-images/user-guides-images/23.x68e7f644.png?q=80&f=webp)

You have now completed the registration of Contensis with Azure and are now ready to [configure Contensis to use Azure AD](https://www.contensis.com/help-and-docs/user-guides/user-management/single-sign-on/azure-ad-single-sign-on/configure-contensis-to-use-azure-ad).

## Configure Contensis to use Azure AD

1.  With your [Contensis application registered in Azure AD](https://www.contensis.com/help-and-docs/user-guides/environment/single-sign-on/azure-ad-single-sign-on/register-contensis-with-azure-ad)**,** the next step is to login to Contensis and configure the Azure AD integration.
    
    1.  Login to Contensis using an administrative account.
    2.  Navigate to the *Management Console* and select **Global Settings**, you need to enter the following settings:
    3.  Select **Azure Active Directory**, followed by **App Registrations** and then select **Endpoints** from the top toolbar.
    

![](/image-library/resources-images/user-guides-images/17a-settings-endpoint.xa1f279e8.png?q=80&f=webp)

2.  Update the *WSFederation\_MetadataEndpoint **global setting**.* The value for this is different depending on whether you are using the current Azure AD configuration (*WSFederation\_Type*\=3) or the legacy configuration (*WSFederation\_Type* =2):
    
    -   Legacy Azure AD configuration (*WSFederation\_Type* =2): Copy the *Federation Metadata Document* address from the textbox.
    -   Current Azure AD configuration (*WSFederation\_Type* =3): Copy the *OpenID Connect metadata* document address from the textbox
    

![](/image-library/resources-images/user-guides-images/17b-settings-endpoint-copy-setting.xf03615bd.png?q=80&f=webp)

![](/image-library/resources-images/user-guides-images/metadata-endpoint.x5566624d.png?q=80&f=webp)

### WsFederation\_AzureTenantID

This needs to be set to your Azure AD tenant ID. This can be found by following these steps:

-   Select Azure Active Directory, followed by Properties. Your tenant ID is the same as your Directory ID. Enter this in the *WSFederation\_TenantID* global setting.

![](/image-library/resources-images/user-guides-images/14-settings-directory-id.x3a56c32a.png?q=80&f=webp)

### WsFederation\_AzureTenantName

This needs to be set to your Azure AD tenant name. This can be found by following these steps:

-   Select **Azure Active Directory**, followed by **Custom domain names**. Your tenant name is the name of your primary domain. Enter this in the *WSFederation\_TenantName* global setting.

![](/image-library/resources-images/user-guides-images/16-settings-tenant-name.xf5b3acc1.png?q=80&f=webp)

### WsFederation\_AzureApplicationID

This needs to be set to the application ID of the registered Contensis app in Azure. This can be found by following these steps:

-   Select **Azure Active Directory**, followed by **App registrations** then select the Contensis application. Your application ID is listed on the application overview. Enter this in the *WSFederation\_ApplicationID* global setting.

![](/image-library/resources-images/user-guides-images/15-settings-application-id.xc62d1e46.png?q=80&f=webp)

### WsFederation\_AzureApplicationKey

1.  Navigate to your application and click **All settings** and then select **Keys** from the secondary menu.

![](/image-library/resources-images/user-guides-images/13-keys.xb461345c.png?q=80&f=webp)

2.  Enter a *description*, choose an *expiration* and then click **Save**.

Once you navigate away from this screen you will not be able to retrieve the key again. In the event that you lose the key value then you will need to delete the key and add a new one.

![](/image-library/resources-images/user-guides-images/13-copy-key.xfcaa3e52.png?q=80&f=webp)

3.  Enter the value of the key into the *WSFederation* **global setting**.

### WSFederation\_Type

This needs to be set to 2 for Azure AD accounts created before October 2021, and to 3 for any created later.

### Final step

Our support team will need to apply these changes for you. Please [raise a help desk ticket](https://www.contensis.com/help-and-docs/help-desk) to arrange this.

Once you have [registered Contensis with Azure AD](https://www.contensis.com/help-and-docs/user-guides/environment/single-sign-on/azure-ad-single-sign-on/register-contensis-with-azure-ad) and set up [Azure AD in Contensis](https://www.contensis.com/help-and-docs/user-guides/environment/single-sign-on/azure-ad-single-sign-on/configure-contensis-to-use-azure-ad), you should see a new *Sign in with Azure AD* button on the Contensis login screen.

![](/image-library/resources-images/user-guides-images/adfs-contensis-login3.x3fc89e4b.png?q=80&f=webp)

Press **Sign in with Azure AD** to be redirected to your Azure AD logon screen.

![](/image-library/resources-images/user-guides-images/azure-ad-login-2.xd4175c89.png?q=80&f=webp)

2.  Enter your email and press **Next**. Follow the on-screen instructions and you will be logged into Contensis.

If this is the first time a user has logged in, a user will be created in Contensis with a username which matches their AD username. If a Contensis user already exists with the same user name, then the user will be converted to an AD user. No permissions or group assignments will be lost.

All users created via an Azure AD login are added to a system group called *AD Users*, this enables you to give the *AD Users* some default permissions.

f you are having problems logging in using Azure AD then here are some things you might want to check are configured correctly and a debug step you could try.

## CMS URL

1.  In the *Management Console* navigate to **Global Settings**.
2.  Look up the ContensisGuiURL setting and check if the *Setting Value* has https:// defined at the start of it (non-https will not work).

## Contensis registration with Azure AD

Has Contensis been registered correctly with Azure AD? Double check that all steps have been carried out correctly in the [Register Contensis with Azure AD](https://www.contensis.com/help-and-docs/user-guides/environment/single-sign-on/azure-ad-single-sign-on/register-contensis-with-azure-ad) article.

## CMS settings

1.  In the *Management Console* navigate to **Global Settings** and make sure that all settings have been set correctly by following the [Configure Contensis to use AD FS](https://www.contensis.com/help-and-docs/user-guides/environment/single-sign-on/azure-ad-single-sign-on/configure-contensis-to-use-azure-ad) article.
2.  Double check that you can access the metadata endpoint specified in the global setting *WsFederation\_MetadataEndpoint.* To do this you can logon to the CMS server and run the following command in PowerShell:

Invoke-WebRequest https://adfs.contensis.com/FederationMetadata/2007-06/FederationMetadata.xml - UseBasicParsing

If the metadata endpoint is configured correctly you should get a *StatusCode* of 200 and the *Content* will start with <EntityDescriptor....

## Machine.config machinekey validation

1.  Open the machine.config file on your CMS server. It can be found in c:\\Windows\\Microsoft.NET\\Framework64\\v4.0.30319\\Config
2.  Search for the following <machineKey>, you will see something like:

<machineKey validationKey="E1D4A7ACE716CC17B9BE3F1794AB117E7CB771B878253727" decryptionKey="E8969B07BF46F3FF659E008495F1EA5163EBDC0E50B6024E" validation="SHA1"/>

Make sure that the validation property is set to SHA1 and not anything else. If it is set to something else, change it and then restart IIS.

## Debug using verbose logging

Follow the steps below to setup tracing on IdentityServer and then attempt to login using Azure AD or logout. Any issues should be seen in the logs.

### Set up tracing on IdentityServer

1.  Add the xml above to the web.config file for the CMS instance, change the Contensis\_DebugInfoLevel to *Debug* in the web.config.
2.  Ensure that the CMS has access to the directory specified in the initializeData setting.
3.  Save web.config.