## We value your privacy

We use cookies to improve your experience. [Privacy policy](/privacy-and-cookies).

[Skip to main content](#main)

1.  [Help and docs](/help-and-docs)
2.  [APIs](/help-and-docs/apis)
3.  [HTTP Management API](/help-and-docs/apis/management-http)
4.  Assets

[Log in to add to favourites](/account/login)

Page last updated 25 September 2024

A file is required to be uploaded to the asset resource endpoint before an asset can be created. A content type of multipart/form-data is used to perform the upload. A file id is returned for a successful upload which then can be used as a file reference in a AssetFile field when creating an asset. Multiple files can be uploaded in a single request with the resulting file ids returning in the same order as they are uploaded. It is not possible to have an upload larger than 2GB, though depending on your connection speed to the CMS, your upload may time out before reaching that limit.

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

Example request

JSON

```
POST /api/management/projects/website/assets HTTP/1.1
Authorization: Bearer [YOUR_AUTH_TOKEN]
Content-Type: multipart/form-data;
Content-Length: 230563
boundary=--upload_boundary

--upload_boundary
Content-Type: image/jpeg

[JPEG_DATA]

--upload_boundary
Content-Type: image/jpeg

[JPEG_DATA]
--upload_boundary--
```

### Response message

HTTP status code

Reason

Response model

201

Created

Array of file id objects

401

Unauthorized

[Error](/help-and-docs/apis/management-http/key-concepts/errors)

500

InternalServerError

[Error](/help-and-docs/apis/management-http/key-concepts/errors)

Example

JSON

```
[
    {
        "fileId": "25bd73bb-cbb0-454f-a762-2bee08a68cbe.jpg"
    },
    {
        "fileId": "97d70ad2-017f-46ff-8d9e-f8d054652d9c.jpg"
    }
]
```