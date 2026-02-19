1.  [Help and docs](/help-and-docs)
2.  [User guides](/help-and-docs/guides)
3.  [Modelling content](/help-and-docs/guides/modelling-content)
4.  Components

[Log in to add to favourites](/account/login)

Page last updated 28 May 2024

A component is a group of fields that defines a reusable content structure, they are created using the component builder.

Unlike an entry a component does not hold content, but is stored in the entry where the component is used.

A component can be used in multiple content types. For example you may have an address component that is used in a Person content type to specify their home address, whilst the same address component could be used in a Venue content type to record the location of an event venue.

-   Address line one
-   Address line two
-   Town / City
-   County
-   Postcode

Other examples could include components like opening times, open graph metadata, accordions, hero banners and calls to action.

Think of components as a set of pre-defined fields that help keep the structure consistent across multiple content types.

## Nesting components

Components can be modular. Made up of multiple components to create a more complex component.

Take a common hero component for example, its usually made up of a title, description an image and a button.

-   Title
-   Description
-   Image
-   Button
    
    -   Label
    -   Style
    -   URL
    

But when we look at a button its made up of its own fields. The label that should be displayed on the button, the style of the button to match the design system (Solid, Outline, Link) and a destination URL when the button is pressed.

This is an opportunity to use nested components, creating a button component that can be placed inside the hero component.

### Hero

-   Title
-   Description
-   Image
-   *Nested component*: Button

### Button

-   Label
-   Style
-   URL