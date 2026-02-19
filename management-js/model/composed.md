The composed field type contains the data that the [composer editor](https://www.contensis.com/help-and-docs/user-guides/content-modelling/field-editors/composer-field "Composer field") defines. It is an array of objects which expose *type* and *value* properties. The *type* property is a name given to an *allowed field type validation* defined in the content type that the entry is based on. The *value* contains the data for the field.

An *allowed field type* is essentially any standard field (such as Image, Heading, Location, etc.) that restricts what types of field can be added to a composed field.

For example, an *allowed field* could be defined with a type of *Heading* and named mainHeading or with a type of *Image* and named bannerImage. There can be multiple *allowed fields* based on the same type, but a composed field cannot contain other composed fields.

Name

Type

Format

Description

type

string

 

The field name given to a field type defined in the content type

value

*Any*

*Any*

The value of the field, which can be of any type

The example shows an example composed field.