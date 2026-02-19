1.  [Help and docs](/help-and-docs)
2.  [User guides](/help-and-docs/guides)
3.  [Forms](/help-and-docs/guides/forms)
4.  Creating forms
5.  [Validation](/help-and-docs/guides/forms/creating-forms/validation)

[Log in to add to favourites](/account/login)

Page last updated 03 October 2024

The *matches pattern* validation method ensures that the value of a field matches a specific pattern defined by a regular expression.

A regular expression is a special text string for describing a search pattern. We use these expressions to validate the text that a user enters into a form field.

## How to set the validation

With a form open for editing:

1.  Select the text field you want to set a validation rule for and pick the **Validation** tab from the *Field settings* panel.
2.  Choose the required regular expression pattern you want to use from the *Matches pattern* dropdown, or define your own using the *Custom* option.
3.  You can add an alternative validation message using the *Validation message* text box. This will be displayed if the field fails validation when the form is submitted.

## Setting a custom expression

You can use the *Custom* option in the matches pattern dropdown to create your own regular expression. Using a handy library and expression checker, like [Regular Expression 101](https://regex101.com/), to test your expression makes things easier.

### Predefined regular expressions

We've included predefined expressions covering some standard scenarios.

#### Website address

Allowed values

Disallowed values

http://www.zengenti.com

special%character@zengenti.com

https://contensis.com

name@zengenti

http://www.contensis.com/help-and-docs/user-guides/introduction-to-contensis

notawebsite.com

#### Email address

Allowed values

Disallowed values

niceandsimple@example.com

Abc.example.com

very.common@example.com

A@b@c@example.com

a.little.lengthy.but.fine@dept.example.com

john..doe@example.com

#### UK postcodes

Allowed values

Disallowed values

SY8 3EG

SY8\_3EG

sy83eg

sy8-3eg

SY83EG

sy8 £eg

#### 12 hour time

Allowed values

Disallowed values

10:20 am

12:15

10.42.01 AM

101603

09 26 03 PM

12am

7:35 PM

10:67

#### 24 hour time

Allowed values

Disallowed values

10:20

1215

10.42.01

101603

09 26 03

12 am

07:57

10:67

#### Title casing

Allowed values

Disallowed values

This Is A Title

This is a title

This Is Another Title

This is A title