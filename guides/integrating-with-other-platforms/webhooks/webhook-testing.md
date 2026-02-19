1.  [Help and docs](/help-and-docs)
2.  [User guides](/help-and-docs/guides)
3.  [Integrating with other platforms](/help-and-docs/guides/integrating-with-other-platforms)
4.  Webhooks

[Log in to add to favourites](/account/login)

Page last updated 29 May 2024

It's really important to test and validate that the information you are sending to a webhook endpoint. Depending on the service you are integrating with, it may be expecting specific HTTP headers to be sent or a payload in a particular structure.

When setting up an integration or using webhooks for the first time it's helpful to use a tool like webhook.site to validate the data you are sending in your webhook request.

This article will outline the process for testing a simple webhook.

## Validate your response with webhook.site

With [webhook.site](https://webhook.site/) you are given a unique, random URL that you can use to test and debug webhooks and HTTP requests.

1.  Open up a new tab and head over to [webhook.site](https://webhook.site/)
2.  Copy *Your unique URL* to the clipboard.
3.  Create or open an existing webhook.
4.  **Paste** the URL in your clipboard into the *Webhook URL* field.
5.  **Save** changes to your webhook.
6.  You can now monitor any requests triggered by your webhook at [webhook.site](https://webhook.site/). The site should automatically update as the webhooks are received. If you can't see anything coming through then you'll also be able to monitor any activity from Contensis by viewing the webhook [activity logs](/help-and-docs/user-guides/integration/webhooks/view-webhook-activity-logs).

Once you are happy that the correct information is being sent, you can update the webhook URL with the endpoint of the service you are using.