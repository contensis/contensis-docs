## Overview

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

## Registering a new application

Go to the [Azure portal](https://portal.azure.com/#home) and click ‘*App registrations*’.

![](/image-library/resources-images/user-guides-images/1-app-registrations-step1.xd5042775.png?q=80&f=webp)

You now have the option to add a new registration.

Click ‘*\+ New registration*’ in the toolbar.

![](/image-library/resources-images/user-guides-images/2-add-new-app.xc0a11d39.png?q=80&f=webp)

You’ll be presented with a form allowing you to enter initial application registration information.

**Name**  
This is the display name for the registration in your Azure portal, and can be anything of your choosing.

**Supported Account Types**  
This defines the types of accounts the application grants permissions to.

**Redirect URI  
**This is not optional and is a requirement for the Zengenti identity provider. It should be entered in the following format:

https://<your cms domain>/authenticate/

After completion, the form should look similar to the following:

![](/image-library/resources-images/user-guides-images/3-initial-reg-form.x2355d810.png?q=80&f=webp)

Click ‘*Register*’. The application is now registered.

## Update authentication options

The application needs to be updated to include additional authentication options.

Click ‘*Authentication*’ from the application overview and ensure *'Access tokens'* and *'ID tokens'* are selected in the **Implicit grant and hybrid flows** section:

![](/image-library/resources-images/user-guides-images/4-tokens1.x1eb93138.png?q=80&f=webp)

Edit Azure AD authentication options

## Update the application manifest

To allow the Zengenti identity provider to be able to identify itself, and process a user’s group membership, the application manifest must now be amended.

Click ‘*Manifest*’ from the application overview:

![](/image-library/resources-images/user-guides-images/5-select-manifest.x2a72ad04.png?q=80&f=webp)

Update the ‘*groupMembershipClaims*’ value to ‘*SecurityGroup*’.

Click ‘*Save*’.

![Edit Azure AD manifest](https://www.contensis.com/image-library/resources-images/user-guides-images/azuread-manifest.x8a5a2536.png?q=80&f=webp)

Edit Azure AD manifest

A message will display confirming that the manifest has been updated successfully.

![](/image-library/resources-images/user-guides-images/6-app-permissions.xeea78a54.png?q=80&f=webp)

Click ‘*API permissions*’ and then click ‘*\+ Add a permission*’.

![](/image-library/resources-images/user-guides-images/7-add-permissions.x0cd110a9.png?q=80&f=webp)

Click ‘*Microsoft Graph*’ from the top.

![](/image-library/resources-images/user-guides-images/7a-add-permissions-select-ms-graph.x5b2a79b0.png?q=80&f=webp)

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

![](/image-library/resources-images/user-guides-images/7b-add-permissions-delegated.xa495f1ee.png?q=80&f=webp)

![](/image-library/resources-images/user-guides-images/7c-add-permissions-directory-read-all.x140e8dda.png?q=80&f=webp)

![](/image-library/resources-images/user-guides-images/7d-add-permissions-user-read.x8c98b1a5.png?q=80&f=webp)

![](/image-library/resources-images/user-guides-images/7e-add-permissions-directory-app-read-all.x7f781e87.png?q=80&f=webp)

When the three permission options have been selected, click ‘*Add permissions*’.

This will take you back to the API permissions page, where a warning relating to changed permissions will be visible.

To allow the permissions to be available for the Zengenti identity provider, you must grant admin access. Click ‘*Grant admin consent*’ at the bottom of the page.

![](/image-library/resources-images/user-guides-images/7f-grant-permissions1.x63b9e56f.png?q=80&f=webp)

A further warning will then display - click ‘*Yes*’.

![](/image-library/resources-images/user-guides-images/7g-grant-permissions.xdb742f37.png?q=80&f=webp)

A success message will display, together with details of the permissions granted.

![](/image-library/resources-images/user-guides-images/7h-grant-permissions-complete.x4d586db5.png?q=80&f=webp)

## Obtain relevant federation data for the CMS

The Zengenti identity provider requires the following information to federate with your Azure instance:

-   Metadata endpoint
-   Application id
-   Tenant id
-   Tenant name
-   Application key

### Metadata endpoint

Go to “Azure Active Directory” > App Registrations

e.g. Home > Zengenti Ltd > App Registrations

Click ‘*Endpoints*’ in the top bar.

![](/image-library/resources-images/user-guides-images/8-endpoints.x6a5c71ec.png?q=80&f=webp)

You will see a list of available application endpoints.

Copy the link for ‘*OpenID Connect metadata document*’

![](/image-library/resources-images/user-guides-images/9-open-id-connect-endpoint1.x7a249602.png?q=80&f=webp)

### Application id

Click ‘*Overview*’ in the application options pane and then copy the ‘*Application (client) ID*’ which will be required when configuring Contensis to use your Azure AD instance.

![](/image-library/resources-images/user-guides-images/10-application-client-id.x2c96e4c0.png?q=80&f=webp)

'Application id' in the application 'Overview' section

### Tenant id

In the ‘*Overview*’ screen, copy the '*Directory (tenant) ID*’ which will be required when configuring Contensis to use your Azure AD instance.

![](/image-library/resources-images/user-guides-images/11-directory-tenant-id.x006582e2.png?q=80&f=webp)

'Directory (tenant) ID' in the application 'Overview' section

### Tenant name

Select ‘*Azure Active Directory*’ from the panel on the left, and then ‘*Custom Domain Names*’. You can then copy the ‘Name’ listed as the ‘Primary’ - this is your tenant name and will be required when configuring Contensis to use your Azure AD instance.

![](/image-library/resources-images/user-guides-images/5-select-tenant-name2.x4203da59.png?q=80&f=webp)

'Tenant name' in the 'Custom Domain names' section

![](/image-library/resources-images/user-guides-images/5a-select-tenant-name2.x7a7eb9f1.png?q=80&f=webp)

### Application key

In the application overview panel, click ‘*Certificates & secrets*’ and then click ‘*\+ New client secret*’.

You will see a form for naming and choosing the lifespan of a key. Complete as appropriate for your requirements, then click ‘*Add*’.

![](/image-library/resources-images/user-guides-images/7-get-key2.x23fe2581.png?q=80&f=webp)

Adding a key for a client secret

You will now need to copy the key as directed before navigating away from this screen. Click the ‘*Copy to clipboard*’ icon.

*Important: Once you leave this screen or carry out any other action, you will no longer be able to retrieve this key value.*

![](/image-library/resources-images/user-guides-images/7a-get-key1.xcfc76a5b.png?q=80&f=webp)

Copying the key for a client secret

You have now completed the registration of Contensis with Azure and are now ready to [configure Contensis to use Azure AD](https://www.contensis.com/help-and-docs/user-guides/user-management/single-sign-on/azure-ad-single-sign-on/configure-contensis-to-use-azure-ad).