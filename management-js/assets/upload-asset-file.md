A file is required to be uploaded to the asset resource endpoint before an asset can be created. A content type of multipart/form-data is used to perform the upload. A file id is returned for a successful upload which then can be used as a file reference in a [AssetFile](https://www.contensis.com/help-and-docs/apis/management-js/model/assetfile) field when creating an asset. Multiple files can be uploaded in a single request with the resulting file ids returning in the same order as they are uploaded. It is not possible to have a single upload request larger than 2GB, though depending on your connection speed to the CMS, your upload may time out before reaching that limit.  

POST /api/management/projects/**{projectId}**/assets/

### Parameters

Name

Parameter type

Type

Format

Description

projectId

path

string

 

The project identifier.

### Example request