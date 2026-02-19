The *ComposedField* type contains the data that the [Composer editor](/help-and-docs/apis/management-dotnet/model/composedfielditem "API Keys") defines. It is a read-only list of *ComposedFieldItem* instances, which expose a *Type* property and *Value* methods. The *Value* methods return the data for the field. The *Type* property is a name given to an *allowed field type validation* defined in the content type that the entry is based on.

An *allowed field type* is essentially any standard field (such as Image, Heading, Location, etc.) that restricts what types of field can be added to a *ComposedField*.

For example, an *allowed field* could be defined with a type of *Heading* and given a type name of "mainHeading" or with a type of *Image* and given a type name of "bannerImage". There can be multiple *allowed fields* based on the same type, but a *ComposedField* cannot contain other *ComposedField* fields.

The methods on the *ComposedFieldItem* enable the value of the field to be retrieved.

Returns the field item value as a dynamic object.

### Syntax

### Remarks

Complex objects will be returned as dynamic [ExpandoObject](https://msdn.microsoft.com/en-us/library/system.dynamic.expandoobject%28v=vs.110%29.aspx) instances.

### Example

Returns the field item value as `T`.

### Syntax

### Remarks

For complex objects, if the type of T does not match the value type, then either a null value will be returned or an object of type T is returned with no property values.

### Example

The example below shows how a composed field with different field types can be rendered.