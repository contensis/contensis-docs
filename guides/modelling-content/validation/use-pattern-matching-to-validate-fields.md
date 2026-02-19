1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [User guides](https://www.contensis.com/help-and-docs/guides)
3.  [Modelling content](https://www.contensis.com/help-and-docs/guides/modelling-content)
4.  Validation

[Log in to add to favourites](https://www.contensis.com/account/login)

Page last updated 04 December 2024

## On this page

-   [Appearance](#appearance)
-   [How to set the validation](#how-to-set-the-validation)
-   [Setting a custom expression](#setting-a-custom-expression)

The *matches pattern* validation method ensures that the value of a field matches a specific pattern defined by a regular expression.

A regular expression is a special text string for describing a search pattern. We use these expressions to validate the text that an author enters into a field of an entry.

## Appearance

![An example of a text field with an email address regular expression validation applied.](https://www.contensis.com/image-library/resources-images/user-guides-images/regex-valdiation.x416953f1.png?q=80&f=webp)

An example of a text field with an email address regular expression validation applied.

## How to set the validation

With a content type open for editing:

1.  Select the text field you want to set a validation rule for and pick the **Validation** tab from the *Field Settings* panel.
2.  Choose the required regular expression pattern you want to use from the *Matches pattern* dropdown, or define your own using the *Custom* option.
3.  You can add an alternative validation message by entering it in the *Validation message* text box. This will be displayed if the field fails validation when published.

## Setting a custom expression

You can use the *Custom* option in the matches pattern dropdown to create your own. Using a handy library and expression checker, like [Regular Expression 101](https://regex101.com/), to test your expression makes things easier.

Note: Expressions need to be written using the full JavaScript syntax to be valid.

### Predefined regular expressions

We've included some predefined expressions covering some standard scenarios.

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

## On this page

-   [Appearance](#appearance)
-   [How to set the validation](#how-to-set-the-validation)
-   [Setting a custom expression](#setting-a-custom-expression)