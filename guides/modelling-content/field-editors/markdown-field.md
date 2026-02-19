1.  [Help and docs](/help-and-docs)
2.  [User guides](/help-and-docs/guides)
3.  [Modelling content](/help-and-docs/guides/modelling-content)
4.  Field editors

[Log in to add to favourites](/account/login)

Page last updated 10 December 2024

The Markdown editor allows you to write blocks of content using the Markdown syntax. Contensis uses the SimpleMDE Markdown editor as it provides a rich toolset, including a full-screen mode.

## Limitations

The content entered into the Markdown editor is stored and returned through the Delivery API as pure Markdown. Any links or images referenced in the Markdown editor have to be external as we do not parse the Markdown content.

## Appearance

![An example of the Markdown editor with the dark theme and toolbars applied.](/image-library/resources-images/user-guides-images/markdown-editor.x5a1fb92e.png?q=80&f=webp)

An example of the Markdown editor with the dark theme and toolbars applied.

## Settings

Setting name

Summary

[Name](/help-and-docs/user-guides/content-modelling/field-editors/field-settings)

A text label to identify the field in an entry.

[Field ID](/help-and-docs/user-guides/content-modelling/field-editors/field-settings)

A sanitised name to be used by the API.

[Read only](/help-and-docs/user-guides/content-modelling/field-editors/field-settings)

Prevents authors from editing the field in the entry editor.

[Allow multiple items to be added](/help-and-docs/user-guides/content-modelling/repeatable-fields/repeatable-field-overview)

Sets the field to be repeatable, allowing an author to create a list of items.

## Supported validation

This field editor supports the following validation methods:

## Properties

### Common properties

Property name

Summary

[Content guidelines](/help-and-docs/user-guides/content-modelling/field-editors/field-properties)

Provides guidance to an author for the expected content that the field should contain.

[Size](/help-and-docs/user-guides/content-modelling/field-editors/field-properties)

Determines the size of the rendered editor in the entry editor. The default value is set to *Medium*.

[Field visibility](/help-and-docs/user-guides/content-modelling/field-editors/field-properties)

Determines if the field should be displayed in the collapsed state when opening the entry editor.

### Show toolbar

This setting lets you prevent the editor toolbar from being displayed. This would require an author to understand how to write in the Markdown syntax.

The default is set to *Off*.

### Show status

This setting changes the visibility of the character and word count below the Markdown editor.

The default is set to *Off*.

### Allow fullscreen

It's possible to edit Markdown in a full-screen window within Contensis. This setting determines if authors should be allowed to enter full-screen mode.

The default is set to *Off*.

### Dark theme

This setting changes the Markdown editor to user the dark theme, rather than the default white theme.

The default is set to *Off*.