Depending on how you've developed your site, you may have created a single Block or app to handle your entire site or chosen to create individual Blocks to serve specific features of it.

In most cases, you'll start with a single renderer/Block applied to the root of your website.

The process below outlines how to set a renderer on any URL of your site.

## Setting a renderer on a node

1.  Select **Site View** from the sidebar to manage your site structure and content.
2.  With Site View open, use the tree to navigate to the node of your site where you want to assign a renderer.
3.  Either right-click the node or press the **Action** button – indicated by the triple dot icon to the right of the node – to open the node context menu.
4.  Select **Node properties** from the menu that is displayed. The node properties panel will open.
5.  From the renderer dropdown, select the renderer associated with the Block you want to use to serve the section of the site.
6.  The *Is partial match root?* option is enabled by default. This ensures that any URL that matches the node or child of that node will use the same renderer. If the renderer should only be applied to the selected node, uncheck the toggle.
7.  Press update to confirm your changes. Your changes will be immediate, and content under that URL will be served by the renderer/Block combination you have assigned.