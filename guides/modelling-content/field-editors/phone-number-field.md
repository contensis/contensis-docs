1.  [Help and docs](/help-and-docs)
2.  [User guides](/help-and-docs/guides)
3.  [Modelling content](/help-and-docs/guides/modelling-content)
4.  Field editors

[Log in to add to favourites](/account/login)

Page last updated 25 November 2024

The phone number field allows you to store contact details within entries. It provides an easy way to capture phone numbers for various purposes, such as following up on orders, event registrations, or job applications.

## Appearance

![](/image-library/resources-images/user-guides-images/phone-number-field.x59cbe8ce.png?q=80&f=webp)

## Settings

Setting name

Summary

[Name](/help-and-docs/user-guides/content-modelling/field-editors/field-settings)

A text label to identify the field in an entry.

[Field ID](/help-and-docs/user-guides/content-modelling/field-editors/field-settings)

A sanitised name to be used by the API.

[Default value](/help-and-docs/user-guides/content-modelling/field-editors/field-settings)

The default value property sets the default content for a field when an entry is created.

[Read only](/help-and-docs/user-guides/content-modelling/field-editors/field-settings)

Prevents authors from editing the field in the entry editor.

## Supported validation

This field editor supports the following validation methods:

### Custom pattern matching validation

If you want to validate the number that the author is entering matches a particular format, you can use a Matches pattern validation on the field to ensure the value is in the format you expect. We've provided some examples below to get you started.

#### UK Phone number

^(?:+44\\s?\\d{4}\\s\\d{6}|0\\d{4}\\s\\d{6})$

This pattern will allow the following UK formats:

-   01233 123456
-   07739 123456
-   +44 7739 123456

#### US Phone number

If you want to capture a US telephone number you can use the following regular expression:

(^(1?)(\\s?)(\[\\s\]?)(((\\d{3}))|(\\d{3}))(\[\\s\]?)(\[\\s-\]?)(\\d{3})(\[\\s-\]?)(\\d{4})+$)

-   555-555-5555
-   (555)555-5555
-   (555) 555-5555
-   555 555 5555
-   1 555 555 5555
-   800-692-7753
-   6505552368

## Properties

Property name

Summary

[Placeholder text](/help-and-docs/user-guides/content-modelling/field-editors/field-properties)

The placeholder property provides a short hint describing the expected value of a field.

[Content guidelines](/help-and-docs/user-guides/content-modelling/field-editors/field-properties)

Provides guidance to an author for the expected content the field should contain.

[Field visibility](/help-and-docs/user-guides/content-modelling/field-editors/field-properties)

Determines if the field should be displayed in the collapsed state when opening the entry editor.