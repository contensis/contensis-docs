1.  [Help and docs](/help-and-docs)
2.  [APIs](/help-and-docs/apis)
3.  [.NET Management API](/help-and-docs/apis/management-dotnet)
4.  Model

[Log in to add to favourites](/account/login)

Page last updated 04 December 2020

## Constructor

### Syntax

C#

```
public ComposedFieldItem(string type, object value)
{
}
```

*type*

Type: `string`  
The name of the allowed field type

*value*

Type: `value`  
The value for the field item returned a dynamic object

## Members

Name

Type

Description

Type

`string`

The name of the allowed field type

Value

`dynamic`

The value for the field item returned a dynamic object

## Methods

### ValueAs<T>

Returns the field item value as `T`.

C#

```
public T Value<T>()
{
}
```

### Parameters

*T*

The type to attempt to cast the field data to.

### Remarks

For complex objects, if the type of T does not match the value type, then either a null value will be returned or an object of type T is returned with no property values.

### Example

C#

```
// Get the ComposedField instance
var composed = movieEntry.Get<ComposedField>("synopsis");

// Get the first item value as a Quote object
var quote = composed[0].ValueAs<Quote>();

// Get the second item value as a string
var paragraph = composed[1].ValueAs<string>();
```