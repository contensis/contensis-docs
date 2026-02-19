There are two ways to create a webhook: within Contensis, or by using the Management API. This guide will take you through setting it one up in Contensis.

To set up a webhook you’ll need to be a System Administrator or be a member of a role with webhook permissions.

1.  Navigate to the Webhooks from by pressing **Settings** in the sidebar and going to **Webhooks** from the menu.
2.  Select **New webhook** from the toolbar. You’ll be presented with a *Create a webhook* window.
3.  Choose the **blank template** option and you’ll be taken to a new webhook screen.
4.  Give your webhook a name and an optional description, these will help you identify the webhook in Contensis.
5.  In the Webhook URL field, choose the method type and add the endpoint URL of the integration or application where you want to send webhook requests. This must be a https endpoint.
6.  Choose the [topics and events](https://www.contensis.com/help-and-docs/user-guides/integration/webhooks/webhook-topics-and-events) you want the webhook to be triggered by in the *Topics* section.
7.  Set any [headers](https://www.contensis.com/help-and-docs/guides/integrating-with-other-platforms/webhooks/webhook-custom-headers) or [custom payloads](https://www.contensis.com/help-and-docs/guides/integrating-with-other-platforms/webhooks/webhook-payloads) for the webhook request.
8.  Click **Save** to save your new webhook.

If you wish to test the webhook, we recommend using a service such as [Webhook.site](https://webhook.site/).