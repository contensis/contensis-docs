1.  [Help and docs](https://www.contensis.com/help-and-docs)
2.  [APIs](https://www.contensis.com/help-and-docs/apis)
3.  [JS Delivery API](https://www.contensis.com/help-and-docs/apis/delivery-js)
4.  Key concepts

[Log in to add to favourites](https://www.contensis.com/account/login)

Page last updated 13 November 2024

## Install the Delivery API client

Install the contensis-delivery-api package to your project dependencies using npm, or your preferred Node.js package manager.

Shell

```
npm install --save contensis-delivery-api
```

## Import the client

Follow the examples with the preferred coding style that best suits your project

TypeScript

```
// Using TypeScript, or ES Module syntax
import { Client } from "contensis-delivery-api";
```

JavaScript

```
// Using Common JS syntax
const { Client } = require("contensis-delivery-api");
```

## Initialise the client

As a minimum, you need to supply the API root URL, access token, and project ID to initialise the client

Further [options](https://www.contensis.com/help-and-docs/apis/delivery-js/model/config) can be set that are applied to all requests made from the [client](https://www.contensis.com/help-and-docs/apis/delivery-js/model/client) instance

Example creating a Delivery API client in JavaScript or TypeScript

TypeScript

```
const client = Client.create({
  rootUrl: "https://api-<cms-alias>.cloud.contensis.com",
  accessToken: "<environment-access-token>",
  projectId: "<project-api-id>",
});
```

## Next steps

We have a  [Delivery API client](https://www.contensis.com/help-and-docs/apis/delivery-js/model/client) connected to our CMS, all operations are available from within this client.

If you are new to using the Delivery API you could test your client by trying one of the following articles first before exploring more complex use cases