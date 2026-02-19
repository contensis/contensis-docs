1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [User guides](https://www.contensis.com/help-and-docs/guides)
3.  [Managing users](https://www.contensis.com/help-and-docs/guides/managing-users)
4.  Single sign-on
5.  [Azure AD single sign-on](https://www.contensis.com/help-and-docs/guides/managing-users/single-sign-on/azure-ad-single-sign-on)

[Log in to add to favourites](https://www.contensis.com/account/login)

Page last updated 19 May 2025

With your [Contensis application registered in Azure AD](https://www.contensis.com/help-and-docs/guides/managing-users/single-sign-on/azure-ad-single-sign-on/register-contensis-with-azure-ad)**,** the next step is to login to Contensis and configure the Azure AD integration.

1.  Login to Contensis using an administrative account.
2.  Navigate to the *Management Console* and select **Global Settings**, you need to enter the following settings:

## WSFederation\_MetadataEndpoint

This needs to be set to your Azure AD metadata endpoint address. This can be found by following these steps:

1.  Navigate to the [**Azure Portal home page**](https://portal.azure.com/#home), followed by **App Registrations**:

![](/image-library/resources-images/user-guides-images/1-app-registrations-step1.xd5042775.png?q=80&f=webp)

2.  Next, select the relevant application from the list:

![](/image-library/resources-images/user-guides-images/2-select-app-step1.xb1926e61.png?q=80&f=webp)

3.  Update the *WSFederation\_MetadataEndpoint **global setting**.* The value for this is different depending on whether you are using the current Azure AD configuration (*WSFederation\_Type*\=3) or the legacy configuration (*WSFederation\_Type* =2):
    
    1.  Legacy Azure AD configuration (*WSFederation\_Type* =2): Copy the *Federation Metadata Document* address from the textbox.
    2.  Current Azure AD configuration (*WSFederation\_Type* =3): Copy the *OpenID Connect metadata* document address from the textbox
    

![](/image-library/resources-images/user-guides-images/3-select-metadat-endpoint.x27b271d4.png?q=80&f=webp)

## WsFederation\_AzureTenantID

This needs to be set to your Azure AD tenant ID. This can be found by following these steps:

-   Select Azure Active Directory, followed by Properties. Your tenant ID is the same as your Directory ID. Enter this in the *WSFederation\_TenantID* global setting.

![](/image-library/resources-images/user-guides-images/4-select-tenant-id1.xebbb99b6.png?q=80&f=webp)

## WsFederation\_AzureTenantName

This needs to be set to your Azure AD tenant name. This can be found by following these steps:

-   Go to the **Azure Portal home page** and select '**tenant properties**'. Your tenant name is the name of your primary domain. Enter this in the *WSFederation\_TenantName* global setting.

![](/image-library/resources-images/user-guides-images/5-select-tenant-name.xbd798943.png?q=80&f=webp)

![](/image-library/resources-images/user-guides-images/5a-select-tenant-name2.x7a7eb9f1.png?q=80&f=webp)

## WsFederation\_AzureApplicationID

This needs to be set to the application ID of the registered Contensis app in Azure. This can be found by following these steps:

-   Navigate to the **[Azure Portal home page](https://portal.azure.com/#home)**, followed by **App registrations** then select the Contensis application. Your application ID is listed on the application overview. Enter this in the *WSFederation\_ApplicationID* global setting.

![](/image-library/resources-images/user-guides-images/10-application-client-id.x2c96e4c0.png?q=80&f=webp)

## WsFederation\_AzureApplicationKey

1.  Navigate to your application and click **Certificates & secrets** and then select **'+ New client secret'**.

![](/image-library/resources-images/user-guides-images/7-get-key1.x686bfcfd.png?q=80&f=webp)

2.  Enter a *description*, choose an *expiration* and then click **Add**.

**Note**: Once you navigate away from this screen you will not be able to retrieve the key again. In the event that you lose the key value then you will need to delete the key and add a new one.

![](/image-library/resources-images/user-guides-images/7a-get-key.xb58de5b1.png?q=80&f=webp)

3.  Enter the value of the key into the *WSFederation* **global setting**.

## WSFederation\_Type

This needs to be set to 2 for Azure AD accounts created before October 2021, and to 3 for any created later.

## Optional Global Settings

**WsFederation\_Azure\_PrioritiseUPNForEmailAddress  
**If set to 1, the UPN of a user will be checked first when establishing the user's email address instead of the primary email claim.

**WsFederation\_EnableGroupImports**

If set to 1, a successful federated CMS login will configure the relevant user's groups to match those on the federated identity provider. If set to 0, no group changes will take place on login. NB: The CMS must be restarted for this to take effect.

**WsFederation\_AzureAdGroupImportAllowList**

Specifies the groups from the federated identity provider that are permitted to be imported during login. Use a semicolon-separated list of group names. If left empty, all groups will be imported (when WsFederation\_EnableGroupImports is active). CMS restart required for changes to take effect.

NB: This setting can be changed without having to restart the identity provider (IdP)

## Final step

Our support team will need to apply these changes for you. Please [raise a help desk ticket](https://www.contensis.com/help-and-docs/help-desk) to arrange this.