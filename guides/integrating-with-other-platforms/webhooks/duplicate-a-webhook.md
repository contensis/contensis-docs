If you find yourself needing to create a duplicate of an existing webhook, you can copy one from the webhook listing or editor.

**Note**: When a webhook is duplicated, it is disabled to prevent duplicate events from being raised and webhooks being sent to the same endpoint. After making your changes to the webhook, you'll need to enable it.

## Duplicate a webhook from the listing

-   From the webhook listing screen, locate the webhook you want to duplicate and press the **Actions** button, as indicated by the triple dot icon. A dropdown menu will be displayed.
-   Select **Duplicate** from the menu. The webhook will be copied and opened for editing. The new webhook will have '- Copy' appended to its name.

## Duplicate a webhook from the editor

-   With the webhook opened for editing, press the **Actions** button, as indicated by the triple dot icon. A dropdown menu will be displayed.
-   Select **Duplicate** from the menu. The webhook will be copied and opened for editing. The new webhook will have ' - Copy ' appended to the name field.

**Warning:** If your webhook contains secret headers, these will be removed when duplicated to prevent unauthorised access to the header secrets.