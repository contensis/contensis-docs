1.  [Help and docs](/help-and-docs)
2.  [User guides](/help-and-docs/guides)
3.  [Deploying websites and apps](/help-and-docs/guides/deploying-websites-and-apps)
4.  Proxies

[Log in to add to favourites](/account/login)

Page last updated 28 May 2024

A proxy needs to be attached to a node in Site View to direct traffic from the incoming user request to its new destination.

This article assumes that all website traffic enters your domain and is managed by Contensis.

1.  Navigate to the *Proxies* screen by pressing **Settings** in the sidebar and selecting **Proxies** from the menu.
2.  From the proxy listing, locate and open the proxy for editing.
3.  Press the **Attached nodes** tab, followed by the **Attach nodes** button. The *Attached nodes* window will open, displaying your Site View tree.
4.  Select the node to which the proxy should be attached, and press **Apply**.
5.  Any visitor request to that node will now use the reverse proxy you have specified.

### Enable/disable partial matching

If the node you have attached the proxy to contains children where Contensis entries should be served, you can enable partial matching for the reverse proxy.

This allows you to use the reverse proxy in a migration scenario where you want to serve content from a legacy system whilst introducing content in Contensis as entries a section at a time.

#### Example: Reverse proxy with partial matching enabled

In this example, the reverse proxy is applied on a node called `about-us`. The `our-team` section contains entries attached to their respective Site View nodes.

The `our-story` and `terms-and-conditions` nodes do not exist in Site View and are served by the reverse proxy using partial matching.

Markdown

```
+ about-us (Reverse proxy, with partial matching)
	+ our-team (Entry)
		+ alfonso-dias (Entry)
		+ marley-phillips (Entry)
		+ maria-petrovs (Entry)
	∞ our-story (Legacy content)
	∞ terms-and-conditions (Legacy content)
```