1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [APIs](https://www.contensis.com/help-and-docs/apis)
3.  [.NET Management API](https://www.contensis.com/help-and-docs/apis/management-dotnet)
4.  Model

[Log in to add to favourites](https://www.contensis.com/account/login)

Page last updated 27 April 2022

A project object can be used to understand the languages that the project supports and which language is the primary language. The project instance is also where entry operations are located.

## Members

Name

Type

Description

Id

`string`

The project identifier, e.g. "movieDb". Found in the project overview screen of the management console.

Name

`string`

The friendly name given to the project.

Description

`string`

The description text given to a project.

SupportedLanguages

`IList<string>`

An array of all the languages supported by the project.

PrimaryLanguage

`string`

[LanguageCode](https://www.contensis.com/help-and-docs/apis/management-dotnet/key-concepts/localization) The primary language for the project.

## Methods

Method

Returns

Description

[Save()](about:/help-and-docs/apis/management-dotnet/model/project-methods#save)

 

Commits any changes made to the project instance.

[SaveAsync()](about:/help-and-docs/apis/management-dotnet/model/project-methods#saveasync)

 

Commits any changes made to the project instance asynchronously.

[Delete()](about:/help-and-docs/apis/management-dotnet/model/project-methods#delete)

 

Deletes the project instance.

[DeleteAsync()](about:/help-and-docs/apis/management-dotnet/model/project-methods#deleteasync)

 

Delete the project instance asynchronously.