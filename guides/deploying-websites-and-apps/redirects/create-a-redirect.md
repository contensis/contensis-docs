There are two ways to create a redirect – within Contensis or by using the Management API. This guide will take you through setting one up in Contensis.

To create a redirect, you’ll need to be a System Administrator or a member of a role with redirect permissions.

1.  Navigate to the *Redirect* listing screen by pressing **Settings** in the sidebar and selecting **Redirects** from the menu.
2.  Select **New redirect** from the toolbar. The *New redirect* window will open.
3.  **Redirect type**: You will first need to choose an appropriate redirect type. There are two options:
    
    -   [301: Moved permanently (default)](https://httpwg.org/specs/rfc9110.html#status.301)
    -   [302: Found](https://httpwg.org/specs/rfc9110.html#status.302)
    
4.  **Source domain**: The source domain will be automatically set to *All domains* for any domain that is part of the project. However, you can choose a specific domain if required.
5.  **Match type:** These properties determine how the URL should be matched.
    
    -   Exact (default) – The redirect will only apply to a direct match to the string, such as `/about-us/.`
    -   Starts with – The redirect will apply for any URL that starts with the value. For example, `/about` would redirect for `/about-us` as well as `/about-us/company/`
    -   Regular expression (PCRE) – String matching using regular expressions based on the PCRE format. Use a service like [regex101](https://regex101.com/) to validate your expression.
    
6.  **Append source path to the destination**: When this toggle is switched on, it will append the original URL to the end of the URL in the browser address bar as a query string parameter.
7.  **Destination**: The new destination URL the source URL should redirect to.
8.  Press **Publish** to create your new redirect.

**Note**: When you create a redirect it may take up to 2 minutes to deploy the change to all load balancers.