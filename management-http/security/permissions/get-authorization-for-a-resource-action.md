## We value your privacy

We use cookies to improve your experience. [Privacy policy](https://www.contensis.com/privacy-and-cookies).

[Skip to main content](#main)

1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [APIs](https://www.contensis.com/help-and-docs/apis)
3.  [HTTP Management API](https://www.contensis.com/help-and-docs/apis/management-http)
4.  [Security](https://www.contensis.com/help-and-docs/apis/management-http/security)
5.  [Permissions overview](https://www.contensis.com/help-and-docs/apis/management-http/security/permissions)

[Log in to add to favourites](https://www.contensis.com/account/login)

Page last updated 31 January 2025

Gets an authorization confirmation for the requested user, resource and action.

HTTP

```
GET /api/management/projects/﻿﻿{projectId}﻿﻿/security/permissions/﻿﻿{resourceType}﻿﻿/﻿﻿{resourceId}﻿﻿/actions/﻿﻿{action}﻿﻿?userId=﻿﻿{userId}﻿﻿&language=﻿﻿{language}
```

## Parameters

Name

Parameter type

Type

Format

projectId

path

string

The project identifier, e.g. "movieDb". Found in the project overview screen of the management console.

resourceType

path

string

The type of resource to retrieve permissions for. Permitted values are: assets, audiences, blocks, comments, contenttypes, domains, entries, eventstreams, forms, manifests, nodes, proxies, redirects, renderers, signals, views, webhooksubscriptions

resourceId

path

string

Id of the resource to retrieve permissions for.

action

path

string

Name of the action to check authorization for.

userId

query

string

The optional id of the user to check authorization for.

language

query

string

[LanguageCode](https://www.contensis.com/help-and-docs/apis/management-http/key-concepts/localization)

Example request

JSON

```
GET: /api/management/projects/movieDb/security/permissions/entries/a65a9d9d-ee64-4c25-a80c-ab5aee00fb9d/actions/sys.create/?userId=a.user
```

### Response message

HTTP status code

Reason

Response model

200

The action is authorized

Authorized true

404

Not authorized for action

[Error](https://www.contensis.com/help-and-docs/apis/management-http/key-concepts/errors)

500

InternalServerError

[Error](https://www.contensis.com/help-and-docs/apis/management-http/key-concepts/errors)

Example request

JSON

```
{
    "authorized": true
}
```