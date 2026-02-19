1.  [Help and docs](/help-and-docs)
2.  [User guides](/help-and-docs/guides)
3.  [Forms](/help-and-docs/guides/forms)
4.  Creating forms

[Log in to add to favourites](/account/login)

Page last updated 17 September 2025

Have you ever filled out a form and had your browser suggest your name and address? This feature, enabled by the autocomplete attribute, is not just convenient but also an important accessibility tool.

The [autocomplete attribute](https://html.spec.whatwg.org/multipage/forms.html#sec-autofill) can be added to form fields so that browsers and assistive technologies can understand the purpose of the field and help users fill out the information faster.

To specify the autocomplete attribute for a form field you'll need to do the following:

1.  With a form opened for editing, select the field you want to apply the autocomplete attribute to.
2.  From the advanced settings panel, locate the Autofill property.
3.  Enter an autocomplete value from the [MDN docs](https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes/autocomplete#values) that reflects the expected input.

## Predefined values

The following fields in the forms builder have predefined values applied when rendered, but these can be overridden using the process above.

-   Email address is set to `email`
-   Phone number is set to `tel`
-   Website is set to `url`

## **Accessibility**