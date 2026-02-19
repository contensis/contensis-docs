1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [User guides](https://www.contensis.com/help-and-docs/guides)
3.  [Deploying websites and apps](https://www.contensis.com/help-and-docs/guides/deploying-websites-and-apps)
4.  Renderers

[Log in to add to favourites](https://www.contensis.com/account/login)

Page last updated 14 March 2025

Renderers are a powerful feature that determine which Block should be used to display specific content. They create connections between content types or URLs and the appropriate display components, giving you flexibility in how your site renders different types of content.

## How renderers work

A renderer creates a relationship between content (identified by URL or content type) and a specific Block. When a browser requests content, the renderer determines which Block should handle the presentation.

This approach provides several benefits:

-   Use different languages or frameworks across your site
-   Apply specialised rendering for specific content types
-   Create consistent presentation for similar content
-   Implement rendering logic at different levels of your Site View structure

## Example: Blog post rendering

When a visitor accesses a blog post:

1.  The system identifies the content as a "blog" content type
2.  The renderer maps this content type to a "blog-post" Block
3.  The "blog-post" Block renders the content with appropriate styling and layout

## Setting up renderers

Renderers can be created in two ways:

1.  **Automatic creation**: When you push a new Block to a Contensis project
2.  **Manual creation**: Through the Renderer editor in Project settings

## Creating renderers manually

To set up a renderer manually:

1.  Navigate to Project settings
2.  Select **Renderers** from the menu
3.  Press **New renderer**
4.  Select the Block to be used
5.  Save your renderer configuration