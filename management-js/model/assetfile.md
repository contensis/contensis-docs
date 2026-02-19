1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [APIs](https://www.contensis.com/help-and-docs/apis)
3.  [JS Management API](https://www.contensis.com/help-and-docs/apis/management-js)
4.  Model

[Log in to add to favourites](https://www.contensis.com/account/login)

Page last updated 04 December 2020

An AssetFile type is used for the creation or update of an asset. The type is always used as a [entry](https://www.contensis.com/help-and-docs/apis/management-js/model/entry) field called 'sysAssetFile'.

## Properties

Name

Type

Format

Description

fileId

string

GUID

The file reference returned from an [asset file upload](https://www.contensis.com/help-and-docs/apis/management-js/assets/upload-asset-file)

filename

string

An optional parameter to override the name of the file

parentNodePath

string

Forward-slash separated

The path to the parent node under which the asset should be created

## Example

JSON

```
{
    "sysAssetFile": {
        "fileId": "69ee6d40-32fd-452a-981b-f94abffdecc9.jpg",
        "filename": "batman-returns.jpg",
        "parentNodePath": "/uploads/movie-posters"
    }
}
```