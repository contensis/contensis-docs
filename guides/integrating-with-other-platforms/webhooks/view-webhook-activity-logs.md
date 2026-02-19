We keep a log of all activity for each webhook for 30 days in your project. Activity logs can be really helpful when you want to troubleshoot why a webhook may not have been successful.

To view the activity logs of a webhook you will need to be a System Administrator or be a member of a role with webhook permissions.

1.  Navigate to the *Webhooks* screen in *Settings* by pressing the **Settings** button in the sidebar, followed by **Webhooks**.
2.  Locate the Webhook you want to view the activity for in the list and press the **Action** button denoted by the triple dot.
3.  Select **Activity logs** from the menu.
4.  The activity logs will be displayed for the webhook.

## Activity log listing

The following information is displayed in the activity log listing:

-   **Webhook URL** – This is the endpoint URL you set in the webhook. The URL that you see may vary if you've templated the URL with values such as the entry ID or other resource values, for example https://www.mywebhookurl.com/endpoint/entry-id="1a4bc60a-a5c1-4030-944f-64b1d90f3431".
-   **Resource** – The type of resource the webhook was triggered by. This could be Entries, Content types, Components, Assets, Nodes, Users or Groups.
-   **Event** – The type of event that raised the webhook event. This could include Created, Updated, Published, Deleted, Unpublished, workflowStateChange, workflowEventRaised.
-   **Date / time** – Specifies the date and time when the webhook was initially triggered.
-   **Status** – Specifies the status of the triggered webhook and whether it was successfully triggered, denoted by the HTTP status code of 200, or if any error has occurred, denoted by status code 400. You may also see a status of In progress. This occurs when the webhook is initially triggered and awaiting a HTTP response.
-   **Response time** – The response time from the endpoint that resulted in a successful 200 HTTP status code.
-   **Attempts** – In the event of a failure, or if a session timeout occurs (the webhook request timeout is 10 seconds), the webhook will immediately retry sending data to the destination URL again a further 9 times in a 24 hour period using an exponential backoff strategy.

## View call details

To view the details of the webhook call, click on the call details link. It will display the Request Details of the webhook call as well as the Response Details received.

### Cycle through retries

When the webhook has had a number of retries you can cycle through the call details of each request and response using the previous and back buttons in the call details toolbar.