1.  [Help and docs](/help-and-docs)
2.  [User guides](/help-and-docs/guides)
3.  [Modelling content](/help-and-docs/guides/modelling-content)
4.  Field editors

[Log in to add to favourites](/account/login)

Page last updated 10 December 2024

You can use the location field editor to provide an accurate geographical location within an entry. A location can be set using the search, which is powered by Google Places, or by navigating with the map.

Fine adjustments to location can be set by dragging the map pin to an exact position, or by entering latitude and longitude coordinates.

## Appearance

![](/image-library/resources-images/user-guides-images/location.xb15e568a.png?q=80&f=webp)

## Settings

Setting name

Summary

[Name](/help-and-docs/user-guides/content-modelling/field-editors/field-settings)

A text label to identify the field in an entry.

[Field ID](/help-and-docs/user-guides/content-modelling/field-editors/field-settings)

A sanitised name to be used by the API.

[Default value](/help-and-docs/user-guides/content-modelling/field-editors/field-settings)

The default value allows you to set the default location for an entry.

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

### Map centre position

If you want to set your map to be centred around a location other than the default of London, you can use this property to set where the map should be centred.

### Show latitude and longitude

It's possible to enter exact latitude and longitude values into the entry editor. However, most authors will want to use the search or set a location using the map.

This setting determines if the latitude and longitude number fields should be shown in the entry editor. These fields are not displayed by default.

### Show search

If you want your authors to manually set the location using the navigation controls, you can disable the search box in the field editor. The search box is enabled by default.

## Place search limitations

The location field editor uses the Google Places API Web Service to carry out location searches. There is a default limit set by Google of 1,000 free requests per 24 hour period.

Each text search counts as 10 requests to this service. The default limit in a 24 hour period could quickly be met if your authors regularly use location searches in their entries.

### Increasing the limit

To increase the limit to 150,000 requests you'll need to verify your identity with Google by adding your billing information through the [Google developer console](https://console.developers.google.com/). Once billing information has been added you can create an API Key via the Google API Console. This API key can then be applied to the project setting *Google\_ApiKey\_Places*.

If you feel you need more than the 150,000 requests then you can purchase a Google Maps API premium plan.

Full details can be found at the Google Place API [usage and billing site](https://developers.google.com/places/web-service/usage)