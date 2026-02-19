## We value your privacy

We use cookies to improve your experience. [Privacy policy](/privacy-and-cookies).

[Skip to main content](#main)

1.  [Help and docs](/help-and-docs)
2.  [APIs](/help-and-docs/apis)
3.  [HTTP Management API](/help-and-docs/apis/management-http)
4.  Content
5.  Content types

[Log in to add to favourites](/account/login)

Page last updated 25 September 2024

Content type groups are used to organise related fields within a [content type definition](/help-and-docs/apis/management-http/content/content-types/content-types). For entries, this organisation appears as tabs in the entry editor, while in forms these groups are rendered as pages.

Each group is defined by a name, ID, and description. The name is displayed as the tab or page title, and the description appears at the top, providing context before the fields are shown. The ID is an internal reference that becomes permanent once saved and cannot be modified.

### Properties of a group

Name

Type

Format

Description

**id**

string

\-

A group identifier which is unique within the content type

**name**

object

localized value

The friendly name given to the content type group

**description**

object

localized value

A description which is displayed at the top of the tab/page

### Example of two groups used in an enquiry form as pages

JSON

```
{
    "groups": [
        {
            "id": "details",
            "name": {
                "en-GB": "Personal Information"
            },
            "description": {
                "en-GB": "Please provide accurate details to help us process your enquiry efficiently."
            }
        },
        {
            "id": "enquiry",
            "name": {
                "en-GB": "Enquiry Information"
            },
            "description": {
                "en-GB": "Specify the type of enquiry and include any additional information or context that will help us understand and address your request."
            }
        }
    ]
}
```