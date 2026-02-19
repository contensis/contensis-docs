The `ComposedField` type contains the data that the [Composer editor](https://www.contensis.com/help-and-docs/user-guides/content-modelling/field-editors/composer-field "Composer field") defines. It contains a list of [ComposedFieldItem](https://www.contensis.com/help-and-docs/apis/management-dotnet/model/composedfielditem) instances, which expose *Type* and *Value* properties. The *Value* property allows data for the field to be retrieved or set. The *Type* property is a name given to an *allowed field type validation* defined in the content type that the entry is based on.

An *allowed field type* is essentially any standard field (such as Image, Heading, Location, etc.) that restricts what types of field can be added to a `ComposedField`.

For example, an *allowed field* could be defined with a type of *Heading* and given a type name of "mainHeading" or with a type of [Image](https://www.contensis.com/help-and-docs/apis/management-dotnet/model/image) and given a type name of "bannerImage". There can be multiple *allowed fields* based on the same type, but a `ComposedField` cannot contain other `ComposedField` fields.

### Add overload

The ComposedField type inherits from `List<ComposedFieldItem>` with an additional *Add* method.

#### Remarks

The item added using this method will be appended to the end of the list.

#### Example