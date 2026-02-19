1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [User guides](https://www.contensis.com/help-and-docs/guides)
3.  [Forms](https://www.contensis.com/help-and-docs/guides/forms)
4.  Creating forms
5.  [Supported fields](https://www.contensis.com/help-and-docs/guides/forms/creating-forms/supported-fields)

[Log in to add to favourites](https://www.contensis.com/account/login)

Page last updated 04 October 2024

The Phone number field lets you collect contact details from users. If you want to be able to contact someone to follow up on feedback they have provided, an event they have registered for, or a job application they have submitted, this field gives your respondents an easy way to provide their details.

## Add a phone number field

-   With a form opened for editing, select the **Phone number** option from the form fields list to add it to your form.
-   From the settings panel, give the field a *Label*, for example, *What is your telephone number (mobile ideally)*?
-   Update the *Response column name* to Contact number.
-   **Save** your form.

## Match telephone number pattern

If you want to validate the number that the user is entering matches a particular format, you can use a Matches pattern validation on the field to ensure the value is in the format you expect. We've provided some examples below to get you started.

### UK Phone number

`^(?:+44\s?\d{4}\s\d{6}|0\d{4}\s\d{6})$`

This pattern will allow the following UK formats:

-   01233 123456
-   07739 123456
-   +44 7739 123456

### US Phone number

If you want to capture a US telephone number you can use the following regular expression:

`(^(1?)(\s?)([\s]?)(((\d{3}))|(\d{3}))([\s]?)([\s-]?)(\d{3})([\s-]?)(\d{4})+$)`

-   555-555-5555
-   (555)555-5555
-   (555) 555-5555
-   555 555 5555
-   1 555 555 5555
-   800-692-7753
-   6505552368