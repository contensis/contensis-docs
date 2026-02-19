## We value your privacy

We use cookies to improve your experience. [Privacy policy](/privacy-and-cookies).

[Skip to main content](#main)

1.  [Help and docs](/help-and-docs)
2.  [APIs](/help-and-docs/apis)
3.  [.NET Management API](/help-and-docs/apis/management-dotnet)
4.  Model

[Log in to add to favourites](/account/login)

Page last updated 27 April 2022

The Quote type represents a section of referenced text from an external source.

## Constructor

### Syntax

C#

```
public Quote(string text, string source)
{
}
```

### Parameters

*text*

Type: `string`  
The quote text.

*source*

Type: `string`  
The source of the quote.

## Properties

Name

Type

Description

Text

string

The quote text.

Source

string

The source of the quote.

## Examples

### Get a Quote object

C#

```
// Get the field value as a Quote instance.
Quote movieQuote = movieEntry.Get<Quote>("memorableQuote");

// Get the field value as a dynamic (ExpandoObject) instance.
dynamic movieQuote = movieEntry.Get("memorableQuote");
```

### Set a Quote object

C#

```
// Create a Quote object.
var memorableQuote = new Quote("There’s a snake in my boots.", "Woody, Toy Story");

// Set the field value.
dynamic movieQuote = movieEntry.Set("memorableQuote", memorableQuote);
```