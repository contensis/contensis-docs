1.  [Help and docs](/help-and-docs)
2.  [User guides](/help-and-docs/guides)
3.  [Modelling content](/help-and-docs/guides/modelling-content)
4.  Field editors

[Log in to add to favourites](/account/login)

Page last updated 10 December 2024

## Name

The *Name* property describes the field content. The *Name* entered here will be displayed to an author when creating an entry. It's used to identify the chunk of content. This *Name* is also sanitised and used to generate the *Field ID*

## Field ID

The *Field ID* is used to identify the field within a content type through the API. The *Field ID* is automatically generated when creating a *Name* and sanitised for use as the *Field ID*.

*Field IDs* have to be unique within a content type. If you attempt to use a *Name* that is already in use then a number will be appended to the *Field ID*.

## Default value

The *Default* value property sets the initial content for a field when an entry is first created. If no change is made by an author when editing the entry then the default value will be used.

For example, default location fields are set to London. So, if the default location isn't changed, that entry will be set to London.

The type of default value input will vary between field editors. Not all field editors support default values.

## Format

Some fields support different *Formats* of data. By changing the data *Format* you are specifying the type of data that is stored and returned via the API.

Depending on the *Format* you specify, you may be provided with different types of field editor for the field.

For example, if you were to select the date field and change its *Format* from *single* to *range*, you would see a set of editors that support *date from* and *date to*.

## Title and slug field

The title field is used to identify content in the editor interface. The title is also used to generate a unique human readable and SEO-friendly identifier known as a slug. Both the title and slug are avaliable through the Delivery API.

The first text field added to the content type will be used as the *Title* field. If you decide you want to use another field for your *Title* field, you can change it at a later date.

You can choose to display the slug editor if you want your authors to be able to update the slug field.

## Description field

The *Description* field can be used to help identify similar entries in the editor and is also available in the Delivery API. A description cannot be set on a field that is the entry title.

## Thumbnail field

The *Thumbnail* field provides a way of visually identifying entries in the editor, as well as providing a consitent way to identify thumbnails in the Delivery API as an `entryThumbnail` alongside `entryTitle` and `entryDescription`.

## Read only

The read only property prevents an author from editing the contents of a field in the entry editor. This is especially useful if you are importing content from an external data source in to an entry that must not be changed by an author.