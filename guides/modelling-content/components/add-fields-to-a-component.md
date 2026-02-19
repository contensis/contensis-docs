1.  [Help and docs](/help-and-docs)
2.  [User guides](/help-and-docs/guides)
3.  [Modelling content](/help-and-docs/guides/modelling-content)
4.  Components

[Log in to add to favourites](/account/login)

Page last updated 10 December 2024

A component is made up of a set of fields. Fields allow you to break up large blobs of content into smaller chunks, making content more flexible and reusable.

Fields comprise a type, format and a field editor. The supported types, formats and editors are outlined in the following [article](/help-and-docs/user-guides/content-modelling/field-editors/supported-fields-and-editors).

## Add a field

With the component open for editing:

-   To add a field to your component, select a field type by pressing on one of the buttons in the *Toolbox*. The field will be added to the bottom of your component. It will be active and indicated by a green border.

### Set a field name

The settings for a field will be displayed in the right-hand panel when the field is active.

Give the field a name that clearly identifies its content. The field name is used to generate a sanitised field ID that a developer will use with the Delivery API. The field name will be visible to an author when they are creating an entry.

Read through our [field settings](/help-and-docs/user-guides/content-modelling/field-editors/field-settings) article to get a better understanding of each setting.

**Warning:** If a field name has previously been used and deleted from the component and is subsequently reused, any existing entries containing that field may have data preserved and would be returned via the Delivery API. Any pre-existing data would also be shown in the entry editor.