1.  [Help and docs](/help-and-docs)
2.  [User guides](/help-and-docs/guides)
3.  [Forms](/help-and-docs/guides/forms)
4.  Creating forms

[Log in to add to favourites](/account/login)

Page last updated 17 September 2025

## On this page

-   [Default notification](#default-notification)
-   [Notification rules (any condition)](#blok-heading146)

You can choose to set up team notifications to automatically email you and your colleagues when a user fills out and submits a form.

## Default notification

When you first create a form, you'll need to enable a default notification to be notified of new responses.

1.  With a form opened for editing select the **Email notifications** button from the form toolbar
2.  Select the **Team notifications** tab
3.  Enable the default notification by pressing the toggle to the on position, the notification properties will be displayed.
4.  -   You can also notify users that don't have Contensis account by typing their email address, you'll be prompted with an `Add external-address@my-org.co.uk` prompt as you enter the address.
    
    **Recipient email:** Choose from a list of users who should be notified when a form response is recieved, the dropdown lists Contensis users.
5.  **Email subject:** An automatic subject is populated, but change it to meet your needs.
6.  **Email content:** Enter a message to be displayed to the users you are notifying. This can be customised using common formatting such as heading, tables, lists and links.
7.  **Save** the changes to your form.

### Including form data in your notification

The notification message can include content that was submitted by the user of the form, either individual parts of the form, or your could include a summary of the data as a Form response table.

#### Using liquid variables

You can use liquid variables to output content such as a users name `{{ name }}` or message `{{ message }}` by including the ID of the field wrapped in curly braces.

If you are unsure of the the field name, press the **Show variables** button to be presented with a list of form fields with their liquid variables displayed. Simply copy and paste them into you message.

#### Insert a Form response table

We've included a forward slash command in the editor to easily insert a table of each of the form fields and their liquid variables, start typing `/form` to insert the Form response table into the body of your message. If you have a multi-page form, a table will be added for each page, using the page name for the table caption.

## Notification rules (any condition)

To send notifications based on form content, use notification rules to customise messages for specific individuals or teams. For example, with an enquiry form, you can send different messages to various teams depending on the enquiry type selected by the user.

1.  From the *Team notification* tab scroll down to *Notification rules (any condition)*.
2.  Add a rule by either selecting **Add rule** if your notifications are empty or by presssing the **add button** indicated by a plus icon.
3.  -   Set **Field** to *Enquiry type*
    -   Set **Operator** to *Equal t*o
    -   Set **Value** to *Project enquiry* by select the value from the list.
    
    A rule is based on one or more conditions being met, based on a *Field*, *Operator* and *Value* selections. Using our enquiry form example if a dropdown labelled enquiry type was set to *Project enquiry* by a user populating a form then we can create a condition that matches.
4.  If you want to add additional logic to the ruleset, press the Plus button next to your first condition. You can choose wether all conditions should be met, or any of the conditions, by changing the value of the dropdown.
5.  As with a [default notification](#default-notification) you can set a recipient list, subject and message to reflect the conditions you've selected allowing a fully customised notification that is relevant to your team members.
6.  **Save** and Publish the changes to your form.

Once you have set up your notification rules and customised your messages, be sure to thoroughly test the notifications to ensure they are working as expected. This will help guarantee that your team receives the relevant information promptly and can respond appropriately.

## On this page

-   [Default notification](#default-notification)
-   [Notification rules (any condition)](#blok-heading146)