1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [User guides](https://www.contensis.com/help-and-docs/guides)
3.  Managing your environment

[Log in to add to favourites](https://www.contensis.com/account/login)

Page last updated 21 October 2024

The Audit screen in Contensis is an enterprise feature that allows you to track and review all activity taken within your environment. Whether you need to monitor content changes, user activity, or system updates, the Audit screen provides a comprehensive log to ensure transparency and accountability.

To access the Audit screen in Contensis:

1.  Open the **Settings** drawer from the sidebar by selecting the cog ion.
2.  From the settings drawer, select **Audit**. This will open the Audit screen, where you can view a detailed log of all activities.

## Understanding the Audit interface

The Audit screen is divided into several key sections:

-   **Project:** This column shows the actions that have taken place in a given project.
-   **Type:** This defines the resource type where an event has taken place.
-   **Title:** This provides a link to the resource that has been affected.
-   **Message**: This describes the specific action taken – for example, Entry created or Entry updated – and may contain additional information about the action, such as the content that was modified or the settings that were changed.
-   **Actioned by**: This column displays the username or email of the individual who performed the action.
-   **Actioned on**: This column shows the exact date and time when an action was performed.

## Filtering and searching logs

To make it easier to find specific actions, the Audit screen in Contensis includes filtering and search options:

-   **Project**: Select a specific project from the dropdown menu to see only the actions that apply to that project.
-   **Resource ID**: Enter an ID of a resource that you are looking for, such as an Entry ID or  API ID.
-   **Resource type**: Choose from a list of specific resources types to narrow down the results.
-   **Actioned by user**: Select a specific user from the dropdown menu to see only the actions performed by that user.
-   **Date range**: Use the date picker to select a specific range of dates for the audit logs you wish to view.

## Export the current page

If you have a single page of audit actions you can quickly export them to CSV using the *Table options* menu in the page toolbar. To export a single page:

1.  Press the **Table options** cog in the page toolbar.
2.  Select **Export to CSV** from the dropdown menu.
3.  Your audit logs will be downloaded in the following format: export\_2024-06-13\_16-43-47.csv

## Export all logs

If your logs span multiple pages, the export to CSV option will present you with a window asking you if you want to download the current page or all logs. To export all logs:

1.  Press the **Table options** cog in the page toolbar.
2.  Select **Export to CSV** from the dropdown menu.
3.  From the window that is displayed, select from the Current page or All logs options.
4.  Your audit logs will be downloaded in the following format: export\_2024-06-13\_16-43-47.csv

## What data is exported?

The audit data that is exported is based on what you can see in the listing. So, if you have used managed columns to reorder column data, add or removed columns, then this is reflected in your export.

## Types of Audit log

Resource

Events

Asset

Asset created  
Asset updated  
Asset published  
Asset deleted

Block

Block version pushed  
Block version workflow status  
Block version running status  
Block version marked as broken

Component

Component created  
Component updated  
Component published  
Component deleted

Content type (Asset)

Content type (Entry)

Content type (Entry) created  
Content type (Entry) updated  
Content type (Entry) published  
Content type (Entry) deleted

Content type (Form)

Content type (Form) created  
Content type (Form) updated  
Content type (Form) published  
Content type (Form) deleted

Content type (Webpage)

Content type (Webpage) created  
Content type (Webpage) published

Entry

Entry created  
Entry updated  
Entry published  
Entry archived/unarchived  
Entry deleted/restored/permanently deleted  
Entry workflow transitions

Folder

Folder created  
Folder updated  
Folder deleted/restored/permanently deleted

Form response

Form response created  
Form response archived/unarchived  
Form response deleted/restored/permanently deleted  
Form response workflow transitions

Group

Group created  
Group updated  
Group deleted  
User assigned/unassigned  
Child group assigned/unassigned

Node

Node created  
Node updated  
Node deleted

Project

Project created  
Project updated

Proxy

Proxy created  
Proxy updated  
Proxy deleted

Renderer

Renderer created  
Renderer updated  
Renderer deleted

Role

Role created  
Role updated  
Role deleted

Setting

Setting updated

Site View tree

Tree created  
Tree updated

User

User created  
User updated  
User deleted

Webhook

Webhook created  
Webhook updated  
Webhook deleted  
Webhook disabled/enabled