1.  [Help and docs](/help-and-docs)
2.  [User guides](/help-and-docs/guides)
3.  [Deploying websites and apps](/help-and-docs/guides/deploying-websites-and-apps)
4.  [Domains](/help-and-docs/guides/deploying-websites-and-apps/domains)

[Log in to add to favourites](/account/login)

Page last updated 28 May 2024

If you’ve added a custom domain to your project, you need to configure your external DNS provider to point your domain to Contensis.

To point a subdomain such as `docs.yourdomain.com` or `www.yourdomain.com` to your project on Contensis, you must first [add the domain to your project](/help-and-docs/guides/deploying-websites-and-apps/domains/add-and-update-a-domain) and then create a CNAME record with your DNS provider.

For example, if your site’s domain is `docs.yourdomain.com` and your alias is `alias.contensis.com`:

-   Follow the instructions to [add your domain](/help-and-docs/guides/deploying-websites-and-apps/domains/add-and-update-a-domain) `docs.yourdomain.com` to your project.
-   Login to your DNS provider’s site, add the CNAME record with your subdomain, `docs`, as the host.
-   Point the record to your Contensis alias, `alias.contensis.com`.
-   Save your settings. It may take a full day for the settings to propagate across the global Domain Name System.

## DNS record propagation

Depending on your DNS provider, **changes to DNS records can take several hours to propagate and take effect for the entire internet.**

If more than 24 hours have passed since you configured your DNS records, and your site is still not accessible, review your DNS configuration to ensure you have configured it correctly, then raise a support ticket.