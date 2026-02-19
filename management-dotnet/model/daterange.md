1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [APIs](https://www.contensis.com/help-and-docs/apis)
3.  [.NET Management API](https://www.contensis.com/help-and-docs/apis/management-dotnet)
4.  Model

[Log in to add to favourites](https://www.contensis.com/account/login)

Page last updated 21 April 2022

The DateRange type represents a start and end point in time.

## Properties

Name

Type

Description

From

DateTime?

The date and time the range starts.

To

DateTime?

The date and time the range ends.

## Constructor

### Syntax

C#

```
public DateRange(DateTime from, DateTime to)
{
}
```

### Parameters

*from*

Type: `DateTime`  
The date and time the range starts.

*to*

Type: `DateTime`  
The date and time the range ends.

## Validation

The *From* value cannot be a later date than the *To* value.

## Examples

### Get a DateRange field object

C#

```
// Get the field value as a DateRange instance.
DateRange filmingPeriod = movieEntry.Get<DateRange>("filmingPeriod");

// Get the field value as a dynamic object (ExpandoObject).
dynamic filmingPeriod = movieEntry.Get("filmingPeriod");
```

### Set a DateRange field object

C#

```
// Set the field value.
movie.Set("filmingPeriod", filmingPeriod);
```