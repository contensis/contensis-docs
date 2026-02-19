1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [APIs](https://www.contensis.com/help-and-docs/apis)
3.  [HTTP Management API](https://www.contensis.com/help-and-docs/apis/management-http)
4.  Assets

[Log in to add to favourites](https://www.contensis.com/account/login)

Page last updated 25 September 2024

## Create an asset

Before an asset can be created, an [asset file needs to be uploaded](https://www.contensis.com/help-and-docs/apis/management-http/assets/upload-asset-file). This will return a temporary *fileId* value which can be used as a file reference when creating the entry that represents the asset.

The AssetFile type needs to used in a field called "sysAssetFile" and the dataFormat within the `sys` object needs to be specified as "asset".

### Example request

The JSON below is an example of an entry that represents an asset. This can be used to create an asset in the same way as [creating an entry](https://www.contensis.com/help-and-docs/apis/management-http/content/entries/create-an-entry) as assets are entries with additional properties.

JSON

```
{
    "title": "Batman Returns",

    "sysAssetFile": {
        "fileId": "25bd73bb-cbb0-454f-a762-2bee08a68cbe.jpg",
        "parentNodePath": "/uploads/movie-posters"
    },

    "sys": {
        "projectId": "movieDb",
        "dataFormat": "asset"
    }
}
```

## Updating an asset

Asset fields (i.e. title, description) can be [updated just like an entry](https://www.contensis.com/help-and-docs/apis/management-http/content/entries/update-an-entry), but updating the file that an asset represents requires a new file to be uploaded as an asset file beforehand and then a new file reference be set.

### Example request

In the example below a new "fileId" has been specified in the "sysAssetFile" field. When the [entry is updated](https://www.contensis.com/help-and-docs/apis/management-http/content/entries/update-an-entry) then the file that the entry represents is updated.

JSON

```
{
    "title": "Batman Returns",
    "Description": "Batman Returns release poster",

    "sysAssetFile": {
        "fileId": "97d70ad2-017f-46ff-8d9e-f8d054652d9c.jpg"
    },

    "sys": {
        "id": "0484bd0b-86d3-4d26-ac97-67514add802b",
        "contentTypeId": "image",
        "projectId": "movieDb",
        "dataFormat": "asset",
        "language": "en-GB",
        "version": {
            "versionNo": "1.0"
        }
    }
}
```