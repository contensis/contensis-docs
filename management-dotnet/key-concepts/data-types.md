1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [APIs](https://www.contensis.com/help-and-docs/apis)
3.  [.NET Management API](https://www.contensis.com/help-and-docs/apis/management-dotnet)
4.  Key concepts

[Log in to add to favourites](https://www.contensis.com/account/login)

Page last updated 04 December 2020

The DataType is the storage type for a field and determines how the field data is validated and indexed for search. In the .NET Delivery API client, the DataType is represented as a DataType `enum` type.

## Syntax

C#

```
public enum DataType
```

## Members

Type

Description

.NET Types

String

Used for text entries such as titles, content or markup.

`string`

Integer

A whole number.

`short`, `int`, `long`

Decimal

A number with a fractional part.

`decimal`, `double`, `float`

Boolean

A value of *true* or *false*.

`bool`

DateTime

A point in time.

`DateTime`

Object

Any arbitrary structure as JSON or a string.

`object`

StringArray

An array of Strings.

`string[]`, `IList<string>`

IntegerArray

An array of Integers.

`int[]`, `IList<int>`

DecimalArray

An array of Decimals.

`int[]`, `IList<int>`

DateTimeArray

An array of DateTimes.

`DateTime[]`, `IList<DateTime>`

ObjectArray

An array of Objects.

`object[]`, `IList<object>`